# Team Quickstart and Test Guide

- **Status:** draft
- **Owner:** operations-agent
- **Last Updated:** 2026-02-20

## Purpose
Give the team one step-by-step path to understand how Research OS Foundation works and how to run repeatable `initialize_project` validation tests.

## How Research OS Foundation Works
1. **Structure first:** work is organized by section (`S00`, `S10`, `S20`, `S30`, `S90`) so humans and agents route outputs consistently.
2. **Contract first:** `initialize_project` behavior is governed by `S20-workflows/initialize-project-contract.md`.
3. **Routing first:** canonical output paths are governed by `S00-foundation/save-map.md`.
4. **Validation first:** runs are scored using `S10-primitives/RUN-REPORT-TEMPLATE.md`.
5. **Banking first:** `banked` status is earned only by passing `S00-foundation/banking-definition.md`.

## Core Files to Read (In Order)
1. `README.md`
2. `S00-foundation/INTEGRATIONS.md`
3. `S20-workflows/initialize-project-contract.md`
4. `S20-workflows/validate_initialize_project.md`
5. `S30-examples/expected_outputs/initialize_project_expected.md`
6. `S10-primitives/RUN-REPORT-TEMPLATE.md`

## Team Setup (Fork + Local)
1. Fork the repository on GitHub.
2. Clone your fork locally.
3. Create a working branch for testing (recommended).
4. Open the repo root in your runtime (Codex App now, OpenClaw later).
5. Confirm these paths exist before running tests:
   - `S30-examples/test_prds/`
   - `S20-workflows/validate_initialize_project.md`
   - `S30-examples/expected_outputs/initialize_project_expected.md`
   - `S10-primitives/RUN-REPORT-TEMPLATE.md`

## Test Protocol (Runtime-Agnostic)
1. Pick a fixture from `S30-examples/test_prds/`.
2. Copy the entire `PRD INPUT` block.
3. Paste into chat and run:

```text
Run initialize_project using the provided PRD block.
Return a Run Report using S10-primitives/RUN-REPORT-TEMPLATE.md.
Save the Run Report to S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-0X-run-report.md.
```

4. Verify outputs at canonical paths:
   - `S00-foundation/prd.md`
   - `S00-foundation/context.md`
   - `S20-workflows/project-plan.md`
   - `S20-workflows/run-ledger.md`
   - `S20-workflows/task.md`
   - `README.md` (summary markers only)
   - `.gitignore`
   - `src/`
   - `tests/`
5. Fill the Run Report using `S10-primitives/RUN-REPORT-TEMPLATE.md`.
6. Record pass/fail for each verification check and complete the path audit.

## Required Test Sequence
1. Run `PRD-01-minimal.md` twice in a row with no contract edits.
2. Run once each for:
   - `PRD-02-standard.md`
   - `PRD-03-sensitive.md`
   - `PRD-04-ambiguous.md`
   - `PRD-05-stress.md`

## Pass/Fail Rules
- **PASS** requires all of the following:
  - Canonical artifact set exists in canonical paths.
  - README changes are only inside protected markers.
  - Ledger behavior is append-only.
  - No writes to legacy paths.
  - Run Report has required sections and complete path audit.
  - Save-map routing is followed for each created/updated path.
- **WARNING** is non-blocking and does not violate contract/routing rules.
- **FAIL** is any contract, routing, protection, or schema violation.

## What Good Looks Like
- Each run produces a saved Run Report in `S30-examples/test-runs/`.
- Reports show explicit verification outcomes, not implicit assumptions.
- Failures are mapped to the correct fix location (contract, save-map, legacy policy, expected outputs, or run report template).
