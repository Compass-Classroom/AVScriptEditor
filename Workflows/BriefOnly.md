# BriefOnly Workflow

Default, safest AVScriptEditor workflow. Walks the transcript, writes per-row image briefs into the BRIEF column (J) of the WORKING tab. **No sourcing fires.** Editor reviews briefs before anything gets sourced.

**Column F (NOTES) is off-limits** — reserved for human editor markers that flow to Final Cut as timeline annotations. Never write there.

## When to use

- First pass on a new script
- Profile is still being calibrated (e.g., Astronomy/Faulkner v0 → v1)
- Human editor (Ryan et al.) wants to see and approve briefs before URLs are pulled

## Inputs

- **Sheet URL** (Google Sheets)
- **Profile slug** (e.g., `astronomy-faulkner`)
- **Row range** (optional; default = all rows with non-empty TIMECODE and AUDIO)

## Preconditions

- WORKING tab must exist. If it does not, either run `PopulateSheet` first, or duplicate Sheet1 manually via Sheets UI / `gws batchUpdate duplicateSheet`.
- The WORKING tab should preserve the column layout (A–J per SKILL.md Sheet Column Map).
- If column J header (`BRIEF`) is missing from row 1, write it before any briefs.

## Procedure

1. **Voice notification.** Send the mandatory curl + text notification.
2. **Load profile.** Read `~/.claude/skills/AVScriptEditor/Profile<PascalCase>.md`. If the slug file does not exist, stop and ask via AskUserQuestion which profile to use (list `Profile*.md` files minus `ProfileTemplate.md`).
3. **Read the transcript.** `gws sheets spreadsheets values get` on the WORKING tab, range `A1:J<last_row>`. Capture TIMECODE, AUDIO, TEXT, SECTION per row.
4. **Pacing pass.** Walk the rows top-to-bottom. Applying the profile's **density target**, decide which rows get image briefs and which do not. Rows without a brief are explicitly left blank (not forgotten). Rows matching the profile's `Text-Beat Signals` stay blank — they belong to the future text-handler agent, not this skill.
5. **Beat-type classification.** For each brief-eligible row, decide the image type using the profile's **Sourcing Priority by Beat Type** table. Assign one of: `science`, `historical`, `art`, `cycle:N`, `hold`. Do NOT emit `TYPE:text` — text handling is out of scope.
6. **Concrete visual description.** Write an 8–16 word visual description of the image concept. Must describe *what the image shows* in a way that matches the *meaning* of the audio, not just the topic keyword. Cross-check against the profile's **Forbidden Moves** — if the brief pattern-matches a forbidden move, rewrite.
7. **Sourcing hint.** Append a short hint naming the likely subject or search term the sourcer should use (e.g., `FindArt: "Greek astronomers engraving 18th c."` or `FindScienceMedia: "Pillars of Creation JWST"`).
8. **Format.** `TYPE:<tag> | <visual description> | <sourcing hint>` — single line per row.
9. **Write to sheet.** `gws sheets spreadsheets values batchUpdate` with `valueInputOption: RAW`, writing each brief to column J (BRIEF) of its row on the WORKING tab. Never write to column F (NOTES).
10. **Report.** Return a summary: rows briefed, rows intentionally blank, tag distribution, any forbidden-move rewrites.

## Anti-patterns (do not do these in this workflow)

- Do NOT write to Sheet1 — only the WORKING tab.
- Do NOT call FindScienceMedia or FindArt. That is `BriefAndSource`'s job.
- Do NOT write to columns D, E, F, H, or I. Only column J. Column F (NOTES) is especially off-limits — it flows to the Final Cut timeline as human-editor markers.
- Do NOT over-brief — honor the profile's density target. If in doubt, leave the row blank; held imagery is a valid editorial choice.

## Output example

```
Row 3  (00:00): (blank — Greek etymology; text-handler agent's territory)
Row 4  (00:05): (blank — hold prior)
Row 5  (00:09): TYPE:historical | 18th-c. engraving of Greek astronomers cataloging stars | FindArt: "ancient Greek astronomer engraving"
Row 12 (00:30): TYPE:historical | medieval astronomer with astrolabe, woodcut style | FindArt: "medieval astronomer woodcut"
Row 13 (00:34): TYPE:science | Pillars of Creation evoking cosmic heavens | FindScienceMedia: "Pillars of Creation JWST"
Row 20 (01:08): TYPE:science | orbital sunrise with lens flare — diurnal cycle | FindScienceMedia: "ISS orbital sunrise"
Row 27 (01:32): TYPE:art | 19th-c. painting of farmers at harvest in sunlight | FindArt: "harvest painting 19th century"
```

## Verification checklist

- [ ] Every row with a brief has a `TYPE:` tag
- [ ] Every brief respects the profile's density target
- [ ] Every brief passes the forbidden-moves check
- [ ] No writes to Sheet1
- [ ] No writes to columns D, E, H, or I
- [ ] Report summarizes tag distribution
