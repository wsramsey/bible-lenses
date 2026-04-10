---
title: "What We Can Build Right Now — Free"
type: "Technical — Build Plan"
tags: [technical, build, free, immediate, mvp]
---

# What We Can Build Right Now — Free

## The Vault IS Ready
We have 1,100+ nodes. Every node has:
- Frontmatter with structured data
- `[[wikilinks]]` for connections
- Portrait images (`Assets/Images/`)
- Artifact images (`Assets/Artifacts/`)
- Primary source transcripts (578MB in `~/bible-lenses-content/transcripts/`)

This is the database. We don't need to build it. It exists.

## The MVP Build — One Weekend

### Step 1: Export the graph (2 hours)
```python
# Already written, just needs to run:
# python3 ~/bible-lenses-content/build-influence-tree.py
# → generates ~/bible-lenses-content/influence-graph.json
```

This JSON file contains every node and every connection. It's already building.

### Step 2: The viewer (1 day)
**Cosmograph** (free, open source): A WebGL-based graph renderer that handles 1M+ nodes at 60fps.

```bash
npm install @cosmograph/cosmos
```

Input: the JSON from Step 1
Output: the full navigable graph in a browser

### Step 3: Keyboard navigation (4 hours)
```javascript
// The keyboard navigation is just event listeners
// Arrow keys → move focus between nodes
// Enter → navigate to focused node
// / → open search
// etc.
```

### Step 4: Node panels (4 hours)
When you enter a node, a side panel opens showing:
- Portrait image
- Name + dates
- One quote (from the `artwork.quote` field)
- Connections list

### Step 5: Deploy (30 minutes)
```bash
# GitHub Pages — free
git push → automatically deployed at username.github.io/bible-lenses
```

**Total: One weekend. Total cost: $0.**

## What GLM-5 Adds (Via OpenRouter, ~$0.0002/query)
Once the graph is running, we add one endpoint:

```python
# User presses Q on Augustine node
# System pulls his transcript files
# Sends to GLM-5: "Speak as Augustine on the topic of grace"
# Returns: Augustine's voice, grounded in his actual writings
```

This is the killer feature. Not just *about* Augustine — *as* Augustine. With 578MB of primary sources, the hallucination risk is minimal.

## The Selah Scholar Vision — Now Achievable

From the MEMORY.md notes:
> "The app is navigating you through the labyrinth of thought to help answer your question. When you look at this constellation you are looking at Christianity itself."

The vault *is* the constellation. The graph renderer *is* the navigation. The paintings are the windows.

**The question was never: can we build it? The question was: do we have the data?**

We have the data.

## Next Step
Run this on the Mini:
```bash
cd ~/bible-lenses-content
python3 build-influence-tree.py
# → influence-graph.json (already partially built from earlier work)
```

Then set up Cosmograph on the iMac and point it at the JSON.

The graph will render. You'll see 1,100 nodes and their connections.

Then we make it beautiful.
