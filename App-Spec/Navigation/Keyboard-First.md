---
title: "Keyboard-First Navigation — The Complete Guide"
type: "UX Specification"
tags: [keyboard, navigation, ux, accessibility]
---

# Keyboard-First Navigation

## The Philosophy
This is not a keyboard shortcut layer on top of a mouse app. This is designed to be navigated entirely by keyboard — the way a musician navigates a keyboard, or a pilot navigates instruments. **The keyboard is how you think through the graph.**

Mouse/touch works perfectly. But keyboard navigation reveals the structure of the knowledge.

## The Complete Keybind Map

### Global (always available)
```
/           Search (semantic — type anything)
Escape      Close overlay / go back
Tab         Next connection
Shift+Tab   Previous connection
G           Toggle Graph View
T           Toggle Timeline View
?           Help / keybind reference
Cmd+K       Quick command palette
```

### Node View
```
↑ ↓         Scroll through connections
← →         Navigate connection history (back/forward)
Enter       Go to highlighted connection
1–9         Jump directly to connection 1–9
P           Open painting/artwork overlay
Q           Play primary source quote (audio + text)
A           Show artifact/object for this node
M           Show map/geographic context
X           Expand: show all connections (not just top 5)
C           Show contribution summary
W           Show world context for this era
E           Open episode that features this node
```

### Graph View
```
Arrow keys  Move selection between nodes
Enter       Enter selected node
+/-         Zoom in/out
0           Reset zoom to fit
F           Filter connections by type
F1          Show only Influence connections
F2          Show only Historical connections
F3          Show only Conflict connections
F4          Show only Typology connections
F5          Show only Artwork connections
S           Toggle Story Mode path
H           Highlight path between two nodes
N           Find nearest unvisited node
```

### Timeline View
```
← →         Move through time
Shift+← →  Jump by century
Home        Go to beginning (30 AD)
End         Go to now (2023)
Enter       Enter selected node
F           Filter by tradition/type
```

### Story Mode
```
→           Next in story
←           Previous in story
L           Leave story mode (keep position)
R           Return to beginning of current story
```

## The Power User Flows

### Finding What Connects Two Things
*"How does Augustine connect to Karl Barth?"*

1. Navigate to Augustine (search: `/Augustine`)
2. Press `H` (highlight path)
3. Type `Barth`
4. The shortest path lights up:
   Augustine → Original Sin → Luther → Reformed Theology → Barth

### Exploring an Era
*"Show me everything happening in the 5th century"*

1. Press `T` (Timeline View)
2. Navigate to 400 AD
3. Press `X` (expand) — all nodes in view
4. Press `F` to filter by type — see only Events, or only Scholars, etc.

### The Serendipity Walk
*"I want to discover something I didn't know I was looking for"*

1. Navigate to any node
2. Press `N` repeatedly — it takes you to the nearest node you haven't visited
3. Keep pressing `N`
4. See where you end up

### Deep Dive on a Painting
*"I want to understand this painting completely"*

1. Navigate to any Artwork node
2. Press `P` — full screen painting
3. While in painting view:
   - Click/tap any area of the painting to see what's there
   - Or navigate with arrow keys (the painting is divided into zones)
   - Each zone links to a connected node
4. Press `Q` — hear the primary source passage this painting depicts
5. Press `Enter` — enter the painting's main connected node

## The Painting Navigation (Special Case)

When you're in a painting full-screen, the painting becomes navigable:

**The Ghent Altarpiece zones:**
- Top center → God the Father node
- Top left → Mary of Nazareth node
- Top right → John the Baptist node
- Bottom center → Revelation 5 node (the Lamb)
- Bottom left → The Just Judges (the stolen panel story)
- The fountain → Revelation 22 node

**The Sistine Ceiling zones:**
- Panel 4 (Creation of Adam) → Adam node / Imago Dei node
- The prophet thrones → Individual prophet nodes
- The Last Judgment (altar wall) → The Last Judgment node

You navigate through the painting's theology by navigating through the painting itself.
