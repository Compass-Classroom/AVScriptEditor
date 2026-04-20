---
slug: astronomy-faulkner
course: Astronomy (Compass Classroom, Danny Faulkner)
instructor: Danny Faulkner
editor: Ryan Stufflebeam
audience: Classical Christian high school (homeschool + Trail Life context)
version: 0 (seed)
last_updated: 2026-04-20
source_of_truth: Ryan Stufflebeam's review of Chapter 1 test pass (first 2 min)
---

# Profile: Astronomy / Faulkner

Editorial taste profile for Dr. Danny Faulkner's Astronomy course, edited by Ryan Stufflebeam. First seeded from Ryan's row-by-row critique of the Chapter 1 image test (WORKING tab of sheet `1VlYEEIqZPcYSvpUSTjWwEF_1BMrSTzO9qSx2KYvLSy0`).

## Editorial Voice

- Pastoral-scholarly. High-school audience — classical Christian homeschool.
- Faulkner's teaching style is anecdotal, biblical, historically grounded. Images should support *meaning*, not decorate topic keywords.
- When Faulkner names a historical figure, people group, or period, imagery should be **historical/artistic** (engravings, woodcuts, museum pieces), not modern space photography.
- When he talks about cosmos, celestial bodies, or Earth observation, imagery should be **scientific** (NASA / NOAA / USGS).
- When he defines a word, cites scripture, or explains a vocabulary term, **on-screen text** beats any image.

## Density Target

**One image every 20–30 seconds of audio.** Not per line. Not per sentence.

Explicit rule: a 30-second section should have **1–2 images**, not 5. Hold images longer; let the viewer stay with a concept.

## Aesthetic Mix (target distribution per chapter)

| Type | Target % | Typical sourcing |
|------|---------|------------------|
| NASA / NOAA / USGS science imagery | ~40% | FindScienceMedia |
| Historical engravings, woodcuts, museum pieces | ~35% | FindArt |
| On-screen text only (no image) | ~15% | n/a (production does the text) |
| Artistic illustration, paintings, maps | ~10% | FindArt |

Percentages are directional, not enforced — aesthetic fit to the beat wins.

## Sourcing Priority by Beat Type

| Beat signal | Primary sourcer | Fallback |
|-------------|----------------|----------|
| Cosmos, planets, stars, nebulae, deep space | FindScienceMedia | FindArt (historical astronomy art) |
| Earth observation, weather, seasons from space | FindScienceMedia | — |
| Etymology, vocabulary, Greek/Latin words | **on-screen text only** | FindArt (if a period visual strengthens it) |
| Scripture citation (book:chapter:verse) | **on-screen text only** | — |
| Ancient/historical figures, cultures, eras | FindArt | FindScienceMedia (only if literal object) |
| Agriculture, daily life, diurnal human scenes | FindArt (paintings, etchings, photos) | FindScienceMedia (only if landscape scale works) |
| Biblical scenes (Creation, Day 2, Day 4, Magi) | FindArt (historical religious art) OR cosmic Hubble/JWST imagery | — |

## Forbidden Moves (anti-patterns from Ryan's critique)

1. **Satellite/aerial imagery for human-scale farm or labor work** — feels abstract and doesn't land with high-school viewers
2. **Topic-keyword matching without meaning matching** — e.g., a solar-system montage for "astronomy is about comets, planets, sun, moon" misses the pedagogical point
3. **More than 1 image per 30 seconds** — over-cutting; viewer can't absorb
4. **Modern telescope photos for "arranging the stars" / cataloging concept** — the concept is *information arrangement*, not equipment
5. **NASA deep-space image for "oldest of the sciences"** — this beat needs a historical engraving (Greek or medieval astronomers at work)
6. **Space imagery for etymology beats** — Greek word roots should be on-screen text, optionally paired with a period-appropriate historical illustration
7. **Cheesy stock-feel composites** — "family portrait of planets" clip-art aesthetic
8. **Pretty-but-irrelevant imagery** — a gorgeous Hubble deep-field does not automatically support whatever the narrator is saying

## On-Screen-Text-Only Content Types (no image needed)

- Greek or Latin word roots and translations
- Scripture citations (explicit book/chapter/verse)
- Vocabulary definitions being read aloud
- Lists of things where the list itself is the point (e.g., "light, signs, times, seasons" can be a bullet build)
- Short definitional asides ("diurnal means...")

## Winning Patterns (from Ryan's review)

- **Atmospheric + literal**: ISS orbital sunrise with lens flare supporting "diurnal creatures / purpose of light" (I20) — the image *was* the concept, not just a topic illustration
- **Concept cycle**: for Day 4 "sun, moon, and stars," a short cycle — sun → moon → stars → back — beats a single composite
- **Period-correct historical art for historical claims**: engraving of Greek astronomers for "aster / nomos" etymology or "oldest of the sciences"
- **Atmospheric Earth imagery for "marking time" / orbital mechanics**: day/night terminator from space (I17 / I20 territory)
- **Pillars of Creation for cosmic-scale biblical language** (Day 2 "heavens") — iconic, evocative, not generic

## Losing Patterns (from Ryan's review — do not repeat)

- Milky Way airglow over Earth horizon for the *etymology* of "astronomy" (I3) — beautiful but off-topic; that beat needs a historical image or on-screen text
- Telescope equipment for "arranging the stars" concept (I5) — equipment ≠ cataloging
- Solar-system planet montage for "astronomy is about comets, planets, sun, moon" (I7, I10) — generic and cheesy
- Hubble deep-field for "oldest of the sciences" (I12) — pretty but needs a historical engraving
- Satellite farm image for "everybody worked on the farm" (I27) — need an artistic/historical pairing
- Equinox/solstice diagram for "track annual cycle to know when to plant" (I31) — the actual content in the next section is about Sirius + Nile flooding, not the equinoxes

## Image Type Tags (used in briefs)

Every brief written by AVScriptEditor includes a `TYPE:` tag so downstream workflows know where to route for sourcing. Canonical tags:

| Tag | Meaning | Sourcer |
|-----|---------|---------|
| `science` | NASA/NOAA/USGS-style scientific imagery | FindScienceMedia |
| `historical` | Engravings, woodcuts, old photographs, period paintings | FindArt |
| `art` | Fine art, illustration, non-historical artistic rendering | FindArt |
| `text` | On-screen text only, no image needed | (production) |
| `cycle:N` | Multi-image concept cycle (e.g., `cycle:3` = three images shown in quick succession) | varies — specify per-slot |
| `hold` | Intentionally reuse / hold prior image for this beat | (editor) |

## Brief Format (what goes in NOTES column)

```
TYPE:<tag> | <concrete visual description, 8-16 words> | <sourcing hint or specific subject keyword>
```

Examples:
```
TYPE:text | "astron-" + "-nomos" — Greek roots side-by-side with English | on-screen text, no image
TYPE:historical | 18th-c. engraving of Greek astronomers at work | FindArt: "ancient Greek astronomers engraving"
TYPE:science | Hubble/JWST nebula evoking cosmic creation | FindScienceMedia: "Pillars of Creation"
TYPE:cycle:3 | Sun → Moon → starfield, 2 sec each | slot 1: sun disk; slot 2: crescent moon; slot 3: starfield
TYPE:hold | keep prior image on screen
```

## Profile Evolution Log

- **v0 (2026-04-20)** — Initial seed from Ryan Stufflebeam's review of Chapter 1 test (first 2 min, sheet `1VlYEEIqZPcYSvpUSTjWwEF_1BMrSTzO9qSx2KYvLSy0`). All forbidden moves + winning/losing patterns derive from that review.
