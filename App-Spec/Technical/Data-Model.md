---
title: "Data Model — How the Vault Becomes the App"
type: "Technical Specification"
tags: [technical, data-model, frontmatter, graph, database]
---

# Data Model — How the Vault Becomes the App

## The Obsidian Vault IS the Database

Every `.md` file in the vault becomes a node. The frontmatter is the structured data. The `[[wikilinks]]` are the edges.

**No separate database needed at first.** The vault structure *is* the graph.

## Frontmatter → Node Data

Every note's frontmatter maps directly to the app's node display:

```yaml
---
name: "Augustine of Hippo"          # → Node title
years: "354–430"                     # → Dates display
tradition: "Catholic"                # → Tradition tag
era: "Patristic"                     # → Era tag + timeline position
weight: 15                           # → Node size in graph
zoom_level: 3                        # → Visibility at different zoom levels
artwork:
  title: "Saint Augustine"           # → Painting overlay
  artist: "Philippe de Champaigne"
  museum: "LACMA"
  catalog: "M.78.15"
image: "Assets/Images/augustine-of-hippo.jpg"  # → Portrait
connections: [...]                   # → Typed edge list
tags: [scholar, patristic, catholic] # → Filter categories
---
```

## The Edge Types (from wikilinks)

The current vault uses `[[wikilinks]]` for connections. For the app, we need typed edges.

**Phase 1 (now)**: Extract all `[[wikilinks]]` → untyped graph
**Phase 2**: Add edge types via frontmatter `connections:` field
**Phase 3**: Auto-suggest edge types from content analysis

### Connection Typing System
Add to frontmatter:
```yaml
connections:
  - node: "[[Council of Nicaea (325)]]"
    type: "historical"
    direction: "outbound"
    label: "Present at / shaped by"
  - node: "[[Pelagius]]"
    type: "conflict"
    direction: "bidirectional"
    label: "Theological opponent"
  - node: "[[Thomas Aquinas]]"
    type: "influence"
    direction: "outbound"
    label: "Major influence on"
```

## The Primary Sources Layer

For each node with transcript data at `~/bible-lenses-content/transcripts/[slug]/`:

```yaml
primary_sources:
  - file: "augustine/Confessions.txt"
    type: "primary"
    quote: "Thou madest us for Thyself..."
    location: "Book 1, Chapter 1"
  - file: "augustine/wikipedia.txt"
    type: "secondary"
  - file: "augustine/yt_sermon_1.txt"
    type: "audio_transcript"
```

The app uses these for:
- The `Q` key quote display
- Semantic search results
- The "Deep Dive" mode reading list

## The Artwork Layer

```yaml
artwork:
  title: "Saint Augustine"
  artist: "Philippe de Champaigne"
  date: "1645–1650"
  museum: "LACMA"
  catalog: "M.78.15"
  url: "https://collections.lacma.org/node/245037"
  image_local: "Assets/Images/augustine-of-hippo.jpg"
  zones:                    # For navigable painting areas
    - area: "face"
      connects_to: "[[Augustine — Conversion]]"
    - area: "book"
      connects_to: "[[The Confessions]]"
```

## The Timeline Layer

```yaml
timeline:
  start_year: 354
  end_year: 430
  peak_year: 397           # Year of Confessions — most notable work
  era: "Patristic"
  century: "4th–5th"
  era_color: "#8B1A1A"     # Crimson for Late Antique
```

## The Episode Layer

```yaml
episodes:
  - id: "S02E09"
    title: "Augustine's Garden"
    season: 2
    episode: 9
    role: "protagonist"     # main figure of this episode
  - id: "S01E04"
    title: "Marketplace of Gods"
    season: 1
    episode: 4
    role: "context"         # appears as context
```

## Build Order

### MVP (usable immediately)
1. Parse all `.md` files from the vault
2. Extract frontmatter → node data
3. Extract `[[wikilinks]]` → edges (untyped)
4. Render as a navigable graph (use D3.js or Cosmograph)
5. Keyboard navigation via vanilla JS
6. Search via simple text matching

**Tech stack**: Static site (no backend needed for MVP)
- Parser: Python (already on the Mini)
- Graph: Cosmograph (free, open source, handles 1M+ nodes) or D3.js
- Frontend: Vanilla JS or Svelte
- Search: Fuse.js (fuzzy search, free)
- Hosting: GitHub Pages or Vercel (free tier handles this)

### V1 (polished)
1. Edge type system (typed connections)
2. Painting navigation zones
3. Audio quotes (Web Audio API)
4. Timeline view
5. Story Mode paths
6. Semantic search (client-side embeddings or simple TF-IDF)

### V2 (full product)
1. Mobile (touch navigation mapped to keyboard logic)
2. The painting zones (clickable areas within paintings)
3. GLM-5 or local Gemma4 for "ask a question about this node"
4. User-created paths ("journeys")
5. The full episode viewer integrated
