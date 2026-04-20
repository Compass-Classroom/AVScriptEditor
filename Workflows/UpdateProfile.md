# UpdateProfile Workflow

Evolves a course profile based on reviewer critique. Takes a critique (Slack/doc/transcript) + the target profile, proposes a diff, and — after human approval — writes the new version to the profile file with an incremented version and updated evolution log.

## When to use

- A reviewer (Ryan et al.) has delivered row-by-row critique of a populated WORKING tab
- After every editorial review pass — profiles should get sharper with each round
- Before running `PopulateSheet` on a new chapter of the same course

## Inputs

- **Profile slug** (e.g., `astronomy-faulkner`)
- **Critique** — pasted transcript, Slack thread, doc link, or meeting notes (Granola)
- **Optional: specific sheet/chapter** the critique was about (for citation in the evolution log)

## Procedure

1. **Voice notification.**
2. **Load current profile** at `~/.claude/skills/AVScriptEditor/Profile<PascalCase>.md`.
3. **Parse the critique.** Extract discrete signals:
    - Forbidden moves (things the reviewer said don't do) → new entries under `## Forbidden Moves`
    - Winning patterns (things the reviewer said worked) → new entries under `## Winning Patterns`
    - Losing patterns (things the reviewer said didn't work) → new entries under `## Losing Patterns`
    - Density adjustments → update `## Density Target`
    - Aesthetic-mix adjustments → update the table under `## Aesthetic Mix`
    - Sourcing-priority adjustments → update `## Sourcing Priority by Beat Type`
    - On-screen-text-only additions → new entries under `## On-Screen-Text-Only Content Types`
4. **Draft the proposed diff.** Present a clear before/after for each changed section, and a new entry for `## Profile Evolution Log` with version bump (e.g., v0 → v1) and source citation.
5. **Human gate (AskUserQuestion).** Present the diff summary and ask: accept, revise, or reject. Do NOT write until approved — profiles are load-bearing editorial documents.
6. **Apply accepted diff.** Edit the profile file, bump `version:` and `last_updated:` in frontmatter, append the evolution log entry.
7. **Report.** Return summary of changes + new version + profile path.

## Version numbering

- `v0` — initial seed (usually from a single reviewer pass on a test chapter)
- `v1` — first round of reviewer feedback incorporated
- `v2, v3, …` — subsequent refinement rounds
- Major version bump (`v2.0` → `v3.0`) only if the editor or course lead changes, OR if the audience materially shifts

## Anti-patterns

- Do NOT silently rewrite the profile. Always show the diff and get approval.
- Do NOT delete prior Winning/Losing Patterns unless explicitly contradicted — patterns accumulate.
- Do NOT update a profile without adding an evolution-log entry citing the source critique.
- Do NOT edit a profile mid-run of another workflow — fully finish UpdateProfile before re-running BriefOnly or PopulateSheet.

## Example (Astronomy/Faulkner v0 → v1)

After Ryan's first review, new entries would include:

```
## Forbidden Moves (additions)
9. Generic "stars in sky" imagery for etymology beats — text-on-screen does more work
...

## Winning Patterns (additions)
- Lens-flare / atmospheric Earth-from-orbit for "purpose of light" beats — meaning matches image

## Losing Patterns (additions)
- NASA equinox/solstice diagram for "annual planting cycle" beat — missed that the next-section content is about Sirius/Nile

## Profile Evolution Log
- **v1 (2026-04-20)** — Incorporated Ryan's row-by-row critique of first 2 min of Ch 1 test (sheet `1VlYEEIqZPcYSvpUSTjWwEF_1BMrSTzO9qSx2KYvLSy0`). Added 3 forbidden moves, 1 winning pattern, 1 losing pattern.
```

## Verification checklist

- [ ] Diff was presented and explicitly approved before write
- [ ] Profile frontmatter `version:` bumped
- [ ] Profile frontmatter `last_updated:` refreshed
- [ ] Evolution log entry appended with source citation
- [ ] No pattern deletions unless explicitly contradicted
