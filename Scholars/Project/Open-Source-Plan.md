---
image: "Assets/Artifacts/codex-sinaiticus.jpg"
name: "Selah Scholar — Open Source Plan"
type: project-planning
created: 2026-04-08
status: future — do not build yet
tags: [project, open-source, planning]
artwork:
  title: School of Athens
  artist: Raphael Sanzio
  date: 1509–1511
  museum: Vatican Museums (Stanza della Segnatura)
  catalog: Vatican inv. — Stanza della Segnatura
---

# Selah Scholar — Open Source Plan

*Created April 8, 2026. Do not build yet — complete the data layer first.*

---

## The Vision (Wyatt's Words)

> "I'd like you to feel like you are inside of the brain of church history and thought. A full connection of brain synapses showing the history of 3000 years of thought. The app is navigating you through the labyrinth of thought to help answer your question.
>
> In a sense when you look at this constellation you are looking at Christianity itself.
>
> A big family tree showing the full scope of thought and revelation through the years. A way to understand where we came from if we identify as a Christian."

---

## What We're Building

A provenance system for theological thought. Not a chatbot, not a database — an experience.

You ask a question and the relevant synaptic path lights up across 3,000 years of connected thought. The constellation IS Christianity.

**The two modes (same mode, different depth):**
- Quick answer: illuminated path, stop when satisfied
- Cave dive: follow the path into the next node and the next, into unknown depths

---

## Data Architecture

### Three Tiers
1. **Obsidian Vault** — source of truth. Human-curated markdown. Everything else generated from this.
2. **SQLite DB** — machine-queryable. nodes, edges, chunks tables. Rebuilt nightly from vault.
3. **Vector Embeddings** — semantic search. Local (sqlite-vec or pgvector). Free.

### Question Flow
```
User asks question
→ Embed question (local model, free)
→ Find nearest chunks (Tier 3 — semantic)
→ Pull edge graph for those nodes (Tier 2)
→ Illuminated subgraph (Tier 1 structure)
→ Frontend renders synaptic firing animation
```

### Zoom Levels (data-driven by weight score)
1. Galaxy — traditions (Christianity, Judaism, Greek Philosophy)
2. Solar System — branches (Catholic, Orthodox, Protestant)
3. Planets — denominations/movements
4. Moons — individual thinkers
5. Surface — texts, contexts, biographical causes

### Node Weight System
Five dimensions scored 1-5:
- `influence_radius` — how many subsequent thinkers shaped
- `temporal_depth` — how long in the conversation
- `cross_trad_reach` — matters outside own tradition
- `source_avail` — primary texts accessible
- `soil_depth` — how many roots feed in

Composite 5-25. Suppressed voices get +2 cross_trad_reach (hidden influence bonus).

---

## Visual Language

Neural/synaptic — not planets and orbits. Organic, asymmetrical, alive.
- Nodes glow and pulse
- Connections fire when traced
- The feeling of being inside a mind, not reading a diagram

**Tech candidates:** Three.js (3D), Cosmograph (large-scale graph), D3.js (hierarchical radial)

---

## Edge Types (Multi-Causal)

| Type | Meaning |
|---|---|
| `influenced-by` | Direct intellectual debt |
| `reacted-against` | Wrote in opposition to |
| `enabled-by` | Technology/event made this possible |
| `forced-by` | Crisis/heresy provoked the response |
| `biographical-cause` | Personal experience → theological position |
| `translation-cause` | A translation decision created a doctrine |
| `parallel-convergent` | Independent similar conclusions |
| `suppression` | Institutional power silenced this voice |
| `controversy-spawned` | This thinker exists because of that fight |

Every edge has `confidence` (primary / scholarly-consensus / probable / contested / wikipedia-unverified) and `source` citation.

---

## Open Source Strategy

### Why Open Source
- The Western Protestant bias in the current data needs correction from voices we don't have
- A Coptic scholar knows the Egyptian church fathers better than we do
- A Korean theologian can add the Korean church's tradition properly
- Community corrections will be more accurate than single-author curation

### License
**Creative Commons CC-BY-SA** (same as Wikipedia)
- Free to use, modify, build on
- Must attribute
- Must share alike
- Prevents commercial lock-in

### Repository Structure
```
selah-scholar/
  vault/              ← Obsidian markdown (the data)
    Scholars/
    Sources/
    Councils/
    ChurchFathers/
    Canons/
    Suppressed/
    OralTradition/
    Trunks/
    Philosophers/
    Context/
  data/               ← Generated JSON
    scholars-taxonomy.json
    influence-graph.json
  pipeline/           ← Free tools
    fetch-texts.sh
    chunk-with-taxonomy.py
    score-nodes.py
    selah-sync.sh
  scripts/            ← Build/sync utilities
```

### Two-Tier Contribution Model (Option B — recommended)

**Core layer (curated, reviewed):**
- Root nodes (Hebrew Scripture, Paul, Plato, etc.)
- Trunk nodes (church splits, councils, apostolic succession)
- Major Church Fathers
- Canonical source texts

*Changes require editorial review + primary source citation*

**Leaf layer (community-contributed):**
- Individual scholars at zoom level 4-5
- Regional/national theological traditions
- Oral tradition nodes
- Contemporary thinkers

*Contributors fill out a structured template; PR merged after basic review*

### Governance
- Small editorial board (3-5 people) for core layer
- Community review (2 approvals) for leaf layer
- Conflict resolution: contested claims get `confidence: contested` tag, not edit wars
- Living theologians policy: included only after significant peer-reviewed engagement with their work

### Contribution Template (for new nodes)
```yaml
name: ""
years: ""
tradition: ""
denomination: ""
sub_tradition: ""
trinitarian_position: ""
hermeneutical_lenses: []
wiki: ""
interpretive_center: ""
transmission_method: ""
geographic_context: ""
influenced_by:
  - node: ""
    type: ""  # influenced-by | reacted-against | etc.
    confidence: ""  # primary | scholarly-consensus | probable
    source: ""  # exact quote or citation
primary_works: []
context: ""  # 2-3 sentences on historical world
bio_shaped_by: ""  # 2-3 sentences on personal formation
```

---

## Wikipedia Edge Mining

Every node has a `wiki` URL. The system mines Wikipedia's:
- "Influenced by" sections
- "Influenced" sections  
- Categories
- "See also" links

These suggest edges the curated graph missed. All Wikipedia-sourced edges get `confidence: wikipedia-unverified` until confirmed against primary texts.

**Why this matters:** Shows connections you haven't thought of before. The unexpected edge is the product's differentiator.

---

## What Needs to Happen Before Open Sourcing

1. Complete the build queue (Layers 0-12 fully populated)
2. Build the SQLite layer + sync script working
3. Build a minimal working visualization (proof of concept)
4. Write contribution guidelines
5. Set up GitHub repository
6. Choose a public name for the project

---

## Naming (Not Decided)

The project needs a name that:
- Signals open intellectual history of Christian thought
- Doesn't feel like one person's brand
- Is findable / memorable
- Works in multiple languages

Options to consider (not committing):
- **Logos** (taken, but thematically right)
- **Rhizome** (roots spreading underground — the soil metaphor)
- **The Chronicle** (too generic)
- **Kairos** (the fullness of time — but Greek)
- **Arche** (origin/beginning — the root node concept)

*Decision deferred until ready to build.*

---

## Build Order (When Ready)

1. Complete Layers 0-12 in vault ← *we are here*
2. SQLite schema + import from vault
3. Embedding pipeline (nomic-embed via Ollama — free)
4. Wikipedia edge enrichment
5. Query API (Python, local)
6. Frontend prototype (Three.js or Cosmograph)
7. Open source release

**DO NOT BUILD APP UNTIL DATA LAYER IS COMPLETE.**
