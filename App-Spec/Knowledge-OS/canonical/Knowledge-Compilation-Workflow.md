# Knowledge Compilation Workflow

## Core principle
**If a task produces durable knowledge, it should leave behind a file.**

## Pipeline
1. raw ingest
2. compile to markdown
3. promote into canonical notes
4. query through the wiki
5. save worthwhile outputs back into the wiki
6. run periodic health checks

## Folder roles
- `raw/` — source material
- `compiled/` — intermediate machine-assisted outputs
- `canonical/` — stable reusable notes
- `generated/` — reports, answer docs, slide drafts, summaries
- `indexes/` — master indexes and topic maps
- `health-check/` — duplicate, missing-data, broken-link, and underdevelopment reports

## Save when
- it will matter again
- the reasoning is reusable
- the synthesis took real effort
- it answers a recurring question
- it improves future retrieval

## Keep ephemeral when
- it is trivial chatter
- it is one-off logistics
- it has no likely future value

## Anti-patterns
- mixing raw and canonical materials
- saving nothing but chat answers
- repeated re-synthesis instead of note updates
- duplicate canonical pages
- using premium models for shoveling work
