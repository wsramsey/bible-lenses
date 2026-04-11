# Bible Lenses Chat Accuracy Plan

## Purpose
Improve Bible Lenses chat accuracy by treating semantic retrieval as a discovery layer and exact markdown notes as the grounding layer.

This plan is designed to reduce:
- semantic drift
- blended interpretations
- false recall
- overconfident synthesis
- loss of source attribution

It adopts the core lesson from the no-escape theorem: **semantic memory is useful but unreliable as an exact long-term memory unless paired with an exact episodic record and verification layer.**

---

## Core Principle

> **Semantic retrieval finds the neighborhood; markdown sources decide the answer.**

Embeddings, graphs, and LLM memory are useful for locating relevant material.
They are not sufficient for establishing exact claims.

---

## The Bible Lenses Chat Stack

### Layer 1 — Discovery / Semantic Retrieval
Use semantic retrieval to identify likely relevant items:
- Bible figures
- scholars
- doctrines
- eras
- controversies
- art/literature notes
- related themes

Allowed tasks:
- candidate discovery
- clustering
- relation finding
- topic expansion
- first-pass relevance ranking

Not trusted for:
- exact historical claims
- exact attribution
- final arbitration between competing interpretations

---

### Layer 2 — Exact Episodic Grounding
Use filesystem/markdown notes as the exact record.

Grounding materials include:
- canonical figure notes
- compiled scholar notes
- source excerpt notes
- controversy notes
- tradition notes
- chronology notes
- primary text notes

These notes should preserve:
- exact quotations when needed
- source references
- article/book identity
- page/section references when available
- distinctions between competing claims

---

### Layer 3 — Verification and Answer Construction
Before a chat answer is finalized, the system should:
1. pull canonical notes
2. pull supporting compiled/source notes
3. separate fact from interpretation
4. separate tradition from modern scholarship
5. identify uncertainty or disagreement
6. generate answer only from grounded materials

If grounding is weak, the system should say so.

---

# Required Note Types

## 1. Canonical Figure Notes
Purpose: stable synthesis pages for figures.

Required sections:
- Biblical role
- Primary texts
- Narrative significance
- Key themes
- Major historical interpretations
- Denominational and traditional readings
- Use across the centuries
- Scholar threads in this vault
- Open questions / gaps
- Sources compiled

---

## 2. Compiled Scholar Interpretation Notes
Purpose: one-note-per-scholar-or-source-cluster per figure/theme when needed.

Examples:
- `David - Augustine.md`
- `Jonah - Modern Critical Readings.md`
- `Isaiah - Catholic Commentary Traditions.md`

Should include:
- scholar/tradition name
- summary of interpretation
- exact relevant claims
- where this reading differs from others
- links into canonical notes

---

## 3. Source Excerpt Notes
Purpose: preserve exact wording or tightly bounded source-based claims.

Should include:
- work title
- author
- edition/source info
- quoted section or precise summary
- figure/theme relevance

---

## 4. Controversy Notes
Purpose: preserve disagreement without flattening it.

Examples:
- historicity questions
- authorship disputes
- moral controversy
- denominational disagreements
- sexuality/gender readings
- violence/ethics questions

---

## 5. Tradition Notes
Purpose: preserve tradition-specific readings that should not be averaged together.

Examples:
- Catholic reading of Mary
- Orthodox reading of icons and saints
- Protestant reading of Paul
- Jewish reading of Isaiah or Jonah

---

# Chat Answer Rules

## Rule 1 — Never answer from semantic retrieval alone
Semantic retrieval may nominate relevant notes.
It may not serve as the sole basis of an answer.

## Rule 2 — Canonical note plus support note minimum
For non-trivial answers, use:
- at least one canonical note
- at least one supporting compiled/source note when available

## Rule 3 — Preserve layers of discourse
Separate:
- biblical text
- reception history
- denominational interpretation
- modern scholarship
- cultural afterlife

## Rule 4 — Preserve disagreement explicitly
Do not collapse contested readings into a single synthetic claim when traditions or scholars substantially differ.

## Rule 5 — Show uncertainty when grounding is weak
If the vault has poor support, say:
- evidence in vault is thin
- interpretation is disputed
- source grounding is partial
- further source compilation needed

## Rule 6 — Attributable claims for major assertions
If a major claim is made about a scholar, tradition, or historical reading, it should be traceable to a note in the vault.

---

# Preferred Internal Answer Flow

## Step 1 — Parse question type
Identify whether the user is asking about:
- biblical narrative
- doctrine
- reception history
- denominational difference
- historical criticism
- art/literature/culture
- controversy

## Step 2 — Semantic discovery
Retrieve candidate notes by theme/figure/scholar/topic.

## Step 3 — Exact grounding pull
Pull:
- canonical figure/theme note
- relevant compiled interpretation notes
- relevant controversy/tradition notes
- exact source excerpt notes when available

## Step 4 — Layer separation
Sort findings into:
- text itself
- historical interpretation
- denominational differences
- modern critical debate
- confidence level

## Step 5 — Answer generation
Generate from grounded notes only.

## Step 6 — Save if valuable
If the answer creates durable synthesis, save it as a markdown artifact.

---

# Recommended Output Structure for Chat

For important questions, answers should internally follow this shape:

1. **Direct answer**
2. **What the biblical text shows**
3. **How major traditions have read it**
4. **What modern scholars debate**
5. **Where uncertainty remains**
6. **Related figures/themes if useful**

Not every answer needs all sections explicitly, but the internal reasoning should respect them.

---

# Confidence Model

## High confidence
- canonical note exists
- multiple supporting notes exist
- claims are attributed
- traditions are clearly separated

## Medium confidence
- canonical note exists
- some support notes exist
- attribution is partial
- one or more layers are thin

## Low confidence
- only semantic matches exist
- no mature canonical note
- little source compilation
- likely drift risk

Low-confidence answers should be visibly more cautious.

---

# Implementation Plan

## Phase 1 — Structure
- create canonical figure template
- create compiled/source/tradition/controversy note types
- create index and health-check notes

## Phase 2 — Grounding Rules
- require source trail sections
- require separation of text / interpretation / debate
- require open questions section

## Phase 3 — Retrieval Discipline
- semantic retrieval for discovery only
- canonical+support note rule for answer generation
- caution flag when support is weak

## Phase 4 — Corpus Expansion
Prioritize:
1. major biblical figures
2. high-volume scholar threads
3. major controversies
4. denominational differences
5. canonical doctrine/theme notes

## Phase 5 — Health Checks
Run periodic checks for:
- canonical notes lacking supporting notes
- major claims with weak attribution
- duplicate figure pages
- unresolved controversy notes
- missing tradition coverage

---

# Immediate Next Actions

1. Create note templates for:
   - source excerpt
   - compiled scholar interpretation
   - controversy note
   - tradition note
2. Seed these note types for a handful of major figures.
3. Build a retrieval checklist for chat generation.
4. Update GitHub so the new architecture is versioned and reusable.

---

# One-Line Summary

**Bible Lenses chat should use semantic tools to find relevant material, but exact markdown notes with source trails must govern what the system is allowed to say.**
