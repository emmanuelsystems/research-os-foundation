# Project Plan

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-26

## Objective
Execute PRD-03 sensitive validation through Slack trigger and confirm `initialize_project` deterministic behavior, canonical routing, append-only evidence, and explicit sensitive-constraint warning handling.

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
- Verify no legacy writes, no protected-boundary violations, and explicit sensitive warning behavior.

## Milestones
- **M1:** Slack PRD payload accepted with all required fields.
- **M2:** Canonical artifact routing completed with marker-safe README update.
- **M3:** Sensitive-mode validation evidence captured in run report and run ledger.

## First Implementation Tasks
- [ ] Add standardized warning semantics for sensitive constraints in run reports.
- [ ] Add fixture-aware checks that verify sensitive-constraint warning presence.
- [ ] Add ledger append assertions for batched sensitive-mode Slack runs.
- [ ] Add preflight checks for canonical-path-only writes before commit.
