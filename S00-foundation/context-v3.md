# Project Context: slack-live-prd-test

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-25

## Trigger Inputs
- **project_name:** slack-live-prd-test
- **goal:** Validate end-to-end Slack-triggered PRD initialization into canonical Research OS paths.
- **owner:** ops-team
- **constraints:** no legacy path writes; append-only ledger; README markers protected.
- **source:** slack live trigger test on 2026-02-25

## Operating Context
This run validates that a Slack-originated PRD block can trigger initialization behavior and route artifacts only to canonical paths defined by the save-map.

## Delivery Boundaries
- Route outputs only to canonical paths.
- Do not write to legacy artifact locations.
- Preserve README content outside the protected summary markers.
- Keep run-ledger history append-only.

## Primary Outcomes
1. Create versioned PRD/context/project-plan artifacts for this run.
2. Update README summary within marker boundaries only.
3. Append run evidence to canonical run ledger.
4. Produce Day 2 run evidence artifact in test runs.

## Risks and Watchouts
- Slack identity or metadata ambiguity may weaken source traceability if message IDs are not captured.
- Marker boundary violations in README would invalidate the run.
- Any write to `docs/`, `artifacts/`, or root `task.md` would fail legacy compliance.