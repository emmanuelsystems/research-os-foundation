# Day 1 Implementation Gameplan (2026-02-24)

- **Status:** draft
- **Owner:** operations-agent
- **Sprint:** OpenClaw + Trigger Pipeline + PRD Validation

## Day 1 Goal
Stabilize runtime environment, verify baseline repo behavior in OpenClaw, and produce reproducible evidence for tomorrow's trigger work.

## Definition of Done (Day 1)
1. OpenClaw baseline checks are completed and documented.
2. README update scope for OpenClaw setup is drafted and ready to implement.
3. Repo structure validation is completed against canonical paths.
4. 1-2 PRD runs are executed in OpenClaw with saved Run Reports.
5. Day 1 progress summary is ready for manual Slack posting.

## Execution Plan

## Block 1: Environment Baseline
1. Validate OpenClaw identity and heartbeat checks.
2. Validate tool discovery and callable tools.
3. Run one basic terminal command through OpenClaw to confirm command execution path.
4. Record outcomes in a short note file.

Output:
- `S30-examples/test-runs/2026-02-24-openclaw-environment-baseline.md`

## Block 2: README Improvement Draft
1. Draft exact sections needed for OpenClaw onboarding:
   - install
   - workspace initialization
   - runtime command references
   - troubleshooting
2. Map where each section should live in `README.md`.
3. List unresolved gaps or assumptions.

Output:
- `S30-examples/test-runs/2026-02-24-readme-update-plan.md`

## Block 3: Repo Structure Validation
1. Validate canonical startup artifact paths exist and are readable:
   - `S00-foundation/prd.md`
   - `S00-foundation/context.md`
   - `S20-workflows/project-plan.md`
   - `S20-workflows/run-ledger.md`
   - `S20-workflows/task.md`
2. Confirm save routing references are intact:
   - `S00-foundation/save-map.md`
   - `S00-foundation/legacy-artifacts.md`
3. Confirm test pack and validation docs exist:
   - `S30-examples/test_prds/`
   - `S20-workflows/validate_initialize_project.md`
   - `S10-primitives/RUN-REPORT-TEMPLATE.md`

Output:
- `S30-examples/test-runs/2026-02-24-repo-structure-validation.md`

## Block 4: Basic OpenClaw PRD Runs
1. Run `PRD-01-minimal.md` once.
2. Run `PRD-02-standard.md` once (or repeat PRD-01 if time is constrained).
3. For each run, enforce report schema and path audit using:
   - `S10-primitives/RUN-REPORT-TEMPLATE.md`
4. Verify each run for:
   - canonical artifact set
   - README protected markers only
   - ledger append-only behavior
   - no legacy path writes
   - save-map routing followed

Outputs:
- `S30-examples/test-runs/2026-02-24-openclaw-prd-01-run-01.md`
- `S30-examples/test-runs/2026-02-24-openclaw-prd-02-run-01.md`

## Block 5: End-of-Day Summary + Slack Draft
1. Summarize what passed, warned, and failed.
2. List top blockers with owner and next action.
3. Draft manual Slack update message.

Output:
- `S30-examples/test-runs/2026-02-24-day-01-summary.md`

## Command to Use During PRD Runs
```text
Run initialize_project using the provided PRD block.
Return a Run Report using S10-primitives/RUN-REPORT-TEMPLATE.md.
Save the Run Report to S30-examples/test-runs/YYYY-MM-DD-openclaw-prd-0X-run-0Y.md.
```

## Risks to Watch Today
1. OpenClaw tool resolution failures.
2. README update scope creep.
3. False pass without complete path audit evidence.
4. Mixed baseline from running in a dirty workspace.

## If Blocked
1. Capture blocker in Day 1 summary with exact error.
2. Continue with remaining blocks that do not depend on the blocker.
3. Do not change contracts or save-map today unless blocker is directly caused by a contract defect.
