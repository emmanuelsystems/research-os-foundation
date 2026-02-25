# README Update Plan (OpenClaw Onboarding Hardening)

- **Date:** 2026-02-24
- **Author:** codex (openclaw runtime)
- **Status:** draft-ready

## Intent
Clarify clean OpenClaw onboarding so execution is deterministic and does not rely on tribal memory.

## Exact Install/Setup Flow Extracted
1. Clone or template the repository (`S00-foundation/START-HERE.md`).
2. Rename project folder/codename (if templating).
3. Initialize git tracking (`git init`) when starting fresh.
4. Open repo root in runtime surface (Codex/OpenClaw) (`S20-workflows/team-quickstart-and-test-guide.md`).
5. Read in order: `README.md` -> `S00-foundation/INTEGRATIONS.md` -> `S20-workflows/initialize-project-contract.md` -> `S20-workflows/validate_initialize_project.md` -> `S30-examples/expected_outputs/initialize_project_expected.md` -> `S10-primitives/RUN-REPORT-TEMPLATE.md`.

## Workspace Initialization Order (What Must Happen First)
1. Confirm canonical sections exist (`S00`, `S10`, `S20`, `S30`, `S90`).
2. Confirm bootstrap contract + save map + legacy policy are readable.
3. Confirm fixture pack + run report template are present.
4. Invoke `initialize_project` using PRD INPUT block.
5. Validate artifact routing + protected markers + ledger append behavior.

## Canonical Runtime Command References
- Invocation command: `Run initialize_project using provided PRD block.`
- Validation command block (from runbook):  
  `Run initialize_project using the provided PRD block.`  
  `Return a Run Report using S10-primitives/RUN-REPORT-TEMPLATE.md.`  
  `Save the Run Report to S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-0X-run-report.md.`

## Protected README Markers (Must Not Be Overwritten)
- `<!-- PROJECT_SUMMARY_START -->`
- `<!-- PROJECT_SUMMARY_END -->`
- Rule: Only text between these two markers may be changed by `initialize_project`.

## Undocumented Troubleshooting Assumptions (Gap List)
1. No explicit recovery path if protected markers are missing, duplicated, or malformed.
2. No explicit policy for runtime encoding issues (README currently displays mojibake in emoji sections).
3. No explicit guidance for filesystem permission anomalies (example: delete/move denial on created temp file).
4. No explicit fallback when tool discovery differs across shells/runtimes.
5. No explicit preflight command checklist for OpenClaw-specific environment verification.

## Ambiguities That Could Cause Environment Drift
1. `S00-foundation/START-HERE.md` suggests `git init` for fresh projects; team guide assumes fork/clone flow. Decision: choose one primary path and mark the other as variant.
2. `S00-foundation/onboarding.md` references `../.codex/skills/save-bank/SKILL.md`, but available skill index may differ per runtime session. Decision: define required/optional skill set at onboarding.
3. Runtime naming inconsistency (`OpenClaw later` in team guide while OpenClaw is already being validated). Decision: update to current-state language with concrete date.

## Proposed README Update Scope
1. Add explicit OpenClaw preflight block (identity, heartbeat mode, tool callability, default write path check).
2. Add single canonical onboarding path with variant notes (template vs fork).
3. Add troubleshooting section for marker integrity, encoding, permissions, and tool-path mismatch.
4. Keep all non-summary content immutable for `initialize_project` and clearly label boundary behavior.
