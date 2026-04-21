---
name: AVScriptEditor
description: Editorial layer for Compass Classroom AV-script Google Sheets. Reads a per-course profile, walks the transcript, and writes per-row image briefs (concept + image type) into a dedicated BRIEF column of a duplicate WORKING tab — then optionally dispatches to FindScienceMedia or FindArt for sourcing. USE WHEN edit AV script, AV script editor, AVScriptEditor, identify images for AV script, draft image briefs, apply course profile to script, compass av script, update profile from critique.
---

# AVScriptEditor

Editorial dispatcher for AV-script **image** planning. Decides **which** audio beats deserve images and **what kind** of image each beat needs, then dispatches to the right sourcing skill. Per-course editorial taste lives in profile files so the skill scales to every Compass course.

**Scope: images only.** On-screen text callouts (word-of-the-day builds, scripture citations, definition cards, etc.) are NOT this skill's job. Text selection needs textbook context that the image-review agent doesn't have, and mixing the two muddies both passes. Text beats are left blank by AVScriptEditor; a separate text-handler agent (future) fills them in.

## 🚨 MANDATORY: Voice Notification (REQUIRED BEFORE ANY ACTION)

When this skill is invoked:

1. Send voice notification:
   ```bash
   curl -s -X POST http://localhost:8888/notify \
     -H "Content-Type: application/json" \
     -d '{"message": "Running the WORKFLOWNAME workflow in AVScriptEditor"}' \
     > /dev/null 2>&1 &
   ```

2. Output text notification:
   ```
   Running the **WorkflowName** workflow in **AVScriptEditor**...
   ```

## Quick Decision: Which Workflow?

```
Has the WORKING tab been created AND just need briefs written?
+-- YES --> BriefOnly (safe default; editor writes BRIEF column only)
+-- NO  --> Sourcing needed too?
    +-- Briefs + live URLs/thumbs in new tab --> PopulateSheet (end-to-end)
    +-- Briefs already written, now source --> BriefAndSource
    +-- Reviewer gave critique; evolve profile --> UpdateProfile
```

**Default when unspecified:** `BriefOnly`. Safer, cheaper, keeps the human editor (Ryan et al.) in the loop before sourcing fires.

## Workflow Routing

| Trigger | Workflow |
|---------|----------|
| "draft briefs", "brief-only", "editorial pass only" | `Workflows/BriefOnly.md` |
| "brief and source", "source after brief" | `Workflows/BriefAndSource.md` |
| "populate sheet", "end to end", "full pipeline" | `Workflows/PopulateSheet.md` |
| "update profile", "evolve profile from critique" | `Workflows/UpdateProfile.md` |

## Invocation Pattern

User specifies the course slug on the front-end. The slug maps 1:1 to a profile file:

```
<slug>                           →  Profile<PascalCase>.md
astronomy-faulkner               →  ProfileAstronomyFaulkner.md
history-stobaugh   (future)      →  ProfileHistoryStobaugh.md
```

**Canonical natural-language invocation:**

> "Edit the astronomy-faulkner AV script at \<sheet-url\>"
> "Draft briefs for astronomy-faulkner on \<sheet-url\>, brief-only mode"
> "Run populate-sheet for astronomy-faulkner on \<sheet-url\>"

If the slug is missing, ask via AskUserQuestion listing available profiles (every file in skill root matching `Profile*.md` minus `ProfileTemplate.md`).

## Profiles (Editorial Profiles)

| Slug | File | Editor | Instructor | Status |
|------|------|--------|------------|--------|
| `astronomy-faulkner` | `ProfileAstronomyFaulkner.md` | Ryan Stufflebeam | Danny Faulkner | v0 (seed from Ch 1 review) |

## How to Add a New Course Profile

Every new course needs its own profile so the skill inherits its editorial taste. Steps:

1. **Pick a slug** — `<course>-<instructor-last-name>`, all lowercase, hyphen-separated.
   - Examples: `history-stobaugh`, `bible-jones`, `writing-wilson`
2. **Copy the template** into a new file in skill root:
   ```
   cp ~/.claude/skills/AVScriptEditor/ProfileTemplate.md \
      ~/.claude/skills/AVScriptEditor/Profile<PascalCase>.md
   ```
   Slug → filename mapping is strict: `history-stobaugh` → `ProfileHistoryStobaugh.md`.
3. **Fill in the profile** — every section in the template matters. Pay special attention to:
   - `editor` and `instructor` in frontmatter (who owns editorial taste, who teaches the course)
   - `Density Target` (images per audio time unit)
   - `Aesthetic Mix` (target distribution across science / historical / art — **no text**; text is a separate agent's job)
   - `Sourcing Priority by Beat Type` (when to use FindScienceMedia vs FindArt)
   - `Forbidden Moves` — start with 2–3 obvious ones; more accumulate as reviewers give feedback
4. **Register in the table above** — add a row to the Profiles table in this file.
5. **Seed from a test pass** — run `BriefOnly` on a short test chapter, get reviewer critique, then run `Workflows/UpdateProfile.md` to lift the profile from v0 (seed) to v1 (first review round).

The profile is a living document. Treat it the way a DP treats a shot list: sharpened every production, never finished.

## Quick Reference

- **Editor is the human** (Ryan et al.) — profile codifies their taste, skill executes it
- **Sourcing is not this skill's job** — dispatches to FindScienceMedia (NASA/NOAA/USGS) and FindArt (Wikimedia/museums)
- **Default mode is BriefOnly** — nothing gets sourced without explicit opt-in
- **Profiles are living documents** — each reviewer critique updates the profile via `UpdateProfile`
- **Sheet convention:** duplicate Sheet1 → `Sheet1 (WORKING)`; column D = IMAGE concept, E = FILE NAME, H = `=IMAGE()` thumbnail, I = bare hi-res URL, J = BRIEF (editorial brief + sourcing hint)
- **NOTES (column F) is OFF-LIMITS to this skill** — F is reserved for human editor markers that flow downstream to Final Cut as timeline annotations. Never write briefs or source info to F.

## Sheet Column Map (shared across workflows)

| Col | Header | Who writes |
|-----|--------|-----------|
| A | TIMECODE | source (do not edit) |
| B | AUDIO | source (do not edit) |
| C | TEXT | source (do not edit) |
| D | IMAGE | AVScriptEditor (concept description) |
| E | FILE NAME | AVScriptEditor (on sourcing) |
| F | NOTES | **reserved** — human editor only (flows to Final Cut as timeline markers). AVScriptEditor NEVER writes here. |
| G | SECTION | source (do not edit) |
| H | THUMBNAIL | AVScriptEditor on sourcing (`=IMAGE()` formula) |
| I | URL | AVScriptEditor on sourcing (bare hi-res URL) |
| J | BRIEF | AVScriptEditor (editorial brief: `TYPE:<tag> \| <description> \| <sourcing hint>`; source + license appended on sourcing) |

## Related Skills

- **FindScienceMedia** — NASA/NOAA/USGS sourcing (Tier 1: public domain)
- **FindArt** — Wikimedia/museums/historical public-domain art
- **GoogleWorkspace** — Sheets read/write via `gws` CLI
