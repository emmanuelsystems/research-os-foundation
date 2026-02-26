# Project Plan

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-26

## Objective
Execute PRD-01 repeatability test A through Slack trigger and confirm deterministic `initialize_project` behavior with canonical routing and append-only evidence.

## Phase Plan

### Phase 1: Input + Contract Gate
- Validate required PRD INPUT fields from Slack batch trigger.
- Confirm contract constraints are enforceable for this run.
- Confirm README marker boundaries are intact.

### Phase 2: Deterministic Initialization
- Create versioned artifacts for PRD/context/project plan.
- Update README summary block only.
- Append one run-ledger row and one task follow-up section.

### Phase 3: Evidence + Verification
- Save one run report in canonical test-runs path.
- Complete path audit against save-map routing rules.
- Verify no legacy writes and no protected-boundary violations.

## Milestones
- **M1:** Slack PRD payload accepted with all required fields.
- **M2:** Canonical artifact routing completed with marker-safe README update.
- **M3:** Repeatability evidence captured in run report and run ledger.

## First Implementation Tasks
- [ ] Add parser guardrails for PRD INPUT batch messages.
- [ ] Add deterministic filename sequencing rules for Day 3 repeat runs.
- [ ] Add ledger append-verification automation for one-row-per-run enforcement.
- [ ] Add structured checks for canonical-path-only write attempts.
