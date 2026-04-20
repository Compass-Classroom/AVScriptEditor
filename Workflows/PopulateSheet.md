# PopulateSheet Workflow

End-to-end pipeline: duplicate Sheet1 → write briefs → dispatch sourcing → populate all columns. The full "go from raw AV-script sheet to reviewable WORKING tab" run. Use only when the profile is mature and the editor trusts the skill to drive.

## When to use

- Profile is calibrated (≥ v1, post first reviewer feedback cycle)
- Editor explicitly asks for end-to-end
- New chapter sheets arriving in bulk

## Inputs

- **Sheet URL**
- **Profile slug**
- **Row range** (optional; default = all rows in Sheet1 with a TIMECODE)

## Procedure

1. **Voice notification.**
2. **Duplicate Sheet1.** Use `gws sheets spreadsheets batchUpdate` with `duplicateSheet` → new tab named `Sheet1 (WORKING)`, inserted at index 1. Treat original Sheet1 as locked.
3. **Add URL column header** at `I1` (`URL`) if not present.
4. **Run BriefOnly** against the WORKING tab (write briefs to column F).
5. **Run BriefAndSource** against the WORKING tab (dispatch sourcing; populate D, E, H, I; append source info to F).
6. **Resize** rows containing images → 100px; column H → 160px.
7. **Sanity check.** Read back the WORKING tab and confirm: no writes to Sheet1; every briefed row has expected columns populated; no `TYPE:text` row has a URL.
8. **Report.** Return link to the WORKING tab, dispatch summary, and any flagged rows (sourcing failures, ambiguous tags, brief-forbidden-move rewrites).

## Anti-patterns

- Do NOT run `PopulateSheet` if the profile is still at v0 (seed). Use `BriefOnly` first so the editor can validate taste before URLs get pulled at scale.
- Do NOT overwrite an existing WORKING tab without asking — if `Sheet1 (WORKING)` already exists, AskUserQuestion: use existing, create a new dated variant, or abort.

## Verification checklist

- [ ] Sheet1 untouched
- [ ] WORKING tab exists and matches Sheet1's structure
- [ ] All briefed rows populated (D, E, F, H, I)
- [ ] All URLs are PD or CC-BY with attribution
- [ ] Editor summary report returned
