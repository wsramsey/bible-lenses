# Bible Lenses — An Open Knowledge Graph of Christianity

**1,170+ interconnected notes spanning 2,000 years of Christian history, theology, art, and thought.**

A free, open-source Obsidian vault designed to be navigated, forked, expanded, and used by anyone who wants to understand Christianity deeply — its history, its thinkers, its art, its failures, and its future.

---

## What's Inside

| Folder | Contents | Count |
|--------|----------|-------|
| `Scholars/` | Theologians, philosophers, mystics — from Origen to Girard | 522 notes |
| `History/` | Church events across 20 eras, world context notes | 55 notes |
| `BibleFigures/` | Adam, Moses, David, Jesus, Paul and more with full context | 12 notes |
| `Figures/` | Historical shapers — Constantine, Plato, Charlemagne | 23 notes |
| `Fruit/` | What Christianity produced: hospitals, abolition, the Crusades, sex abuse | 24 notes |
| `Issues/` | Every major debate: homosexuality, inerrancy, predestination, war | 20 notes |
| `Movements-Events/` | Monasticism, Pietism, Pentecostalism, Liberation Theology | 12 notes |
| `Wars/` | Every major conflict involving Christianity, honest and documented | 18 notes |
| `Arts/` | Paintings, cathedrals, music, literature as theology | 37 notes |
| `Monuments/` | Cathedrals, monasteries, holy sites, biblical archaeology | 18 notes |
| `AncientReligions/` | Mesopotamia, Egypt, Canaan, Persia — the world Israel was born into | 13 notes |
| `Statistics/` | Demographic data, Pew/Barna/PRRI research, global trends | 7 notes |
| `Education/` | Seminaries, universities, missionary history | 11 notes |
| `Papacy/` | All 264 Catholic popes + Orthodox patriarchs of all 4 ancient sees | 292 notes |
| `Gaps/` | Eastern Church, women in history, heresies as serious theology | 16 notes |
| `App-Spec/` | Product spec for a navigable knowledge graph app | 7 notes |
| `Episodes/` | 63-episode documentary series framework + full production bible | 32 notes |

---

## The Design Principles

**1. Honest, not devotional.** The rotten fruit folder doesn't pull punches — Crusades, Inquisition, sex abuse, antisemitism. Good scholarship requires seeing the full picture.

**2. Cross-tradition.** Catholic, Orthodox, Protestant, Evangelical, Pentecostal — all traditions represented fairly, on their own terms.

**3. Connected.** Every note has a `connections:` field linking it to related nodes. The vault is a knowledge *graph*, not a collection of isolated articles.

**4. Primary source grounded.** Where possible, notes include actual quotes from the thinkers themselves. There are 578MB of primary source transcripts in the companion data repository.

**5. Art as theology.** Every note has an `artwork:` field pointing to a real painting, sculpture, or artifact in a named museum with a catalog number. The visual tradition is taken seriously as a theological source.

---

## How to Use This

### In Obsidian
1. Download or clone this repository
2. Open Obsidian → "Open folder as vault" → select the cloned folder
3. Enable the Graph View plugin
4. Open Graph View — you'll see 1,100+ nodes and their connections
5. Navigate freely or use the search

**Recommended plugins:**
- Graph View (built-in) — see all connections
- Dataview — query the structured frontmatter
- Canvas — build visual maps from the notes

### As a Research Tool
Every note has structured frontmatter you can query with Dataview:
```dataview
TABLE years, tradition, weight
FROM "Scholars"
WHERE tradition = "Eastern Orthodox"
SORT weight DESC
```

### As a Starting Point for Building
The `App-Spec/` folder contains a complete product specification for building a navigable knowledge graph app using Cosmograph and the existing JSON export. Everything is free and open source.

---

## The Frontmatter Schema

Every scholar note follows this schema:
```yaml
name: "Augustine of Hippo"
years: "354–430"
tradition: "Catholic"
branch: "Patristic Theology"
denomination: "North African Christianity"
hermeneutical_lenses: ["Allegorical", "Typological"]
interpretive_center: "Grace and the Restless Heart"
weight: 15          # 1–15, significance/influence
zoom_level: 3       # 1–5, at what zoom level to display
wiki: "https://en.wikipedia.org/wiki/Augustine_of_Hippo"
artwork:
  title: "Saint Augustine"
  artist: "Philippe de Champaigne"
  date: "1645–1650"
  museum: "LACMA"
  catalog: "M.78.15"
connections: ["[[Council of Nicaea (325)]]", "[[Pelagian Controversy]]"]
tags: [scholar, patristic, catholic, grace, north-africa]
```

---

## Contributing

This vault is designed to be forked and extended. Some directions:

- **Add missing scholars** — 522 is a start, not a finish
- **Deepen existing notes** — add more primary source quotes, more connections
- **Add more Bible figures** — only 12 are detailed; hundreds more to go
- **Correct errors** — primary source citations, dates, museum catalog numbers
- **Add non-Western perspectives** — the vault skews Western; this needs correcting
- **Translate** — the structure works in any language

**Pull requests welcome.** No theological gatekeeping — the vault represents all traditions.

---

## The Companion Data

Primary source transcripts (578MB of text from public domain sources) are available separately — they're too large for a standard repository but are documented in `Education/Missions/` and can be regenerated using the fetch scripts in the companion repository.

---

## License

**Creative Commons Attribution 4.0 International (CC BY 4.0)**

Use it, fork it, build on it, sell products built on it — just attribute the source.

The goal is for this to be useful to as many people as possible. That means as few restrictions as possible.

---

## Built With

This vault was built using:
- Obsidian (note-taking and graph visualization)
- Python scripts for bulk generation
- Public domain sources: Project Gutenberg, CCEL, Internet Archive, Wikipedia
- YouTube caption API for lecture transcripts
- Wikipedia REST API for portrait images

No paid APIs were used in building the vault itself. Everything is reproducible for free.

---

*"The aim of Christian thought is not to provide answers but to deepen the questions." — adapted from Rilke*
