# Validation Runbook: initialize_project

- **Status:** draft
- **Owner:** qa-agent
- **Last Updated:** 2026-02-18

## Mac Codex App quick start for David
1. Open Codex App on Mac and select the repo root `research-os-foundation`.
2. Create a new chat session.
3. Paste the PRD INPUT block from `S30-examples/test_prds/PRD-01-minimal.md`.
4. Send: `Run initialize_project using the PRD INPUT block above.`
5. Save the Run Report using `S10-primitives/RUN-REPORT-TEMPLATE.md` to `S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-01-run-report.md`.
6. Repeat step 3 and 4 for the second pass of PRD-01 (pass twice in a row rule).

```text
Run initialize_project using the PRD INPUT block above.
Return a Run Report using S10-primitives/RUN-REPORT-TEMPLATE.md.
Save the Run Report to S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-0X-run-report.md.
```

## Protocol Steps
1. Create an isolated copy of the repo for the validation run.
2. Open `S30-examples/test_prds/` and choose the next PRD fixture in order.
3. Paste the PRD INPUT block into Codex App and run `initialize_project`.
4. Verify outputs against `S30-examples/expected_outputs/initialize_project_expected.md`.
5. Save a Run Report in `S30-examples/test-runs/` using `S10-primitives/RUN-REPORT-TEMPLATE.md`.
6. Append one row to `S20-workflows/run-ledger.md` per run (append-only).
7. Repeat for PRD-02 through PRD-05.
8. Run PRD-01 twice in a row with no manual edits between runs.

## Where Outputs Should Land (Canonical Paths)
- `S00-foundation/prd.md`
- `S00-foundation/context.md`
- `S20-workflows/project-plan.md`
- `S20-workflows/run-ledger.md`
- `S20-workflows/task.md`
- `README.md` (summary block only)
- `.gitignore`
- `src/`
- `tests/`
- Run Reports: `S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-0X-run-report.md`

## Warning vs Fail Definitions
- **Warning:** Non-blocking deviation that does not violate contract protections or canonical paths (for example, minor formatting gaps or missing optional context details).
- **Fail:** Any contract violation, missing required output path, protected path edit, or Run Report missing required sections (including Path audit).

## Acceptance Checklist
| Check | Pass/Fail | Notes |
|---|---|---|
| Required outputs exist at canonical paths |  |  |
| README edits limited to summary block |  |  |
| No protected paths edited |  |  |
| Run ledger append-only rule respected |  |  |
| Run Report includes Created/Updated/Skipped/Warnings/Next |  |  |
| Run Report includes Path audit mapped to save-map |  |  |
| Path audit covers every created/updated path |  |  |
| PRD-01 passes twice in a row with no manual edits |  |  |
| Warnings are documented with justification |  |  |
| Output artifacts match required sections |  |  |

## Failure Modes (Top 5) and Fix Location
1. **Missing required input fields in PRD fixtures.**
Fix in: `S30-examples/test_prds/PRD-0X-*.md`
2. **Outputs written to non-canonical paths.**
Fix in: `S00-foundation/save-map.md`
3. **README edited outside summary block.**
Fix in: `S20-workflows/initialize-project-contract.md`
4. **Run Report missing required sections or Path audit.**
Fix in: `S10-primitives/RUN-REPORT-TEMPLATE.md`
5. **Run ledger not append-only or missing a row.**
Fix in: `S20-workflows/run-ledger-schema.md`
