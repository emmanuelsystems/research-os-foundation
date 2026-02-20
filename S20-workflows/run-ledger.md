# Run Outputs Ledger

- **Status:** draft
- **Owner:** operations-agent
- **Last Updated:** 2026-02-17

## Purpose
Track what each run produced, what changed, and what was promoted to reusable knowledge.

| run_id | date_utc | operator | workflow_used | inputs_summary | outputs_created | outputs_updated | review_status | promotion_target | commit_ref | notes |
|---|---|---|---|---|---|---|---|---|---|---|
| 2026-02-17-001 | 2026-02-17 | codex | initialize_project; workflow-trigger-to-repo | Bootstrap from existing foundation context and startup workflows | docs/prd.md; docs/project-plan.md; artifacts/run-ledger.md; S00-foundation/context.md; task.md; .gitignore | README.md | draft | none | uncommitted | Initial project artifacts created. Awaiting PRD review and first execution run. |
| 2026-02-17-002 | 2026-02-17 | codex | initialize_project (test-case-1) | Minimal PRD internal tool conformance validation | S30-examples/test-runs/minimal-prd-run-report.md | S20-workflows/run-ledger.md | reviewed | none | uncommitted | Non-destructive contract validation; canonical paths and README boundary checks passed. |
| 2026-02-17-003 | 2026-02-17 | codex | initialize_project (test-case-2) | Client-like constrained project conformance validation | S30-examples/test-runs/client-like-project-run-report.md | S20-workflows/run-ledger.md | reviewed | none | uncommitted | Non-destructive contract validation; path and report requirements passed. |
| 2026-02-17-004 | 2026-02-17 | codex | initialize_project (test-case-3) | Sensitive mode strict-permission conformance validation | S30-examples/test-runs/sensitive-mode-run-report.md | S20-workflows/run-ledger.md | reviewed | none | uncommitted | Non-destructive contract validation; protected path policy checks passed. |
| 2026-02-20-005 | 2026-02-20 | openclaw | initialize_project | internal-notes-assistant bootstrap from provided PRD block | S00-foundation/prd-v2.md; S00-foundation/context-v2.md; S20-workflows/project-plan-v2.md; S30-examples/test-runs/internal-notes-assistant-run-report.md | README.md; S20-workflows/task.md; S20-workflows/run-ledger.md | draft | none | uncommitted | Applied contract overwrite policy using versioned artifacts; README summary updated within protected markers only. |
