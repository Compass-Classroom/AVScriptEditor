# AVScriptEditor

PAI skill for Compass Classroom AV-script image planning.

Editorial layer that reads a per-course profile, walks an AV-script Google Sheet transcript, and writes per-row image briefs (concept + image type) into the NOTES column of a duplicate WORKING tab — then optionally dispatches to `FindScienceMedia` or `FindArt` for sourcing.

## Design

- **Skill = dispatcher** (lean, opinionated)
- **Profiles = data** (per-course editorial taste lives in `Profile<CourseInstructor>.md` files in skill root)
- **Workflows = execution** (four flows: `BriefOnly`, `BriefAndSource`, `PopulateSheet`, `UpdateProfile`)
- **Sourcing reused** (delegates to existing PAI skills — no duplicate sourcing logic)

## Structure

```
AVScriptEditor/
├── SKILL.md                          # Routing, invocation, voice notification
├── ProfileAstronomyFaulkner.md       # First profile (Editor: Ryan Stufflebeam, Instructor: Danny Faulkner)
├── ProfileTemplate.md                # Scaffold for new course profiles
├── Workflows/
│   ├── BriefOnly.md                  # Editor pass — writes briefs to NOTES column only
│   ├── BriefAndSource.md             # Editor pass + dispatch to FindScienceMedia / FindArt
│   ├── PopulateSheet.md              # End-to-end: duplicate tab, briefs, URLs, thumbnails
│   └── UpdateProfile.md              # Profile evolution from reviewer critique
```

## Usage

```
"Edit the astronomy-faulkner AV script at <sheet-url>"
"Draft briefs for astronomy-faulkner on <sheet-url>, brief-only mode"
"Run populate-sheet for astronomy-faulkner on <sheet-url>"
"Update the astronomy-faulkner profile from this critique: <paste>"
```

## Default mode

`BriefOnly` — safer, cheaper, keeps the human editor in the loop before sourcing fires.

## Profiles currently in the repo

| Slug | Editor | Instructor | Version |
|------|--------|------------|---------|
| `astronomy-faulkner` | Ryan Stufflebeam | Danny Faulkner | v0 (seed) |

## Installation

Clone into your PAI skills directory:

```
cd ~/.claude/skills/
git clone git@github.com:Compass-Classroom/avscripteditor.git AVScriptEditor
```

Skill auto-registers in PAI on next session start.

## Dependencies

- PAI with `FindScienceMedia` and `FindArt` skills installed
- `gws` (GoogleWorkspace CLI) for sheet read/write
- `gh` (GitHub CLI) for repo operations
