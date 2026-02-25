# Slack -> OpenClaw Trigger Task Breakdown (Day 2)

- **Date:** 2026-02-25
- **Owner:** operations-agent
- **Status:** ready for execution
- **Goal:** Turn Slack messages into canonical `initialize_project` runs in OpenClaw with deterministic outputs.

## Task 1: Trigger Contract Definition
- [ ] Define approved Slack trigger commands and payload schema.
- [ ] Map each command to one OpenClaw action only.
- [ ] Freeze required input fields: `project_name`, `goal`, `owner`, `constraints`, `source`.
- [ ] Define invalid-input behavior (reject + guidance, no file writes).

Acceptance criteria:
- Command table exists with examples.
- Input validator rejects missing required fields.
- Invocation remains runtime-agnostic:
  - `Run initialize_project using provided PRD block.`

## Task 2: Slack Authentication and Endpoint Setup
- [x] Select trigger surface: Slack bot or webhook endpoint.
- [x] Configure signing secret/token validation.
- [x] Validate gateway reachability and auth token in runtime status.
- [ ] Implement replay protection (timestamp + signature checks).
- [ ] Log request metadata (channel, user, timestamp, request id).
- [ ] Ensure gateway service runs continuously (not stopped/ready only).

Acceptance criteria:
- Unsigned/invalid requests are rejected.
- Valid requests are accepted and assigned a deterministic run id.
- Request metadata is captured for audit.
Current validation evidence:
- `openclaw status` shows `Slack | ON | OK`, `tokens ok`, `accounts 1/1`, and active slack session.
- `openclaw status` shows gateway `reachable` with `auth token`.
- See `S30-examples/test-runs/2026-02-25-openclaw-slack-connection-validation.md`.

## Task 3: Message Parser and PRD Block Builder
- [ ] Parse Slack message into PRD input fields.
- [ ] Normalize field formatting to canonical block format.
- [ ] Preserve original Slack message as `source` traceability text.
- [ ] Fail closed if parser cannot produce all required fields.

Acceptance criteria:
- Parser output matches `S30-examples/test_prds/` input style.
- Missing field returns warning response, no `initialize_project` run.
- Parsed block is stored in run evidence artifact.

## Task 4: OpenClaw Invocation Adapter
- [ ] Send normalized PRD block to OpenClaw with canonical invocation text.
- [ ] Enforce one run per trigger request id.
- [ ] Capture OpenClaw response and run metadata (start/end time, status).
- [ ] Return deterministic Slack acknowledgment (accepted/running/completed/failed).

Acceptance criteria:
- Each trigger creates at most one run.
- OpenClaw call path is logged with run id.
- Slack receives status response with run id.

## Task 5: Canonical Write and Path Audit Guardrail
- [ ] Validate outputs only target canonical routes from `S00-foundation/save-map.md`.
- [ ] Block/flag legacy write attempts (`docs/`, `artifacts/`, root `task.md`).
- [ ] Enforce README marker boundary checks.
- [ ] Enforce ledger append-only check before run success.

Acceptance criteria:
- Any path violation marks run FAIL.
- README out-of-bound write marks run FAIL.
- Ledger overwrite attempt marks run FAIL.

## Task 6: Run Report and Ledger Integration
- [ ] Generate Run Report using `S10-primitives/RUN-REPORT-TEMPLATE.md`.
- [ ] Save report to `S30-examples/test-runs/YYYY-MM-DD-openclaw-prd-0X-run-0Y.md`.
- [ ] Append single row to `S20-workflows/run-ledger.md`.
- [ ] Include complete Path Audit for created/updated files.

Acceptance criteria:
- Run report contains required sections and verification checks.
- Ledger row appended exactly once per successful run.
- Naming convention is lowercase kebab-case.

## Task 7: Slack Result Message Contract
- [ ] Define completion message format:
  - run id,
  - status,
  - key outputs,
  - pass/fail checks,
  - link/path to run report.
- [ ] Define failure message format with remediation hint.
- [ ] Include warning block when run is non-destructive validation only.

Acceptance criteria:
- Slack message reflects final run status accurately.
- Operator can locate run report and ledger row from Slack message alone.

## Task 8: Controlled Test Sequence
- [ ] Test A: valid PRD-01 Slack trigger.
- [ ] Test B: valid PRD-02 Slack trigger.
- [ ] Test C: missing required field (expect reject, no writes).
- [ ] Test D: malformed payload/signature failure (expect reject).
- [ ] Test E: duplicate trigger idempotency check (expect no duplicate run).

Acceptance criteria:
- A and B PASS all canonical checks.
- C and D produce zero repo writes.
- E does not append duplicate ledger rows.

## Task 9: Day 2 Exit Criteria
- [ ] At least one end-to-end Slack -> OpenClaw run completed with PASS.
- [ ] All path and protection checks PASS.
- [ ] Run report + ledger evidence saved.
- [ ] Open issues recorded with owner and next action.

## Operator Execution Order (Recommended)
1. Task 1 -> 3 (contract, auth, parser)
2. Task 4 -> 5 (invocation + guardrails)
3. Task 6 -> 7 (evidence + Slack response)
4. Task 8 (tests)
5. Task 9 (closeout)
