# Example Run: Idea to Repo

- **Status:** reviewed
- **Owner:** example-curator
- **Last Updated:** 2026-02-16

## Fake project idea
**Idea:** Build a lightweight “Paper Pulse” digest that summarizes new research notes every Friday.

## Filled PRD (abbreviated, template-aligned)

## 1. Document Control
- **Project Name:** paper-pulse-digest
- **Owner:** research-ops
- **Contributors:** analyst-1, analyst-2
- **Version:** v0.1.0
- **Decision State:** reviewed

## 2. PRD Source Traceability
- **Primary Source:** Weekly research sync notes
- **Supporting Sources:** Slack intake thread; prior digest doc
- **Source Links / File Paths:** `../S90-assets/bonus-lesson-clip-map.md` (reference format only)

## 3. Problem Statement
Research updates are scattered; teams need one reliable weekly summary artifact.

## 4. Goals
- Produce one weekly digest artifact in under 20 minutes of editing.
- Standardize summary sections so output is comparable week-to-week.
- Keep a ledger of each digest run.

## 5. Non-Goals
- Full literature review automation.
- Replacing human editorial judgment.

## 6. Users and Stakeholders
- **Primary User(s):** Research team members
- **Secondary User(s):** Product and strategy leads
- **Stakeholders / Decision Makers:** Head of Research

## 7. Scope
### In Scope
- Weekly note collection, summarization draft, and publication artifact.

### Out of Scope
- Data warehouse integration.

## 8. Requirements
### Functional Requirements
1. Collect tagged notes from the week.
2. Generate a structured markdown digest draft.
3. Save digest and run ledger entry.

### Non-Functional Requirements
- Performance: First draft under 5 minutes.
- Reliability: Weekly run success >= 95%.
- Security/Privacy: No private docs in public outputs.
- Accessibility: Markdown headings and plain language.
- Maintainability: Reusable sections and naming conventions.

## 9. Success Metrics
- Digest published weekly (baseline 0, target 1/week).
- Edit time reduced (baseline 45 min, target 20 min).
- Ledger compliance (baseline 0%, target 100%).

## 10. Constraints
- Technical constraints: Markdown-first workflow.
- Time constraints: Friday 4 PM publish deadline.
- Resource constraints: One operator per run.
- Compliance constraints: Internal-only source content.

## 11. Risks and Mitigations
- **Risk:** Sparse note quality.
  **Mitigation:** Add required note tags and a pre-run quality check.

## 12. Dependencies
- Internal: Research notes folder and tagging process.
- External: None required for v0.

## 13. Milestones
- M1: PRD + repo bootstrap complete.
- M2: First successful weekly run.
- M3: Review and bank reusable digest template.

## 14. Open Questions
1. Should digest include confidence scoring?
2. Which sections are mandatory vs optional?
3. Should publication be email, wiki, or both?

## 15. Initial Artifact Plan
- `docs/prd.md`
- `docs/project-plan.md`
- `artifacts/run-ledger.md`
- `README.md`

## 16. Approval
- **Reviewer:** research-lead
- **Decision:** reviewed
- **Date:** 2026-02-16
- **Notes:** Ready for first production run.

## Initial artifacts created by workflow
- `README.md`
- `docs/prd.md`
- `docs/project-plan.md`
- `artifacts/run-ledger.md`
- `.gitignore`
- `src/`
- `tests/`

## Run ledger row example

| run_id | date_utc | operator | workflow_used | inputs_summary | outputs_created | outputs_updated | review_status | promotion_target | commit_ref | notes |
|---|---|---|---|---|---|---|---|---|---|---|
| 2026-02-16-001 | 2026-02-16 | codex | workflow-trigger-to-repo | PRD ready for paper-pulse-digest | docs/prd.md; docs/project-plan.md; artifacts/run-ledger.md | README.md | banked | S30-examples/example-weekly-digest-template.md | deadbee | Boot sequence complete; one reusable artifact promoted |

## Promotion target usage (one example)
- **Promoted file:** `docs/weekly-digest-template.md` (initially Draft in the project repo).
- **Banked location:** `S30-examples/example-weekly-digest-template.md`.
- **Recorded in ledger:** `review_status=banked` and `promotion_target=S30-examples/example-weekly-digest-template.md`.
