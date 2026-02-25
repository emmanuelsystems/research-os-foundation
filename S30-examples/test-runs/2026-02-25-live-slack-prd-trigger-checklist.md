# Live Slack -> PRD Trigger Checklist

- **Date:** 2026-02-25
- **Owner:** ops-team
- **Status:** ready to run
- **Goal:** Trigger `initialize_project` from Slack and verify canonical repo outputs.

## Preconditions (Current State)
- [x] OpenClaw running and responding in Slack.
- [x] Slack channel connected (`ON/OK` from prior status checks).
- [x] Trigger phrase spec exists: `S20-workflows/slack-trigger-spec.md`.

## Step 1: Post the Trigger in Slack
Post this exact message in your OpenClaw-connected channel/thread:

```text
Run initialize_project using the provided PRD block below.

PRD INPUT
project_name: slack-live-prd-test
goal: Validate end-to-end Slack-triggered PRD initialization into canonical Research OS paths.
owner: ops-team
constraints: no legacy path writes; append-only ledger; README markers protected.
source: slack live trigger test on 2026-02-25

PRD:
# Product Requirements Document (PRD)
## Summary
Run a live Slack-triggered initialize_project execution and verify canonical artifact routing.

## Problem Statement
Need proof that Slack can trigger OpenClaw and persist outputs to correct repo paths.

## Goals
- Trigger initialize_project from Slack message.
- Generate/update canonical startup artifacts.
- Produce run evidence for Day 2.

## Non-Goals
- External integrations beyond Slack trigger.
- Full production hardening in this run.

## Users and Stakeholders
- Primary Users: ops-team
- Stakeholders: platform-owner

## Requirements
### Functional
1. Parse PRD INPUT from Slack message.
2. Execute initialize_project.
3. Save outputs to canonical paths.

### Non-Functional
- Deterministic routing per save-map.
- No writes to legacy paths.

## Constraints
- Must preserve README protected marker boundaries.
```

## Step 2: Wait for OpenClaw Response
- [ ] Confirm OpenClaw acknowledges run start/completion in Slack.
- [ ] Capture Slack timestamp/thread link as evidence.

## Step 3: Repo Validation (Run Immediately After Slack Response)
- [ ] Check modified files:
  - `git status --short`
- [ ] Verify canonical outputs changed only where expected:
  - `S00-foundation/prd*.md`
  - `S00-foundation/context*.md`
  - `S20-workflows/project-plan*.md`
  - `S20-workflows/task.md`
  - `S20-workflows/run-ledger.md`
  - `README.md` summary block only
- [ ] Verify no legacy writes:
  - `docs/prd.md`
  - `docs/project-plan.md`
  - `artifacts/run-ledger.md`
  - root `task.md`

## Step 4: Save Run Evidence
- [ ] Save run report to:
  - `S30-examples/test-runs/2026-02-25-openclaw-slack-prd-live-run-01.md`
- [ ] Append one ledger row with new run id.
- [ ] Record pass/fail for:
  - canonical artifact set,
  - README marker protection,
  - ledger append-only behavior,
  - legacy write check,
  - save-map routing followed.

## Pass Criteria
- One Slack message triggers exactly one `initialize_project` run.
- Canonical paths updated correctly.
- No legacy path writes.
- Run report + ledger evidence saved.
