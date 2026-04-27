---
slug: astronomy-faulkner
course: Astronomy (Compass Classroom, Danny Faulkner)
instructor: Danny Faulkner
editor: Ryan Stufflebeam
audience: Classical Christian high school (homeschool + Trail Life context)
version: 7
last_updated: 2026-04-27
source_of_truth: Ryan Stufflebeam's ch01-1 v1+v5+v6 sourcing reviews — eleven durable sourcing rules; v7 adds five rules from the section-by-section v6 re-source pass
test_sheet: <REDACTED-TEST-SHEET-ID>
---

# Profile: Astronomy / Faulkner

Editorial taste profile for Dr. Danny Faulkner's Astronomy course, edited by Ryan Stufflebeam. First seeded from Ryan's row-by-row critique of the Chapter 1 image test (WORKING tab of sheet `<REDACTED-TEST-SHEET-ID>`), hardened across v2–v4 by a full-lecture sourcing pass on ch01-1 (31 min, ~38 briefed rows) and the resulting FCP timeline review.

## Editorial Voice

- Pastoral-scholarly. High-school audience — classical Christian homeschool.
- Faulkner's teaching style is anecdotal, biblical, historically grounded. Images should support *meaning*, not decorate topic keywords.
- When Faulkner names a historical figure, people group, or period, imagery should be **historical/artistic** (engravings, woodcuts, museum pieces), not modern space photography.
- When he talks about cosmos, celestial bodies, or Earth observation, imagery should be **scientific** (NASA / NOAA / USGS).
- When he defines a word, cites scripture, or explains a vocabulary term, **leave the beat blank** for the separate text-handler agent — AVScriptEditor no longer emits text callouts.

## Density Target

**One image every 20–30 seconds of audio.** Not per line. Not per sentence.

Explicit rule: a 30-second section should have **1–2 images**, not 5. Hold images longer; let the viewer stay with a concept.

## Aesthetic Mix (target distribution per chapter — images only)

| Type | Target % | Typical sourcing |
|------|---------|------------------|
| NASA / NOAA / USGS science imagery | ~45% | FindScienceMedia |
| Historical scientific artifacts (star charts, diagrams, catalogs) | ~25% | FindArt (`artifact`) |
| Historical engravings / woodcuts / paintings of people | ~20% | FindArt (`historical`) |
| Artistic illustration, paintings, maps | ~10% | FindArt (`art`) |

Percentages are directional, not enforced — aesthetic fit to the beat wins. Text beats are out of scope (handled by a separate text-handler agent) and do not count in this distribution.

## Sourcing Priority by Beat Type

| Beat signal | Primary sourcer | Fallback |
|-------------|----------------|----------|
| Cosmos, planets, stars, nebulae, deep space | FindScienceMedia (`science`) | FindArt (historical astronomy art) |
| Earth observation, weather, seasons from space | FindScienceMedia (`science`) | — |
| **Astronomical ideas, catalogs, star charts, historical diagrams** | **FindArt (`artifact`)** — Bayer, Hevelius, Kepler, Flamsteed, Ptolemaic plates | FindScienceMedia (NASA historical reproductions) |
| Etymology, vocabulary, Greek/Latin words | **leave blank** (text agent territory) | FindArt (ONLY if the image clearly supports, not replaces, text) |
| Scripture citation (book:chapter:verse) | **leave blank** (text agent territory) | — |
| Ancient/historical **people** doing science | FindArt (`historical`) | FindScienceMedia (only if literal object) |
| Agriculture, daily life, diurnal human scenes | FindArt (paintings, etchings, photos) | FindScienceMedia (only if landscape scale works) |
| Biblical scenes (Creation, Day 2, Day 4, Magi) | FindArt (historical religious art) OR cosmic Hubble/JWST imagery | — |
| **A-vs-B contrast beats** ("like", "versus", "whereas") | **Always `TYPE:cycle:2`** — see Dichotomy pattern below | — |

## Forbidden Moves (anti-patterns from Ryan's critique)

1. **Satellite/aerial imagery for human-scale farm or labor work** — feels abstract and doesn't land with high-school viewers
2. **Topic-keyword matching without meaning matching** — e.g., a solar-system montage for "astronomy is about comets, planets, sun, moon" misses the pedagogical point
3. **More than 1 image per 30 seconds** — over-cutting; viewer can't absorb
4. **Modern telescope photos for "arranging the stars" / cataloging concept** — the concept is *information arrangement*, not equipment
5. **NASA deep-space image for "oldest of the sciences"** — this beat needs a historical engraving (Greek or medieval astronomers at work)
6. **Space imagery for etymology beats** — Greek word roots should be text-only, optionally paired with a period-appropriate historical illustration
7. **Cheesy stock-feel composites** — "family portrait of planets" clip-art aesthetic
8. **Pretty-but-irrelevant imagery** — a gorgeous Hubble deep-field does not automatically support whatever the narrator is saying
9. **Zodiac imagery leading a "calendar" beat** — a high-school viewer without archaeology/antiquities background reads the zodiac before the calendar, defeating the pedagogical point. Zodiac belongs in astrology-origins beats, not in calendar-marking-time beats.
10. **Posed portraits where a scientific artifact carries the point** (v2) — when Faulkner names an astronomical idea, structure, or catalog, a portrait of the astronomer is weaker than the artifact itself. Default to `TYPE:artifact` in that case.
11. **Single image on dichotomy beats** (v2) — when AUDIO sets up an A-vs-B contrast, a single image loses the argument. Always brief as `TYPE:cycle:2` with slot A + slot B.

## Text-Beat Signals (leave blank — NOT this skill's job)

These content types belong to the future text-handler agent. AVScriptEditor identifies them only to avoid briefing an image over them — the BRIEF cell stays empty for these rows so the text agent can fill them on its own pass.

- Greek or Latin word roots and translations
- Scripture citations (explicit book/chapter/verse)
- Vocabulary definitions being read aloud
- Lists of things where the list itself is the point (e.g., "light, signs, times, seasons" — a bullet build)
- Short definitional asides ("diurnal means...")

## Winning Patterns (from Ryan's review)

- **Atmospheric + literal**: ISS orbital sunrise with lens flare supporting "diurnal creatures / purpose of light" (I20) — the image *was* the concept, not just a topic illustration
- **Concept cycle**: for Day 4 "sun, moon, and stars," a short cycle — sun → moon → stars → back — beats a single composite
- **Period-correct historical art for historical claims**: engraving of Greek astronomers for "aster / nomos" etymology or "oldest of the sciences"
- **Atmospheric Earth imagery for "marking time" / orbital mechanics**: day/night terminator from space (I17 / I20 territory)
- **Pillars of Creation for cosmic-scale biblical language** (Day 2 "heavens") — iconic, evocative, not generic — *but see v1 refinement below: when historical imagery already leads into the beat, maintain that lane*
- **Historical-lane continuity across section transitions** (v1) — once a historical visual lane is established, preserve it for adjacent biblical/cosmic beats. Example: if the beats leading into "God created the heavens on day 2" are historical engravings of ancient astronomers, the Day-2 beat should stay in that lane (altarpiece, illuminated manuscript) rather than pivoting to a JWST nebula.
- **Subject + context pairing** (v1) — when a beat names both an astronomical object AND a specific geography (e.g., Sirius over Egypt), the brief must put both in frame so the viewer connects them. The object alone is insufficient.
- **Zodiac in astrology-origins beats, not calendar beats** (v1) — zodiac imagery reads as "astrology" to a high-school viewer. Use it where the instruction is about astrology's origins; keep it out of "calendar / marking time" beats (which need a calendar to read as a calendar first).
- **Artifact over portrait when the point is the work** (v2) — Bayer Uranometria, Kepler diagrams, Tycho mural-quadrant engraving beat a portrait of the astronomer when the audio is about *what they produced*.
- **Dichotomy as a cycle** (v2) — A-vs-B contrast beats ("disbelieving evolution is as bad as disbelieving gravity") need both sides on screen; single images consistently miss the argument.

## Losing Patterns (from Ryan's review — do not repeat)

- Milky Way airglow over Earth horizon for the *etymology* of "astronomy" (I3) — beautiful but off-topic; that beat needs a historical image or on-screen text
- Telescope equipment for "arranging the stars" concept (I5) — equipment ≠ cataloging
- Solar-system planet montage for "astronomy is about comets, planets, sun, moon" (I7, I10) — generic and cheesy
- Hubble deep-field for "oldest of the sciences" (I12) — pretty but needs a historical engraving
- Satellite farm image for "everybody worked on the farm" (I27) — need an artistic/historical pairing
- Equinox/solstice diagram for "track annual cycle to know when to plant" (I31) — the actual content in the next section is about Sirius + Nile flooding, not the equinoxes
- **Medieval illuminated manuscript where specific detail must read (ch01-1 r78 Breviari d'Amour, r130 Paris Psalter)** — decorative but illegible at HS speed. Use when the illumination IS the point (zodiac wheel, liturgical context); skip when a specific event or detail must be parsed.
- **Dark grayscale period painting for "19th-c. chemistry lab"** — a modern classroom with visible color + beakers beat the Wellcome oil paintings for HS readability. Readability > pedigree when the point is the *scene*, not the era.
- **Allegorical Renaissance painting where concept is literal** — Veronese's *Allegory of Navigation with an Astrolabe* reads as "ornate allegory" before "astrolabe"; use Holbein's *Ambassadors* (instruments on a table, clearly recognizable scholars) instead.

## Image Type Tags (used in briefs)

Every brief written by AVScriptEditor includes a `TYPE:` tag so downstream workflows know where to route for sourcing. Canonical tags:

| Tag | Meaning | Sourcer |
|-----|---------|---------|
| `science` | NASA/NOAA/USGS-style modern scientific imagery (photos, simulations, observatory plates) | FindScienceMedia |
| `artifact` | **Historical scientific artifacts** — star charts, celestial maps, astronomical diagrams, manuscript pages, period instruments. The *object of scientific work*, not *people doing it*. | FindArt (Bayer/Hevelius/Kepler/Flamsteed scans, BnF Gallica, Smithsonian instruments) + FindScienceMedia (historical NASA sky-chart reproductions) |
| `historical` | Engravings, woodcuts, paintings of **people** doing science / historical scenes / period portraits | FindArt |
| `art` | Fine art, illustration, non-historical artistic rendering | FindArt |
| `cycle:N` | Multi-image concept cycle (e.g., `cycle:3` = three images shown in quick succession) | varies — specify per-slot |
| `hold` | Intentionally reuse / hold prior image for this beat | (editor) |

Note: `TYPE:text` was removed in v1. Text-only beats get a blank BRIEF cell; the separate text-handler agent (future) will fill those.

### `artifact` vs `historical` — the distinction matters

The ch01-1 review surfaced this: many beats tagged `TYPE:historical` really wanted `TYPE:artifact`. The key question: **is the pedagogical point the people or the object?**

- "Astronomy is the oldest science. Astronomers have been arranging information about the sky for thousands of years." → pedagogical point is *the arranged information*. Brief as `TYPE:artifact` pointing at a Bayer Uranometria plate, a Ptolemaic zodiac diagram, a medieval star catalog page. NOT a painting of astronomers.
- "Galileo used his telescope to revolutionize our view of the heavens." → pedagogical point is *Galileo as a person doing science*. Brief as `TYPE:historical` pointing at a portrait / engraving of Galileo with his instrument.
- "Kepler worked out that orbits are ellipses." → either can work, but the *diagram* from Kepler's *Astronomia Nova* (artifact) is often stronger than a portrait of Kepler (historical).

Default to `artifact` when the instructor names a scientific idea, structure, or catalog. Default to `historical` when the instructor names a person, era, or cultural context.

## Brief Format (what goes in BRIEF column J)

```
TYPE:<tag> | <concrete visual description, 8-16 words> | <sourcing hint or specific subject keyword>
```

Optional annotation fields (see **Editorial Principles (v3)** below for usage):
- `WHY:` — one-sentence "why this, why now" rationale for hard beats
- `OR |` — alternative image, when multiple picks serve equally well
- `RHYMES-WITH: r<row>` / `SETS-UP: r<row>` / `CALLBACK-TO: r<row>` / `PAYS-OFF: r<row>` — cross-beat linkage annotations
- `FAIR-USE: <class> | <rationale>` — required on Tier 4 fair-use picks (see **Sourcing Location Hierarchy** below)

Examples:
```
TYPE:artifact | Bayer Uranometria plate showing an organized star catalog | FindArt: "Bayer Uranometria constellation plate"
TYPE:historical | 18th-c. engraving of Greek astronomers at work | FindArt: "ancient Greek astronomers engraving"
TYPE:science | Hubble/JWST nebula evoking cosmic creation | FindScienceMedia: "Pillars of Creation"
TYPE:cycle:3 | Sun → Moon → starfield, 2 sec each | slot 1: sun disk; slot 2: crescent moon; slot 3: starfield
TYPE:cycle:2 | Dichotomy — evolution (A) vs gravity (B) as ongoing sciences | slot 1: ape-to-man diagram (science); slot 2: LIGO or space-time curvature (science)
TYPE:hold | keep prior image on screen
```

---

# Editorial Principles (v3)

Teacher/editor moves that lift the brief-writer from row-local pattern-matcher toward narrative-aware editorial judgment. Principles are guidance, not mandates — when a section's structure doesn't support a principle (e.g., pure enumeration where no arc exists), don't force it.

## 1. Narrative arc (soft, multi-scale)

When a stretch of rows **traces a progression** — historical development, argument building, scaffold of an idea, introduce → define → example → implication — the brief sequence across that stretch should honor the arc. First image **orients**, middle images **build**, last image **resolves or pivots**.

Arcs exist at three scales. The brief-writer should look for whichever scale actually applies, not force the section-wide one.

### Sub-section / beat cluster (3–5 rows, ~30–60s)

The most reliable arc. A single point developed over a few adjacent rows: introduce concept → define term → example → implication. Happens in **technical content even when the section-level arc fails**. For technical chapters (ch03+), this is usually the right granularity.

**Detection signals:** local connectives in AUDIO — "first… second… finally," "let me explain… for example… so what this tells us," "on one hand… on the other," "and that's why," "so here's the thing."

### Section-level (5–15 briefed rows, 3–7 min)

AstronomyScript-assigned section boundary. Strong in historical / argumentative sections.

**Detection signal:** section's first data row and last data row describe **different times or different stages of an argument** → arc applies. If the section is pure enumeration (list of planets, properties, types), treat as parallel structure — **no arc**.

### Chapter-level (entire lecture)

Bookends: first section orients the whole lecture, last section resolves or pivots to the next lecture. This is where `PAYS-OFF:` and `CALLBACK-TO:` annotations earn their keep.

**Detection signal:** compare section headings taken in sequence — do they trace a progression?

### Worked examples

- **Section-level (ch01-1 "Oldest Science"):** Bayer Uranometria → Tycho at his quadrant → Wright of Derby *Orrery* traces *antiquity → early modern observation → Enlightenment demonstration*. A random reshuffling weakens the section even though the picks are unchanged.
- **Sub-section-level (hypothetical ch03 "Types of stars"):** the section enumerates star classes (no section-level arc), but within each class: a composition diagram (introduce) → an H-R diagram position (define) → a named exemplar photo (example) → a late-stage evolution image (implication). Four-beat sub-section arc.

### The "don't force it" clause

**Better to skip the arc than to force a phony one.** If neither sub-section nor section signals are present, treat the rows as parallel and brief them independently. Forcing a narrative on enumerated content produces worse briefs than acknowledging the enumeration.

**Workflow implication:** after writing briefs across a cluster or section, re-read the briefs **as a sequence** before committing. Do they honor a progression? If yes, good — reorder or rewrite to strengthen. If no (parallel / enumeration / single concept), move on without forcing.

## 2. Analogy vs identity

When AUDIO uses analogy-signaling language, the image is the **analogy**, not the literal referent.

**Signal phrases:** "like", "imagine", "think of it as", "similar to", "picture", "just as X, so Y", "it's kind of a…", "you can think of this as…"

**Worked examples:**
- "Gravity is like a ball on a rubber sheet" → image is the **rubber-sheet space-time diagram**, not a literal ball or Earth.
- "Astronomers are *arranging* information like librarians cataloging books" → image is a **librarian cataloging scene** or a **card-catalog grid**, not more astronomers.
- "The universe is *older* than we can imagine — if you compressed its age into one year, humans appear on December 31st" → image is a **calendar / cosmic-clock** visualization, not a human.

When the analogy is the point, `TYPE:artifact` for historical analogies or `TYPE:science` for modern visualizations. Rarely `TYPE:historical` — analogies aren't *about* people.

## 3. "Why this, why now?" — forcing-function question

Every brief must answer one sentence: **why this specific image at this specific beat?**

- ❌ Weak answer: "Because the AUDIO says the word 'star.'" (Keyword matching — rewrite.)
- ❌ Weak answer: "It's a pretty picture of the concept." (Generic illustration — rewrite.)
- ✅ Strong answer: "Rhymes with the Bayer plate at r7 and sets up Tycho's observational work in r11 — this beat is *about the growing catalog of celestial knowledge*, not just 'stars.'"
- ✅ Strong answer: "Faulkner is transitioning from scriptural authority (prior section) to natural observation (next section) — this image is the hinge; an illuminated manuscript with astronomy marginalia bridges both."

**Application:** the brief-writer should be able to articulate a "why now" answer for every image brief. For **hard beats** (pivots, dichotomies, analogies, section heads, test-concept flags), include the answer in the brief itself as an optional `WHY:` field.

If you can't write a "why now" sentence that goes past keyword-matching, the brief is weak — rewrite or mark the row as `TYPE:hold`.

## 4. Brief as hypothesis (OR alternatives)

When **multiple images could serve the same beat equally well**, list both with `OR`. Gives the sourcer room to pick by actual availability and quality.

Format:
```
TYPE:artifact | Bayer Uranometria plate — organized star catalog | FindArt: "Bayer Uranometria plate" | OR | Kepler Astronomia Nova diagram | FindArt: "Kepler Astronomia Nova figures"
```

**When to use alternatives:** both options carry the same meaning with equal pedagogical force; neither option has a clear tier advantage; the sourcer's judgment on "what's actually available at textbook quality" is better than the brief-writer's remote guess.

**When NOT to use alternatives:** one option is clearly stronger editorially (just pick it); the options have different meanings (that's two briefs, not one); on `TYPE:cycle:N` beats (use the cycle slots).

## 5. Cross-beat awareness (annotation layer)

Brief can carry optional linkage fields documenting editorial relationships between rows. No pipeline action required yet; these are **annotations for QC audit and future callback-aware logic**.

Supported fields:
- `RHYMES-WITH: r<row>` — this image is aesthetically/thematically paired with another beat's image
- `SETS-UP: r<row>` — this image prepares the viewer for a concept revealed later
- `CALLBACK-TO: r<row>` — this image intentionally echoes an earlier established image (motif reuse)
- `PAYS-OFF: r<row>` — this image resolves a scaffold started at an earlier row
- `FAIR-USE: <class-1|class-2|class-4> | <one-sentence rationale>` — declares Tier 4 fair-use invocation under a documented class. Required on all Tier 4 picks. See **Sourcing Location Hierarchy → Tier 4** below.
- `VERIFY: <what to verify>` — flags ambiguous filename patterns where Commons metadata can't be trusted (numbered files, plate numbers, folio refs, numeric IDs). QC reviewer eyeballs the file in Drive and clears the annotation. See **Sourcing Criteria → File-Content Verification** below.

Multiple annotations can stack: `RHYMES-WITH: r48 | SETS-UP: r130`. Cheap to write, compounding value for QC audit and future callback-aware sourcing.

---

# Sourcing Criteria (v2+)

These rules govern how an image is *picked*, not what concept is briefed. Enforced by FindScienceMedia / FindArt / any sourcer writing filenames + URLs into the sheet.

## Resolution & Format Floor

- **Width ≥ 2000px is the floor; 4000px+ width preferred for 4K-ready editing.** Width is what determines screen real estate at 16:9 timeline use — a 2400-tall portrait at 1500 wide fails this floor regardless of total pixel count. For sub-2000-width picks: only acceptable if the image is genuinely iconic and no higher-res exists (e.g., Robert Hannah's Newton-at-Woolsthorpe — 1200×880, literal Newton + apple 1665 and nothing else matches). Flag sub-floor picks.
- **No AI-upscaled reproductions.** They read as plasticky even at HS audience scale (Bertini Galileo fresco was rejected on this ground).
- **Videos (.webm, .mp4) are first-class.** NASA SVS, LIGO simulations, NASA SDO. Prefer the plain / unlabeled variant when multiple exist.

## Aspect Ratio for Video Editing

Landscape orientation (width > height) is preferred but historically often unavailable — many canonical paintings are vertical. When only a portrait pick exists, accept it; the editor frames ken-burns / partial-fill / 9:16-letterbox at edit time. NASA / observatory imagery is naturally 16:9 — default to landscape there. No explicit aspect annotation needed in the brief; the editor figures it out from looking at the file.

## Planar Reproduction Over Installation Photo

For paintings, manuscripts, and 2D artifacts, prefer **flat digital scans** (Google Art Project, Met Open Access, NGA, Rijksmuseum, BnF Gallica, museum digital archives) over **installation photos** taken at the museum. **Visible frames, perspective foreshortening, museum interior context, or angled reproductions = reject** and find the planar version.

Worked examples (recurring in v1+v5):
- Brueghel *The Harvesters* — the "with frame" / Met-installation photo gets rejected; the Google Art Project straight scan (`The_Harvesters.jpg` at `/wikipedia/commons/1/13/`) is the right pick.
- Dendera Zodiac Louvre wall photo (angled, rejected) → planar Description-de-l'Égypte-style reproduction (`Ancient Egypt Zodiac of Dendera (28306172802).jpg`, accepted).

## HS Legibility — the "2-second rule"

If a HS student wouldn't recognize what the image shows in 2 seconds, the pick fails. **Applies to `TYPE:historical`, `TYPE:artifact`, `TYPE:art`** — anything used as b-roll support for a concept Faulkner names but doesn't walk through.

**Exception — image-as-subject:** when AUDIO explicitly narrates the image's contents ("notice how X works… this part shows Y… here you can see…"), the legibility rule relaxes. Faulkner is doing the explaining; complex diagrams hold up because the voiceover is the reader. Future canonical example: ch04+ Hertzsprung-Russell diagram, where Faulkner spends minutes walking through stellar evolution — the H-R diagram is unintelligible to most HS viewers cold but works because Faulkner narrates it.

**Heuristic to apply at sourcing time:** scan AUDIO for the next ~30 seconds after the image appears. If the AUDIO explicitly describes parts of the image, legibility is relaxed. If the AUDIO names a concept and moves on, legibility is enforced.

Common 2-second-rule rejections from v1+v5: Veronese *Allegory of Navigation with Astrolabe* (allegorical figures don't read as astronomy), Hevelius *Tabula Selenographica* (lunar map mistakenly looks like an abstract circle), AI-upscaled Bertini fresco, small medieval illuminations where details don't read at TV size, alchemy 1922 stippled engraving.

**Readability over pedigree.** A dark grayscale Wellcome alchemist oil painting reads worse to HS students than a modern photo of a chemistry classroom. The historical nature is secondary; the point is the viewer understanding what's being shown.

## Default to 3 OR Alternatives for Non-Science Picks

Single picks for `TYPE:art`, `TYPE:historical`, `TYPE:artifact` are the wrong default — art availability is variable, museum scan quality varies, and the editor benefits from picking based on actual file content. **Default to 3 OR alternatives** for these tags. The sourcing JSON uses the cycle `filenames`/`source_urls` list pattern; the editor selects one in FCP.

**Single picks are fine for `TYPE:science`** — when NASA Pillars or NASA SVS Moon Phase 2026 plain webm is the canonical answer, one pick is right.

**Cycles (`TYPE:cycle:N`) opt out** of the 3-options rule — those are conceptually deterministic (Day-4 sun → moon → stars). One canonical asset per slot. If a cycle slot turns out wrong, Ryan flags it specifically and we swap that slot.

## Honor cycle:N counts when sourcing (procedural)

When a brief says `TYPE:cycle:2`, source **2** alternates — not 1. Sourcing fewer slots than the cycle calls for forces a re-source round. If a slot can't be cleanly filled (e.g., one half is fair-use with no PD equivalent), surface that explicitly in the license field rather than silently delivering a single. The cycle count is a contract from the brief; treat it as such.

## Color over B&W when the subject is in living memory

For 20th–21st-century subjects (working scientists, recent events, modern instruments), prefer color even at cost of resolution. B&W reads as "historical" and breaks the modern-relevance beat — Sagan in B&W lands wrong because the audience knows him as a TV-era figure. **Pre-photographic and early-photo subjects (Huxley 1863 frontispiece, Newton's apple tree, Renaissance prints) read fine in monochrome** — period-appropriate. The split is roughly: post-1950 subject → push for color; pre-1900 subject → monochrome neutral.

## Query Tier 0 (CCmini) first for Christian / religious art

CCmini's painting gallery has dense coverage of Christ-in-landscape, Brueghel/Perugino/Saftleven baptism scenes, Cranach religious works, and other classical/romantic Christian imagery that Wikimedia under-serves at hi-res. Default order for `TYPE:art` with Christian subject matter: **CCmini FTS query → Wikimedia → Tier 2 museums.** Querying CCmini early routinely saves a swap round on this audience's content.

## "Show the experiment" — close enough to read

For `TYPE:science` beats illustrating a specific demo or apparatus, the action must read in 2 seconds. Wide-context shots that include the demonstration but bury it in environment fail (Apollo 15 hammer/feather wide shot — viewer can't tell what's falling). The experiment IS the subject; frame it that way. **Sub-floor strobe/close-up shots that clearly show the demo are preferable to hi-res wide shots that bury it** (image-as-subject exception per resolution rule).

## Observatory shots need the observatory in frame

For "professional observatory at night" beats, the observatory dome / telescope must be visibly in frame. Distant summit panoramas with no visible domes (Mauna Kea summit panorama from afar) read as "starry sky" not "observatory." Prefer ESO Paranal/La Silla/Mauna Kea shots **with telescopes clearly silhouetted or featured**, even at lower resolution than a pure-skyscape panorama.

## File-Content Verification (`VERIFY:` Annotation)

Commons file descriptions are sometimes misleading — a numbered file ("Giotto di Bondone 006.jpg") may not actually be the panel its title claims. When the source URL has an **ambiguous filename pattern** (numbered without explicit subject; "Plate XXIV"; "Folio 74r"; numeric IDs like "26358"), append a **`VERIFY:`** annotation to the brief in column J:

```
... | VERIFY: file content vs Wikipedia article on <work-title>
```

The QC reviewer (Ryan / Hannah) eyeballs the downloaded file in Drive, confirms it matches the brief's intended subject, and clears the VERIFY by removing the annotation. Failed verifications trigger a re-source. Files with explicit subject names (`Tissot The Exodus.jpg`, `Pieter Bruegel - The Harvesters - Google Art Project.jpg`) don't need VERIFY — the filename itself is the verification.

## Fair Use for Commentary on a Named Person or Place (v1; generalized in v4 — see Tier 4)

When the script is **commenting on a specific person or place** (discussing their ideas, career, legacy, or a specific site's significance), fair-use doctrine lets us run their image even if it's not formally PD/CC. v4 widened this to the full Documentary Filmmakers' Best Practices framework — see **Tier 4 — Fair Use** in the Sourcing Location Hierarchy below.

## Tone & Content Calibration (HS Classical Christian Audience)

- **No graphic violence.** Goya's *Saturn Devouring His Son* is iconic but disqualified — too dark for the homeschool context even in an astrology/pagan-mythology beat.
- **No gratuitous nudity.** Canonical nude Renaissance works (Botticelli *Birth of Venus*, Ingres *Jupiter and Antiope* seduction scenes, Goltzius *Mercury*) are rejected even when they fit the brief thematically. Classical sculpture nudity is case-by-case; lean restrained.
- **Biblical scenes: prefer narratively clear 19th-c. academic or High Renaissance over graphic medieval.** Tissot OT watercolors are the ideal (but see manual-source note — they don't exist at usable res on Commons). Good substitutes: Gustave Doré's 1866 Bible engravings, Cranach *Christ Blessing the Children*, Leonardo *Last Supper*.
- **Passion / crucifixion imagery**: prefer Italian Renaissance (Mantegna, Raphael) to graphic Northern works (Grünewald's Isenheim Altar is too raw/bloody for this audience).

## Subject-Specific Preferences (ch01-1 lessons)

| Brief subject | Good pattern | Avoid |
|---|---|---|
| Ancient astronomer (person-focused) | `TYPE:historical` — Tycho at his mural quadrant, Hevelius + Elisabetha at sextant, Raphael *School of Athens*, Wright of Derby *Orrery* | Posed portraits without instruments, pure astrolabe-object photos, allegorical works (Veronese *Allegory of Navigation*) |
| "Arranging information" / astronomical catalogs / idea of astronomy as organized science | **`TYPE:artifact`** — Bayer *Uranometria* plates, Hevelius *Firmamentum* charts, Kepler *Astronomia Nova* diagrams, Flamsteed atlas plates, Cellarius zodiac plates, Ptolemaic diagrams, medieval celestial manuscripts | Portraits of astronomers when the point is the *work* not the *worker* |
| Historical science in action | Mary Anning at Lyme Regis, dinosaur excavation photos, Teniers/Wright alchemists, Faraday at Royal Institution, Liebig's Giessen lab | Bertillon mugshot grids (read as "two portraits"), heavily-cluttered 19th-c. lab engravings |
| Chemistry lab | Modern classroom with visible glassware + color (Baldwin Academy Chemistry Lab), chemical-garden reaction close-up, scientist pouring blue liquid | Dark period paintings where the beakers blend into shadow |
| Seasonal / time-of-year | Literal pastoral with season legible — Brueghel *Harvesters*, Millet *Gleaners* / *Sower*, Alma-Tadema *Spring* | Almanac cover pages (too text-heavy), abstract calendar art |
| Star map / zodiac | Bayer Uranometria plates, Flamsteed atlas, Sidney Hall *Urania's Mirror* cards | Small medieval illumination zodiacs (Breviari d'Amour is readable but <2000px; keep only if nothing better exists) |
| Cosmic-scale beat | Hubble Pillars of Creation, Hubble Ultra Deep Field, IllustrisTNG cosmic web simulation | Random Hubble "pretty picture" without iconic recognition value |
| Biblical illuminated manuscript | Drop when possible — HS students don't parse medieval illumination at speed. Move to text-agent territory (leave blank) or `TYPE:hold` | Forli Siddur, Paris Psalter, generic illuminated pages |
| Observatory dome | ESO La Silla / Kitt Peak / Mauna Kea night shots with domes visible + stars | Daytime dome shots, empty observatory interiors |

## Repeat-Avoidance (Used-Image Registry)

**Rule:** Don't reuse the same image within a chapter set of lectures unless the lecturer explicitly calls out the same reference twice.

**Registry file:** `~/.claude/skills/avscripteditor/registry/astronomy-faulkner-used.json`

Canonical per-course ledger recording every sourced FILE NAME + URL across every lecture, exploded per slot for cycle entries. Bootstrap from sheet state with `scripts/backfill_registry.py`; query with `scripts/check_registry.py`; auto-updated by `apply_sourcing.py` on every successful run.

**Usage in the sourcing workflow:** before finalizing a pick, run
```bash
python3 scripts/check_registry.py --course-slug astronomy-faulkner --url "<candidate-url>"
```
Exit 0 = already used; exit 1 = clean; exit 2 = no registry.

## Manual-Source hints

When no suitable PD/CC imagery exists (e.g., Catastrophic Plate Tectonics diagrams owned by AiG/ICR, personal photos of the instructor), and the pick can't be claimed as Tier 4 fair use, carry a `MANUAL-SOURCE:` hint in the brief itself so the sourcer drops a placeholder and flags the row for human follow-up. **Do not write editorial NOTE markers to column F** — that column is reserved for human editor markers that flow downstream to Final Cut as timeline annotations. The manual-source flag lives in the brief (column J) where the sourcer can act on it.

---

# Sourcing Location Hierarchy

Prefer higher tiers when a valid match exists. Only drop to lower tiers when the beat genuinely requires it.

## Tier 0 — Compass local galleries (GalleryQuery)

**The first place to look.** Pre-cleared PD imagery curated by Compass and hosted on-prem (`10.1.10.198`). Zero licensing friction, fastest round-trip (sub-second FTS, ~10ms CLIP), and the content has already been vetted for our use — no per-item verification needed at pick time.

Query via the `GalleryQuery` skill (`bens-skills/GalleryQuery/Tools/gallery_query.py`). Three modes: `fts` (known terms / artist names / iconographic categories), `clip` (natural-language visual briefs), `sql` (structured filters like year ranges, color palettes, medium). See `GalleryQuery/SKILL.md` for the full output contract.

**Registered galleries:**

| Name | Enabled | Content | Best for |
|------|---------|---------|----------|
| `paintings` | ✅ | 40,936 classical paintings, CLIP + FTS5 searchable, 100% AI-tagged (style/medium/colors/mood/description) | `TYPE:historical` biblical scenes, `TYPE:art` academic paintings, `TYPE:historical` portraits, allegorical works. Strong for Renaissance / Baroque / 19th-c. coverage. |
| `science` | ❌ (future, ~4,000 curated PD images) | scientific imagery | Will cover much of `TYPE:science` and `TYPE:artifact` demand when it comes online. Query returns exit-4 while offline — sourcer silently moves on. |

**Which mode to pick:**

- **Brief names a specific subject, artist, or iconographic category** ("Annunciation", "Millet", "Passover seder") → `fts` first.
- **Brief is a vibe / visual description** ("tense biblical scene, warm palette", "reverent altarpiece depicting creation", "19th-c. pastoral with farmers in sunlight") → `clip` first.
- **Brief has structured constraints** (year ≤ 1700, specific medium, palette intersection) → `sql`.

The two cheap modes (fts + clip) can both be tried without a meaningful cost penalty.

**When to invoke Tier 0:**

- Default first probe for `TYPE:art`, `TYPE:historical`, and (once the science gallery is online) `TYPE:artifact` + `TYPE:science` beats.
- Any beat where a curated classical painting might land — Tier 0 has already done the licensing work, and the catalog size (40k+ paintings) is larger than any single museum we'd hit in Tier 1.

**When to skip Tier 0:**

- Brief is purpose-specific to a known external asset (e.g., "Bayer Uranometria plate 49" — that's Tier 1 Commons territory, not Tier 0).
- Brief needs NASA / Hubble / JWST / ESO imagery — those are purpose-built Tier 1 sources. Don't round-trip to a local gallery first.
- Brief is for very recent content (post-ingest cutoff). Empty result will waste the round-trip.

**Fallback behavior:**

Tier 0 misses are **silent** — no brief annotation, no `NOTE:` flag, no visible trace. A non-zero exit code (unreachable, bad input, disabled gallery) or an empty result array means "this beat wasn't in the local catalog," and the sourcer moves directly to Tier 1. Tier 0 is a speculative pre-check, not a committed tier.

**Sanity check before a sourcing run:**

```bash
python3 GalleryQuery/Tools/gallery_query.py health --gallery paintings
```

If exit 0 and all four services (`datasette`, `clip_health`, `clip_ready`, `images`) report `ok: true`, the gallery is live. If unreachable from your network (e.g., working off-site), Tier 0 is silently skipped — no editorial impact, just less catalog coverage.

## Tier 1 — PD, scrapable via Commons API

NASA Image & Video Library, APOD, Hubble, JWST (MAST), NOAA, USGS, NASA Earth Observatory, NASA SVS. Wikimedia Commons PD scans (Yorck Project, Google Art Project, NGA, Met Open Access, Rijksmuseum, Mauritshuis, BnF Gallica, British Library, Library of Congress).

## Tier 2 — CC BY, scrapable

Wellcome Collection, ESO, Biodiversity Heritage Library, Europeana, NASA ISS Expedition photo releases (frequently PD-USGov-NASA, occasionally CC). Cleveland Museum of Art, Paris Musées.

## Tier 3 — CC BY-SA, acceptable with attribution

Individual Commons photographers (Giles Laurent for Milky Way work, Uroš Novina for twilight sky), observatory astrophotography. Acceptable but requires LICENSE line with attribution.

## Tier 4 — Fair Use (copyrighted material, transformatively quoted)

Per the *Documentary Filmmakers' Statement of Best Practices in Fair Use* (Center for Social Media / American University, 2005), educational documentary work has standing to quote copyrighted material under three of the four documented classes. Compass Classroom is an identified educational publisher making transformative, bounded use — the four-factor test favors us.

**The three applicable classes:**

- **Class #1 — Critique.** Copyrighted material used as the *object* of commentary. Faulkner critiquing Sagan's naturalism → editorial Sagan portraits. Faulkner discussing evolution as a rival worldview → contemporary evolutionary-biology imagery. Faulkner commenting on alchemy/phlogiston → illustrations of those ideas being critiqued.
- **Class #2 — Illustration.** Copyrighted material quoted to illustrate an argument Faulkner is developing. **The broadest and most useful class.** Opens: publisher textbook figures (HR diagrams, space-time curvature, ape-to-man), editorial photography, modern science visualizations, YouTube/PBS/Veritasium frames when quoting established explainer styles.
- **Class #4 — Historical sequence.** Irreplaceable archival material for historical context when licensing is unavailable or prohibitive. Opens: Getty Images editorial archive, Life / National Geographic archives, Bettmann/Corbis historic photos, AiG/ICR proprietary YEC diagrams (Catastrophic Plate Tectonics, flood geology).

Class #3 (incidental capture) does not apply — we're not shooting verité.

**Decision order (when to invoke fair use):**

1. Tier 1–3 search completed, no PD/CC equivalent at textbook quality → proceed
2. Identify the class: object of critique → #1; illustrating an argument → #2; irreplaceable historical material → #4.
3. Pass the transformativeness test: is our use for a *different purpose* than the original? (Educational illustration vs. original commercial/news/marketing use → yes.)
4. Pass the amount test: we use the whole image but only for the 10-second beat. Bounded. OK.
5. Pass the "range of sources" test: if we're about to lean disproportionately on one publisher/photographer, diversify.
6. Annotate the brief: **`FAIR-USE: <class> | <one-sentence rationale>`**.
7. License string identifies the source as fully as possible: publisher, photographer, archive, original publication date.
8. Production-side: fair-use items get **prominent credit** in the lecture's end credits (not just metadata).

**Limitations enforced per class:**

- All classes: proper attribution; amount ≤ what's needed to make the point; not used merely to avoid the cost of shooting equivalent footage.
- Class #2 specifically: quotations drawn from a **range of sources** across a lecture; no single publisher/photographer dominates.
- Class #4 specifically: the project is not designed around the copyrighted material; the material has a critical illustrative function with no suitable substitute; licensing genuinely unavailable or prohibitive relative to a reasonable budget.

## Tier 5 — Manual download only (scrape-blocked, JS-rendered, or licensed)

**Last resort.** Requires human-in-the-loop effort, so it should only be invoked when no Tier 1–4 path works. Jewish Museum NYC collection (Tissot OT series hi-res), WikiArt (anti-scrape), Google Arts & Culture (when the originating museum isn't an API partner). Plan: user acquires manually in a browser, drops the file into the local media folder, sourcer writes FILE NAME/URL manually or flags with `MANUAL-SOURCE:` in the brief.

## Archive.org as a cross-cutting source (Tier 1/2/3/4 depending on item license)

Internet Archive hosts substantial collections relevant to our workflow. Per-item licenses vary — the sourcer reads the `licenseurl` metadata field and places the item in the appropriate tier:

- **NASA HQ press photography** (`nasahqphoto-*` identifiers) — PD US gov works → **Tier 1**
- **Prelinger Archives** — ephemeral / educational / historical film, mostly CC0 → **Tier 1/2**
- **19th–20th c. astronomy book scans** (Flammarion, Proctor, Humboldt, etc.) — often PD by age, high-quality figure plates extractable → **Tier 1** for `TYPE:artifact` beats (goldmine for historical scientific artifacts not on Commons)
- **Smithsonian contributed items** — typically CC0 → **Tier 1**
- **Everything with `licenseurl` starting `creativecommons.org/publicdomain/zero/`** → **Tier 1**
- **`creativecommons.org/licenses/by/`** → **Tier 2**
- **`creativecommons.org/licenses/by-sa/`** → **Tier 3**
- **No license tag or explicit copyright** → evaluate under **Tier 4 fair use** with class + rationale

**API probe pattern:** `curl "https://archive.org/advancedsearch.php?q=<query>&fl[]=identifier&fl[]=title&fl[]=licenseurl&fl[]=mediatype&rows=<N>&output=json"`. Returns `licenseurl` for license-tier classification. Items fetch via `https://archive.org/download/<identifier>/<filename>`.

## Technical Sourcing Rules

- **Verify URLs via the Commons API. Never construct paths by hash guess.** `curl -sS "https://commons.wikimedia.org/w/api.php?action=query&titles=File:<URLencoded>&prop=imageinfo&iiprop=url|size&format=json"` returns the canonical upload.wikimedia.org URL. Claude will hallucinate the hash-prefix folder (`4/42/` vs `8/85/`); the API won't.
- **Use a browser User-Agent** for downloads from upload.wikimedia.org. Wikimedia aggressively rate-limits UA strings that read like scrapers (`Mozilla/5.0 (Macintosh; Intel Mac OS X 14) AppleWebKit/605 Safari/17` works).
- **Rate-limit handling**: if a single URL returns repeated 429 with cache-id `0c640b1`, the edge node has blacklisted that path for the session. Fall back to manual `curl` (often hits a different edge) or skip and re-run later.
- **Fetch originals**: `~orig.jpg` for NASA, full-res upload.wikimedia.org for Commons. Don't fetch `/thumb/`.
- **NASA SVS variant hunting**: annual releases (e.g., "Moon Phase and Libration 2026" SVS5587) publish fancy (with labels), plain (no labels), north-up / south-up, horizontal 2160p / vertical 1920p variants. Pull the horizontal plain 2160p by default.

---

## Profile Evolution Log

- **v0 (2026-04-20)** — Initial seed from Ryan Stufflebeam's review of Chapter 1 test (first 2 min, sheet `<REDACTED-TEST-SHEET-ID>`). All forbidden moves + winning/losing patterns derive from that review.
- **v1 (2026-04-21)** — Incorporated Ryan's row-by-row critique of the full BriefOnly dry run (`Feedback/Ryans-Feedback-2026-04-21-1016.md`). Added 3 winning patterns (historical-lane continuity, subject + context pairing, zodiac-placement rule) and 1 forbidden move (zodiac leading a calendar beat). Density target intentionally unchanged — Ryan noted the over-coverage was tolerable and he wants more options in practice; revisit scheduled after a second pass (tracked in `ROADMAP.md`). Two architectural blockers from the same review were addressed in separate commits: BRIEF column (commit d69b6eb) and image-only scope narrowing (commit b70c300).
- **v2 (2026-04-24)** — ch01-1 FCP-timeline review. Scientific beats landed; historical beats miscategorized as fine-art when the pedagogical point was the scientific *object* (star charts, diagrams, catalogs). Dichotomy beats (evolution-vs-gravity) briefed as single images when the contrast itself was the point. Added: **`TYPE:artifact`** as a fourth primary tag (scientific artifacts: star charts, celestial maps, astronomical diagrams, manuscript pages, period instruments). Added: **Dichotomy / comparison pattern** — always `TYPE:cycle:2` for A-vs-B beats. Added: **Read-ahead rule** — brief-writer reads next ~3 rows of AUDIO before committing, defaults to section-at-a-time walk. Two new Forbidden Moves (#10 portraits where artifact carries the point, #11 single image on dichotomy beats). New winning pattern (artifact-over-portrait, dichotomy-as-cycle). Subject-Specific Preferences matrix to codify the ch01-1 misses.
- **v3 (2026-04-24)** — Editorial-principles conversation after the v2 fixes. Added five teacher/editor principles as a first-class section: (1) **narrative arc** (soft, multi-scale — sub-section / section / chapter; sub-section arcs are often the right granularity for technical content where section arcs fail); (2) **analogy vs identity** (analogy-signaling language means the image is the metaphor, not the referent); (3) **"Why this, why now?" forcing question** with optional `WHY:` brief field; (4) **brief-as-hypothesis `OR` alternatives** when multiple images serve equally well; (5) **cross-beat annotation layer** (`RHYMES-WITH:`, `SETS-UP:`, `CALLBACK-TO:`, `PAYS-OFF:`). Principles are guidance, not rigid; `TYPE:speaker` and course-level visual lexicon were considered and explicitly deferred.
- **v6 (2026-04-26)** — Codified the v1+v5 sourcing-pattern lessons after pattern-matching on recurring back-and-forths. Six concrete sourcing rules, all in the **Sourcing Criteria** section: (1) **Width-based 2000px floor** (not long-edge), 4000px+ width preferred for 4K-ready editing — accounts for portrait paintings whose total pixels are large but whose width is too narrow for 16:9 timelines. (2) **Aspect ratio guidance** — landscape preferred when available, portrait acceptable when only option (editor frames at edit time); no explicit annotation needed. (3) **Planar reproduction over installation photo** — visible frames, perspective foreshortening, museum interior context = reject; find the Google Art Project / museum digital archive scan. (4) **HS "2-second rule"** for legibility on `TYPE:historical/artifact/art` picks — if a HS student wouldn't recognize what the image shows in 2 seconds, the pick fails. **Image-as-subject exception** when AUDIO narrates the image (e.g., future Hertzsprung-Russell diagram walks where Faulkner spends minutes explaining stellar evolution). Heuristic: scan AUDIO for next ~30s after the image appears. (5) **Default to 3 OR alternatives** for `TYPE:art/historical/artifact` picks — single picks are the wrong default, art availability is variable. `TYPE:science` stays single (canonical NASA imagery is deterministic). `TYPE:cycle:N` opts out — one canonical asset per slot, swap if Ryan flags. (6) **`VERIFY:` annotation** in BRIEFS for ambiguous filename patterns (numbered files, "Plate XXIV", folio refs, numeric IDs) — QC reviewer eyeballs in Drive and clears. Catches the v5 Giotto-di-Bondone-006 mislabeling pattern.
- **v5 (2026-04-24)** — Added **Tier 0 — Compass local galleries (GalleryQuery)** at the top of the Sourcing Location Hierarchy. Points at Ben's new `GalleryQuery` skill (`bens-skills/GalleryQuery`), a thin HTTP adapter over the on-prem paintings catalog on ccmini (40,936 classical paintings, CLIP + FTS5 + SQL) and the future science gallery (~4,000 curated images, offline until endpoints stabilize). Pre-cleared PD license posture — zero per-item verification needed. Tier 0 is the default first probe for `TYPE:art` and `TYPE:historical` beats (and will be for `TYPE:science` / `TYPE:artifact` once the science gallery comes online). Misses are silent — non-zero exit or empty result means "move to Tier 1," no brief annotation, no `NOTE:` flag. Sourcer should still skip Tier 0 for purpose-specific external assets (Bayer Uranometria, Commons-specific works) and for NASA / Hubble / JWST / ESO imagery where Tier 1 is purpose-built.
- **v4 (2026-04-24)** — Adopted **full Documentary Filmmakers' Best Practices in Fair Use** (Center for Social Media, 2005) as **Tier 4** in the Sourcing Location Hierarchy. Three applicable classes: #1 critique, #2 illustration (broadest / most useful), #4 historical sequence. Added the `FAIR-USE: <class> | <rationale>` brief annotation as mandatory for Tier 4 picks. Added **archive.org** as a cross-cutting source (Tier 1/2/3/4 depending on per-item `licenseurl`) — specifically notable for 19th–20th c. astronomy book scans (goldmine for `TYPE:artifact`), NASA HQ press photography, Prelinger Archives. **Manual-download moved to Tier 5 (last resort)** from v1's implicit "tier 4" position — manual sourcing requires human-in-the-loop effort, so it should only be invoked when all scrapable/fair-use paths have been exhausted. Formalized the Sourcing Location Hierarchy as its own top-level section. Codified the per-course used-image registry (referenced earlier, now load-bearing) and technical sourcing rules (Commons API verification, browser UA, rate-limit handling, NASA SVS variant hunting).
