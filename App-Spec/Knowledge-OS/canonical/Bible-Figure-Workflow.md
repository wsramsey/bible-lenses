# Bible Figure Workflow

## Goal
Build every major Bible figure as a canonical note that combines biblical role, history of interpretation, denominational readings, and cultural afterlives.

## Required sections
- Biblical role
- Primary texts
- Narrative significance
- Key themes
- Major historical interpretations
- Denominational and traditional readings
- Use across the centuries
- Scholar threads in this vault
- Related notes
- Open questions / gaps
- Sources compiled

## Build process
1. ingest source material into `BibleFigures/raw/`
2. compile scholar positions into `BibleFigures/compiled/`
3. draft a figure page using `_Figure-Template.md`
4. promote mature drafts into `BibleFigures/canonical/`
5. update `Bible-Figures-Index.md`
6. log missing pieces in `health-check/`

## Model routing
- Gemma: extraction, structure, cleanup, scholar position pulling
- Qwen: readable first-pass figure profile and interpretation-history prose
- Premium: contested synthesis and final flagship note polishing

## Minimum source expectations
Each mature figure note should ideally connect to:
- biblical text
- at least one scholar or interpretive tradition
- at least one downstream use (art, doctrine, preaching, politics, controversy, or literature)
