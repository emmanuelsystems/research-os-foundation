```text
PRD INPUT
project_name: internal-notes-assistant
goal: Create a searchable internal notes assistant for weekly operations updates.
owner: ops-team
constraints: 2-week timeline; markdown-only outputs; no external integrations in v1.
source: manual intake from planning call notes

PRD:
# Product Requirements Document (PRD)
## Summary
Create a lightweight, searchable notes assistant for weekly operations updates.

## Problem Statement
Weekly ops notes are hard to find and reuse because they live in scattered markdown files.

## Goals
- Centralize weekly ops notes in one searchable index.
- Enable simple keyword and tag search.
- Produce a weekly summary in markdown.

## Non-Goals
- Integrating with external ticketing systems.
- Replacing existing note-taking tools.

## Users and Stakeholders
- Primary Users: ops-team
- Stakeholders: operations lead

## Requirements
### Functional
1. Ingest markdown notes from a designated folder.
2. Support keyword search and tag filters.
3. Generate a weekly summary markdown file.

### Non-Functional
- Performance: search results under 2 seconds for up to 5,000 notes.
- Security/Privacy: internal-only access; no external sharing.

## Success Metrics
- 90 percent of weekly notes are searchable within 24 hours.
- Search latency under 2 seconds for typical queries.

## Constraints
- Markdown-only storage.
- No external integrations in v1.

## Risks
- Inconsistent tagging reduces search quality.

## Open Questions
1. What tagging schema should be enforced?
2. Where should the weekly summary be stored?
```
