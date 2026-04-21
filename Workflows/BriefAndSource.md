# BriefAndSource Workflow

Runs `BriefOnly` first, then dispatches each brief to the right sourcing skill (`FindScienceMedia` for `TYPE:science`, `FindArt` for `TYPE:historical`/`TYPE:art`). Populates the IMAGE, FILE NAME, THUMBNAIL, and URL columns of the WORKING tab.

## When to use

- Briefs already drafted and approved by a human editor (or trusted profile is mature)
- Full-chapter image sourcing pass

## Inputs

- **Sheet URL**
- **Profile slug**
- **Row range** (optional — default = all rows with a brief in column J)

## Preconditions

- WORKING tab exists
- Column J has briefs in the canonical format (`TYPE:<tag> | <description> | <hint>`)

## Procedure

1. **Voice notification.**
2. **Load profile** (for sourcing priorities and fallbacks).
3. **Read briefs** from column J of the WORKING tab.
4. **Parse each brief** into `{tag, description, hint}`.
5. **Dispatch by tag:**
    - `TYPE:science` → invoke `FindScienceMedia` (Tier 1: NASA/NOAA/USGS). Pass `description` + `hint` as the search.
    - `TYPE:historical` → invoke `FindArt` with `historical` filter (Wikimedia/museums/public-domain engravings).
    - `TYPE:art` → invoke `FindArt` with `art` filter.
    - `TYPE:cycle:N` → dispatch N times per the per-slot hints; populate with comma-separated URLs in URL column and first-slot thumbnail in H.
    - `TYPE:hold` → skip sourcing; copy prior image's references into IMAGE/FILE NAME/THUMBNAIL/URL.
6. **Select the single best candidate per brief.** If the sourcer returns a shortlist, apply the profile's winning/losing patterns to pick. Prefer `~orig.jpg` URLs for NASA assets.
7. **Write to sheet** (WORKING tab only). Use `gws sheets spreadsheets values batchUpdate`:
    - Column D (IMAGE): short concept name
    - Column E (FILE NAME): `<nasa_id_or_source_id>_<slug>.jpg`
    - Column J (BRIEF): append source + license line to the existing brief (NEVER write to F)
    - Column H (THUMBNAIL): `=IMAGE("<medium_url>")` formula
    - Column I (URL): bare `~orig.jpg` or equivalent hi-res URL
8. **Resize rows and columns** on WORKING tab: rows containing briefs → ~100px; column H → ~160px.
9. **Report.** Return dispatch counts (science/historical/art/text/cycle/hold), any sourcing failures, and a link to the updated WORKING tab.

## Sourcing fallback

If `FindScienceMedia` returns nothing for a `TYPE:science` brief, try `FindArt` as fallback *only if* the profile permits it for that beat type. Otherwise leave IMAGE/URL blank and flag in a final report for the editor to re-brief.

## Anti-patterns

- Do NOT re-read the transcript — briefs in column J are the source of truth.
- Do NOT write to column F (NOTES) under any circumstances — it's human-editor / FCP marker space.
- Do NOT second-guess the editor's tag — if `TYPE:historical`, do NOT silently substitute `TYPE:science` even if easier to source.
- Do NOT mix licenses in a single brief without an explicit note in column F.
- Do NOT write to Sheet1.

## Verification checklist

- [ ] Every row that had a brief has IMAGE + URL populated (or explicit skip reason in NOTES)
- [ ] Every URL is public-domain or CC-BY with attribution
- [ ] `~orig.jpg` (or source equivalent hi-res) used in column I
- [ ] `=IMAGE()` formulas render in column H
- [ ] No Sheet1 modifications
