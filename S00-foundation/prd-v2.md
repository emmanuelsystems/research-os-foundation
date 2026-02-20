# Product Requirements Document (PRD)

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-20

## 1. Document Control
- **Project Name:** internal-notes-assistant
- **Owner:** ops-team
- **Version:** v0.1.0
- **Decision State:** draft

## 2. PRD Source Traceability
- **Primary Source:** manual intake from planning call notes
- **Source Input Block Fields:** `project_name`, `goal`, `owner`, `constraints`, `source`, `PRD`

## 3. Summary
Create a lightweight, searchable notes assistant for weekly operations updates.

## 4. Problem Statement
Weekly ops notes are hard to find and reuse because they live in scattered markdown files.

## 5. Goals
- Centralize weekly ops notes in one searchable index.
- Enable simple keyword and tag search.
- Produce a weekly summary in markdown.

## 6. Non-Goals
- Integrating with external ticketing systems.
- Replacing existing note-taking tools.

## 7. Users and Stakeholders
- **Primary Users:** ops-team
- **Stakeholders:** operations lead

## 8. Requirements
### Functional
1. Ingest markdown notes from a designated folder.
2. Support keyword search and tag filters.
3. Generate a weekly summary markdown file.

### Non-Functional
- Performance: search results under 2 seconds for up to 5,000 notes.
- Security/Privacy: internal-only access; no external sharing.

## 9. Success Metrics
- 90 percent of weekly notes are searchable within 24 hours.
- Search latency under 2 seconds for typical queries.

## 10. Constraints
- 2-week timeline.
- Markdown-only outputs/storage.
- No external integrations in v1.

## 11. Risks
- Inconsistent tagging reduces search quality.

## 12. Open Questions
1. What tagging schema should be enforced?
2. Where should the weekly summary be stored?
