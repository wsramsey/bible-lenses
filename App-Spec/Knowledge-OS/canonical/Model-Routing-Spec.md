# Model Routing Spec

## One-line rule
**Gemma does the digging, Qwen does the drafting, premium does the deciding.**

## Tiers
### Tier 1 — Local / Free
Primary: `ollama/gemma4:e4b`
Use for extraction, cleanup, tagging, normalization, OCR post-processing, ETL, sync jobs, and all sensitive/private data.

### Tier 2 — Cheap Remote or Cheap Local Workhorse
Primary: Qwen-class model
Use for readable first drafts, synthesis over compiled notes, explanatory prose, and medium-quality batch writing.

### Tier 3 — Premium
Use for nuanced judgment, final synthesis, flagship writing, architecture decisions, and difficult debugging.

## Global rules
1. No premium model for batch jobs.
2. No premium model for first drafts.
3. Sensitive data defaults to local Gemma.
4. Queries that produce durable knowledge should create/update markdown notes.
5. Sample before scaling paid runs.

## App routing
### Bible Lenses
- Gemma: extraction, OCR cleanup, note cleanup, metadata, tagging
- Qwen: figure drafts, interpretation-history drafts, scholar synthesis
- Premium: final theological synthesis and contested judgment

### JobForcast
- Gemma: ETL, logs, private summaries, transforms, data cleanup
- Qwen: proposal drafts, customer-facing first-pass prose, summaries
- Premium: architecture, hard debugging, strategic product reasoning

### No Guilt
- Gemma: transaction classification, recurring-payment detection, private financial summaries
- Qwen: monthly summaries, coaching drafts, onboarding copy
- Premium: product strategy, behavioral design, final trust-sensitive copy
