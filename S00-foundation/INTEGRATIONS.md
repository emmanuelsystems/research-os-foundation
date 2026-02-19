# Integrations

- **Status:** reviewed
- **Owner:** operations-agent
- **Last Updated:** 2026-02-19

## Purpose
Define how external trigger surfaces map into the canonical bootstrap flow without changing artifact routing, protections, or contract behavior.

## Supported Trigger Surfaces
- **Phase 1 (Primary):** Notion PRD
- **Phase 2 (Documented Only):** Slack PRD
- **Phase 3 (Documented Only):** Telegram PRD
- **Execution Surface:** Codex App is a valid runtime surface
- **Execution Surface:** OpenClaw is a valid runtime surface

All surfaces route to the same `initialize_project` contract behavior.

## PRD Input Contract
- PRD input format is invariant across trigger surfaces.
- Required fields remain:
  - `project_name`
  - `goal`
  - `owner`
  - `constraints`
  - `source`
- Canonical PRD input block format for operator paste/testing is documented in:
  - `S30-examples/test_prds/PRD-01-minimal.md`
  - `S20-workflows/initialize-project-contract.md`

## Bootstrap Invocation
Standard invocation:
`Run initialize_project using provided PRD block.`

No UI assumptions are allowed. The invocation contract is text-only and runtime-agnostic.

## Artifact Guarantees
After successful bootstrap, the canonical artifact set must exist at:
- `S00-foundation/prd.md`
- `S00-foundation/context.md`
- `S20-workflows/project-plan.md`
- `S20-workflows/run-ledger.md`
- `S20-workflows/task.md`
- `README.md` (summary markers only)
- `.gitignore`
- `src/`
- `tests/`

## Run Report Contract
Each bootstrap run must include these sections:
1. **Created**
2. **Updated**
3. **Skipped**
4. **Warnings**
5. **Next**
6. **Path Audit**
7. **Canonical Naming Check**
8. **Legacy Write Check**

Run report structure is defined in `S10-primitives/RUN-REPORT-TEMPLATE.md`.

## Banking Definition
Banking criteria are defined in `S00-foundation/banking-definition.md`.
