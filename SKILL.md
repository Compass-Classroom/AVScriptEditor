---
name: AVScriptEditor
description: Editorial layer for Compass Classroom AV-script Google Sheets. Reads a per-course profile, walks the transcript, and writes per-row image briefs (concept + image type) into the NOTES column of a duplicate WORKING tab — then optionally dispatches to FindScienceMedia or FindArt for sourcing. USE WHEN edit AV script, av script editor, identify images for AV script, draft image briefs, apply course profile to script, compass av script, update profile from critique, avscripteditor.
---

# AVScriptEditor

Editorial dispatcher for AV-script image planning. Decides **which** audio beats deserve images and **what kind** of image each beat needs, then dispatches to the right sourcing skill. Per-course editorial taste lives in profile files so the skill scales to every Compass course.

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
+-- YES --> BriefOnly (safe default; editor writes NOTES only)
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

New courses: copy `ProfileTemplate.md` → `Profile<PascalCase>.md` and fill it in.

## Quick Reference

- **Editor is the human** (Ryan et al.) — profile codifies their taste, skill executes it
- **Sourcing is not this skill's job** — dispatches to FindScienceMedia (NASA/NOAA/USGS) and FindArt (Wikimedia/museums)
- **Default mode is BriefOnly** — nothing gets sourced without explicit opt-in
- **Profiles are living documents** — each reviewer critique updates the profile via `UpdateProfile`
- **Sheet convention** (from the Astro Ch 1 working tab): duplicate Sheet1 → `Sheet1 (WORKING)`; column D = IMAGE concept, E = FILE NAME, F = NOTES (brief + source + license), H = `=IMAGE()` thumbnail, I = bare hi-res URL

## Sheet Column Map (shared across workflows)

| Col | Header | Who writes |
|-----|--------|-----------|
| A | TIMECODE | source (do not edit) |
| B | AUDIO | source (do not edit) |
| C | TEXT | source (do not edit) |
| D | IMAGE | AVScriptEditor (concept description) |
| E | FILE NAME | AVScriptEditor (on sourcing) |
| F | NOTES | AVScriptEditor (brief + image type + sourcing hint + license) |
| G | SECTION | source (do not edit) |
| H | THUMBNAIL | AVScriptEditor on sourcing (`=IMAGE()` formula) |
| I | URL | AVScriptEditor on sourcing (bare hi-res URL) |

## Related Skills

- **FindScienceMedia** — NASA/NOAA/USGS sourcing (Tier 1: public domain)
- **FindArt** — Wikimedia/museums/historical public-domain art
- **GoogleWorkspace** — Sheets read/write via `gws` CLI
