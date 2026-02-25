# Task List

- **Date:** 2026-02-17
- **Author:** Codex (Agent: builder-agent)
- **Status:** DRAFT

- [ ] Initialize Project structure and context
- [ ] Review and approve `S00-foundation/prd.md`
- [ ] Run first execution cycle using `S20-workflows/workflow-context-to-output.md`

## 2026-02-20 initialize_project follow-up (internal-notes-assistant)
- [ ] Define and document enforced tagging schema for ops notes.
- [ ] Select and document weekly summary storage path.
- [ ] Create markdown intake folder and sample note set.
- [ ] Implement keyword + tag search prototype and measure latency.
- [ ] Implement weekly summary markdown generation workflow.

## 2026-02-25 initialize_project follow-up (slack-live-prd-test)
- [ ] Document a standard for storing Slack trigger source identifiers in run metadata.
- [ ] Add an automated check to assert README summary marker boundary-only edits.
- [ ] Add a validation check that fails on legacy path writes (`docs/`, `artifacts/`, root `task.md`).
- [ ] Create a Day 2 verification checklist for Slack-triggered initialization runs.

## 2026-02-25 initialize_project follow-up (slack-live-prd-test-02)
- [ ] Define reproducibility acceptance criteria for consecutive Slack-triggered runs.
- [ ] Add a deterministic filename policy for sequential run evidence artifacts.
- [ ] Add a pre-write check that blocks updates if README markers are malformed.
- [ ] Add a post-run script to verify one-row ledger append behavior per invocation.
