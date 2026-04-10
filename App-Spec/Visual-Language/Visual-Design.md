---
title: "Visual Design Language"
type: "Design Specification"
tags: [design, visual, dark-mode, typography, color]
---

# Visual Design Language

## The Aesthetic
**Dark space. Glowing nodes. Ancient meets future.**

Think: the inside of a cathedral at night, but made of data. Or the Antikythera mechanism — ancient, precise, beautiful, functional. Or the star maps of the Arab astronomers who preserved classical knowledge — each star a node, each line a relationship.

Not flat design. Not Material Design. Something with depth, shadow, and texture.

## The Color System

### Background
Near-black with a very slight warm tint — not pure black, which feels digital. The warmth suggests candlelight, vellum, the color of old paper.
`#0D0B08` (primary background)
`#1A1710` (secondary surface)

### Node Colors (by type)
Each node type has a primary color and a glow:
- Scholar: `#D4A017` (aged gold) with soft amber glow
- Event: `#8B1A1A` (deep crimson) with red pulse on hover
- Artwork: `#5B3A8C` (Byzantine purple) with violet glow
- Biblical Figure: `#8B7032` (burnished bronze) with gold glow
- Place: `#2D5A1B` (forest) with green glow
- Issue/Debate: `#C85A1A` (fire orange)
- Movement: `#8C2A00` (warm rust)
- Ancient Religion: `#1A2B5A` (deep night blue)
- Fruit/Good: `#2A7A1A` (growth green)
- Fruit/Rotten: `#7A1A1A` (dark blood)

### Connection Line Colors
- Influence: `#D4A017` (gold, 40% opacity)
- Historical: `#4A7AB5` (steel blue)
- Conflict: `#CC3333` (red)
- Typology: `#4AB54A` (green)
- Artwork: `#8A4AB5` (purple)
- Causation: `#E07A20` (orange)

### Typography
- **Primary**: A serif with slight calligraphic quality — EB Garamond or similar. History deserves a historical typeface.
- **Secondary**: Clean sans for labels and navigation — Inter or similar.
- **Quote text**: Slightly larger, slightly wider line-spacing. The words that matter get space.
- **Era labels**: Small-caps, widely tracked.

## The Node Visual Treatment

### The Portrait Node (Scholar/Figure)
```
┌──────────────────────────────────┐
│                                  │
│    ┌────────────┐                │
│    │            │  AUGUSTINE     │
│    │  PORTRAIT  │  OF HIPPO      │
│    │   (oil     │                │
│    │  painting) │  354 – 430 AD  │
│    │            │  North Africa  │
│    └────────────┘                │
│                                  │
│  "Our heart is restless until    │
│   it rests in Thee."             │
│                                  │
│  ────────────────────────────    │
│  Connections  [23]               │
│                                  │
│  🟡 → Pelagius                   │
│  🟡 → Thomas Aquinas             │
│  🔵 → Council of Nicaea (325)    │
│  🔵 → Fall of Rome (410)         │
│  🟣 → Philippe de Champaigne    │
│                                  │
│  [P] Portrait  [Q] Quote  [T] ─  │
└──────────────────────────────────┘
```

### The Artwork Node
```
┌──────────────────────────────────┐
│                                  │
│  ┌──────────────────────────┐   │
│  │                          │   │
│  │   THE PAINTING           │   │
│  │   Full width             │   │
│  │   Ken Burns pan on load  │   │
│  │                          │   │
│  └──────────────────────────┘   │
│                                  │
│  TITLE                           │
│  Artist · Date · Museum          │
│  Catalog: [number]               │
│                                  │
│  What it depicts → [node link]   │
│  What it means → [brief]         │
│                                  │
│  🟣 Connected nodes:             │
│  → Augustine of Hippo            │
│  → The Restless Heart            │
│  → North African Christianity    │
└──────────────────────────────────┘
```

### The Event Node
```
┌──────────────────────────────────┐
│  ◆ HISTORICAL EVENT              │
│                                  │
│  COUNCIL OF NICAEA               │
│  325 AD · Nicaea, Asia Minor     │
│                                  │
│  ┌──────────┐  ~300 bishops.     │
│  │ ICON OR  │  Many bore marks   │
│  │ ARTIFACT │  of torture.       │
│  └──────────┘  One word changed  │
│                everything.        │
│                                  │
│  Before: Arianism spreading      │
│  After: Nicene orthodoxy         │
│                                  │
│  Key figures present:            │
│  → Athanasius · Constantine      │
│  → Arius (condemned)             │
│                                  │
│  What it produced:               │
│  → The Nicene Creed [text]       │
└──────────────────────────────────┘
```

## The Graph View Aesthetic

**Imagine**: A star map. But the stars are ideas and the constellations are historical connections.

- Nodes glow with their type-color
- The glow intensifies when you approach
- Connection lines are semi-transparent, with slight movement (pulsing slowly)
- Zooming out: individual nodes collapse into their type-color glow — a galaxy of thought
- Zooming in: details emerge — portraits, labels, connection types

**The global graph view** (all 1,100+ nodes visible):
When you pull fully back, the entire history of Christianity becomes visible as a shape. The density of nodes around 325 AD (councils), 1517 (Reformation), 1906 (Azusa). The thin edges (the period between the Apostolic era and the 3rd century). The explosion of the Global South after 1950.

The shape of Christianity — visible in data.
