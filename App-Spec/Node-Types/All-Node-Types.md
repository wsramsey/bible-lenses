---
title: "Node Types — The Complete Taxonomy"
type: "Technical Specification"
tags: [nodes, taxonomy, types, graph]
---

# Node Types — Complete Taxonomy

## The 14 Node Types

Every note in the vault maps to one of these node types. Each has a distinct visual treatment.

---

### 1. SCHOLAR / THINKER
**Shape**: Circle
**Color**: Amber/Gold
**Size**: Scaled by `weight` field (1–15)
**Image**: Portrait (painting or photograph)
**Examples**: Augustine, Aquinas, Luther, Barth, Weil

*What you see when you enter:*
Portrait → Name + dates → Tradition → One quote → Connections → The question their life asks

---

### 2. HISTORICAL FIGURE (non-scholar)
**Shape**: Square
**Color**: Steel blue
**Examples**: Constantine, Charlemagne, Plato, Saladin, Napoleon

*Distinct from Scholar:* Their significance is what they *did*, not what they *thought*

---

### 3. BIBLICAL FIGURE
**Shape**: Star (6-pointed)
**Color**: Deep gold
**Examples**: Adam, Moses, David, Isaiah, Paul, Mary Magdalene

*What you see when you enter:*
The canonical painting/artifact → Biblical text → Historical context → What theologians said → Typological connections → The question

---

### 4. HISTORICAL EVENT
**Shape**: Diamond
**Color**: Crimson
**Examples**: Council of Nicaea (325), Black Death (1347), Luther's 95 Theses (1517)

*What you see when you enter:*
The primary image (painting/artifact) → Date → Who was there → What happened → Why it mattered → What it changed

---

### 5. ARTWORK
**Shape**: Rounded rectangle
**Color**: Purple/violet
**Examples**: The Ghent Altarpiece, Rublev's Trinity, Bach's St. Matthew Passion

*What you see when you enter:*
The artwork full-screen → Artist + date + museum + catalog number → What it depicts → The theology in it → Connected nodes

---

### 6. PLACE / MONUMENT
**Shape**: Hexagon
**Color**: Forest green
**Examples**: Hagia Sophia, Chartres Cathedral, Jerusalem, Monte Cassino

*What you see when you enter:*
Photograph/artifact → Location → Historical layers → What happened here → Connected nodes

---

### 7. THEOLOGICAL ISSUE / DEBATE
**Shape**: Octagon
**Color**: Orange
**Examples**: Predestination, Baptism, Homosexuality and the Church, The Atonement

*What you see when you enter:*
The question in large text → The positions (with their scholars) → The biblical texts → The historical arc → Where it stands today

---

### 8. HERMENEUTICAL METHOD
**Shape**: Triangle
**Color**: Teal
**Examples**: Allegorical Interpretation, Form Criticism, New Perspective on Paul

*What you see when you enter:*
The method described → Who developed it → What it produces → What it misses → Key scholar

---

### 9. HISTORICAL MOVEMENT
**Shape**: Elongated oval
**Color**: Warm orange-red
**Examples**: Monasticism, Pietism, Pentecostalism, Liberation Theology

*What you see when you enter:*
The movement's origin story → Its key figures → Its geographic spread → Its theological contribution → Its legacy

---

### 10. ANCIENT RELIGION / MYTHOLOGY
**Shape**: Crescent
**Color**: Deep indigo
**Examples**: Enuma Elish, Baal Cycle, Zoroastrianism, Egyptian Religion

*What you see when you enter:*
The artifact (cylinder seal, tablet, relief) → What it says → How it connects to the Bible → The scholarly debate

---

### 11. BIBLICAL TEXT
**Shape**: Open book
**Color**: Ivory/cream
**Examples**: Genesis 1–3, Psalm 22, Romans 5, Revelation 5

*What you see when you enter:*
The text → Its manuscript (oldest known) → Its historical context → Key interpretations → Connected scholars and events

---

### 12. CULTURAL FRUIT
**Shape**: Leaf
**Color**: Bright green (good fruit) / Dark red (rotten fruit)
**Examples**: Universities, Hospitals, The Crusades, Abolition, Sex Abuse Crisis

*What you see when you enter:*
The claim → The evidence → The tradition breakdown → The complications → The honest verdict

---

### 13. WORLD CONTEXT
**Shape**: Globe segment
**Color**: Slate
**Examples**: The World Augustine Was Born Into, The World Karl Barth Wrote In

*What you see when you enter:*
The map of the era → Key events happening simultaneously → Why it matters for understanding the thinker

---

### 14. EPISODE (Documentary)
**Shape**: Film frame
**Color**: Black with white border
**Examples**: S01E01 The Upper Room, S04E25 Here I Stand

*What you see when you enter:*
The episode title + runtime → The central painting → The story synopsis → The primary sources → The sound design notes → The question

---

## The Connection Types (Line Colors)

| Color | Type | Meaning |
|-------|------|---------|
| 🟡 Gold | Influence | Person A shaped Person B |
| 🔵 Blue | Historical | Node A and Node B share a historical moment |
| 🔴 Red | Conflict | Node A and Node B disagreed/fought |
| 🟢 Green | Typology | OT node points forward to NT/theological node |
| 🟣 Purple | Artwork | This artwork depicts/was made about this node |
| 🟠 Orange | Causation | Event A caused Event B |
| ⚪ White | Reference | General connection |
| ⚫ Black | Rotten fruit | This node produced this harm |
