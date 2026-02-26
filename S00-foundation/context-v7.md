# Project Context: day3-prd03-sensitive

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-26

## Trigger Inputs
- **project_name:** day3-prd03-sensitive
- **goal:** Validate sensitive-mode style PRD handling through Slack trigger.
- **owner:** ops-team
- **constraints:** canonical paths only; no legacy writes; append-only ledger; README markers protected; explicit warnings if sensitive constraints are present.
- **source:** day3 slack batch run prd03 sensitive (2026-02-26)

## Operating Context
This run validates a sensitive-mode style PRD fixture through Slack trigger to verify that stricter constraints are surfaced clearly while canonical routing and deterministic output behavior remain intact.

## Delivery Boundaries
- Keep outputs inside canonical Research OS paths only.
- Preserve all README content outside protected summary markers.
- Append to run ledger without rewriting historical rows.
- Avoid all legacy path writes (`docs/`, `artifacts/`, root `task.md`).
- Surface sensitive constraints explicitly in run warnings when applicable.

## Primary Outcomes
1. Create versioned PRD/context/project-plan artifacts for PRD-03 sensitive scenario.
2. Update README summary only in protected marker block.
3. Append one new run-ledger entry.
4. Save one new run report artifact under `S30-examples/test-runs`.

## Risks and Watchouts
- Sensitive constraint handling can drift if warning behavior is not consistently encoded in run reports.
- Missing path-audit evidence weakens deterministic and compliance claims.
