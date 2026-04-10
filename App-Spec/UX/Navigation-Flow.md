---
title: "Navigation Flow — How You Move Through the Graph"
type: "UX Specification"
tags: [ux, navigation, keyboard, graph, flow]
---

# Navigation Flow

## The Three Views

### 1. NODE VIEW (default)
You're inside a single node. Full screen.

**Layout:**
```
┌─────────────────────────────────────────────────┐
│  [ERA TAG]          [TRADITION TAG]              │
│                                                  │
│  ┌──────────┐  NAME                             │
│  │          │  Dates · Location                 │
│  │ PAINTING │                                   │
│  │ or FACE  │  One-line description              │
│  │          │                                   │
│  └──────────┘  ─────────────────────────────── │
│                                                  │
│  KEY QUOTE (highlighted, readable)               │
│                                                  │
│  ─────────────────────────────────────────────  │
│                                                  │
│  CONNECTIONS  [5 visible, more below]            │
│  → Augustine of Hippo                            │
│  → Council of Nicaea (325)                       │
│  → The Fall of Rome                              │
│  → Pelagian Controversy                          │
│  → Monica (mother)                               │
│                [↓ 12 more connections]           │
│                                                  │
│  [P] Painting   [Q] Quote   [T] Timeline         │
└─────────────────────────────────────────────────┘
```

**Keyboard in Node View:**
- `↓` / `↑` — scroll through connections
- `Enter` — go to highlighted connection
- `P` — painting/artwork overlay
- `Q` — primary source quote (audio + text)
- `T` — show on timeline
- `Backspace` — go back
- `Space` — expand to Graph View

---

### 2. GRAPH VIEW (Space bar)
The node explodes outward. You see the web.

**Layout:**
The current node sits at center. Connections radiate. Each connection is a line. The line's color indicates the type:
- 🟡 **Gold** — Influence (this person shaped that person)
- 🔵 **Blue** — Historical Event (this person was at/shaped this event)
- 🔴 **Red** — Conflict/Debate (these two argued)
- 🟢 **Green** — Typology (this OT figure/event points to this NT reality)
- 🟣 **Purple** — Artwork (this painting depicts/was inspired by this node)
- ⚪ **White** — General Connection

**Keyboard in Graph View:**
- Arrow keys — move selection between visible nodes
- `Enter` — enter selected node
- `+` / `-` — zoom in/out
- `F` — filter by connection type
- `G` — toggle full global graph (all 1,100+ nodes visible)
- `Backspace` — return to Node View

---

### 3. TIMELINE VIEW (T key)
The current node appears on a horizontal timeline. Nearby events and figures appear. You can scroll left/right through history.

**Layout:**
```
◄─────────────────────────────────────────────►
100 AD    200 AD    300 AD    400 AD    500 AD

         [PERPETUA]     [NICAEA] [AUGUSTINE]
              ↑               ↑        ↑
         [PLINY'S     [CONSTANTINE]  [FALL OF
          LETTER]                     ROME]
```

Color coding matches the node type. Hover/select any node to preview. Enter to go there.

---

## The Journey Modes

### DRIFT MODE (default)
You navigate freely. No prescribed path. Follow what interests you. The graph expands wherever you go.

### STORY MODE (S key)
The app suggests a path — chronological, or thematic, or by tradition. You can follow it or leave it at any moment.

*Story Mode paths:*
- The Full Timeline (chronological, 2,000 years)
- The Mystics (a thread through every major mystical figure)
- The Reformers (a thread through every Reformation figure)
- The Artists (following the visual tradition)
- The Martyrs (a thread through martyrdom accounts)
- The Arguments (following every major theological controversy)
- The Global South (Christianity's demographic revolution)

### DEEP DIVE MODE (D key)
Select any node. The app builds you a complete "reading list" — the primary sources, the key secondary sources, the museum links, the audio recordings. A research assistant mode.

---

## The Search

`/` opens search. Type anything. Results appear instantly:

- Names (Augustine, Luther, Aquinas)
- Events (Council of Nicaea, Black Death)
- Ideas (Grace, Predestination, Theosis)
- Questions ("why did Christianity grow under persecution?")
- Paintings (search by artist, subject, museum)
- Era (search by century)

The search is **semantic** — searching "suffering and God" finds Job, Theodicy, Irenaeus, Moltmann, Weil, the Psalms of Lament, the Isenheim Altarpiece.
