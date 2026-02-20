# Project Plan

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-20

## Objective
Deliver `internal-notes-assistant` in 2 weeks as an internal, markdown-only system that ingests weekly ops notes, supports keyword/tag search, and generates weekly summaries.

## Phase Plan

### Phase 1 (Days 1-3): Structure + Intake
- Define designated markdown intake folder structure.
- Define required frontmatter/tag conventions.
- Add sample notes and acceptance checks.

### Phase 2 (Days 4-8): Searchability
- Implement index generation for markdown notes.
- Implement keyword search and tag filter behavior.
- Validate latency target (<2s typical query, up to 5,000 notes).

### Phase 3 (Days 9-12): Weekly Summary
- Build weekly summary generation in markdown.
- Define destination path for weekly summaries.
- Validate summary completeness from ingested notes.

### Phase 4 (Days 13-14): Stabilization + Handoff
- Resolve open questions (tag schema, summary location).
- Run final QA against success metrics.
- Prepare operator usage notes.

## Milestones
- **M1:** Intake path + tagging schema drafted.
- **M2:** Search and tag filtering functional under latency target.
- **M3:** Weekly summary generation complete in markdown.
- **M4:** v1 handoff complete with no external integrations.

## First Implementation Tasks
- [ ] Decide and document tagging schema.
- [ ] Define canonical folder for weekly summary outputs.
- [ ] Create initial markdown note corpus and tag normalization checklist.
- [ ] Build baseline index + search command flow.
- [ ] Validate against success metrics for latency and coverage.
