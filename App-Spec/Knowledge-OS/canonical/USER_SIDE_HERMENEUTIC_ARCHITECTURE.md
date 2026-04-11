# User-Side Hermeneutic Architecture

## Purpose
Help Bible Lenses answer the question the user is actually asking by modeling interpretive posture, formation goal, and question context without boxing the user into a fixed identity.

## Core principle
A good answer mediates between:
- the text
- the tradition
- the hermeneutic/method
- the user's current posture
- the formation need beneath the question

## What to model
### Reader posture
- inherited/current tradition
- explicit beliefs
- inferred presuppositions
- tolerance for ambiguity
- preferred answer style
- recurring themes in questions
- current existential pressure points

### Question event
- raw question
- explicit topic
- inferred underlying concern
- emotional tone
- desired outcome
- answer style used
- sources used
- feedback / response

### Formation goal
- clarity
- consolation
- comparison across traditions
- doctrinal precision
- historical understanding
- spiritual direction
- moral discernment
- prayerful reflection

## Rules
1. User modeling must remain probabilistic and revisable.
2. Explicit beliefs are stored separately from inferred posture.
3. Low-confidence inferences should not over-control retrieval.
4. The system should fit the user for clarity, not flatter them.
5. If confidence about the user's lens is low, answer more broadly and surface assumptions explicitly.

## Retrieval flow
1. classify the question
2. infer likely posture + formation goal
3. retrieve text/tradition/method candidates
4. plan answer structure
5. answer honestly
6. update question-event memory, not a frozen user essence

## Four kinds of truth to balance
- textual truth
- interpretive truth
- communal truth
- existential truth

## Practical caution
This layer should help the system understand the user's horizon. It should not become manipulative, psychoanalytic cosplay, or overconfident mind-reading.
