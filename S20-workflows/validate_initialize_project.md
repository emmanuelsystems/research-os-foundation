# Validation Runbook: initialize_project

- **Status:** draft
- **Owner:** qa-agent
- **Last Updated:** 2026-02-19

## Mac Codex App quick start for David
1. Open Codex App on Mac and select the repo root `research-os-foundation`.
2. Create a new chat session.
3. Open `S30-examples/test_prds/PRD-01-minimal.md` and copy the full `PRD INPUT` block.
4. Paste into chat and send the invocation below.
5. Save the generated Run Report to `S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-01-run-report.md`.
6. Repeat steps 3-5 a second time for PRD-01 with no contract edits between runs.

```text
Run initialize_project using the PRD INPUT block above.
Return a Run Report using S10-primitives/RUN-REPORT-TEMPLATE.md.
Save the Run Report to S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-0X-run-report.md.
```

Runtime note: this protocol is runtime-agnostic and applies to Codex App now and OpenClaw later.

## Protocol Steps
1. Create an isolated copy of the repository for each run sequence.
2. Pick the next fixture in order from `S30-examples/test_prds/`.
3. Paste the full `PRD INPUT` block into the runtime chat.
4. Send: `Run initialize_project using the provided PRD block.`
5. Collect artifact outputs at canonical paths.
6. Fill pass/fail checks in this runbook and in `S10-primitives/RUN-REPORT-TEMPLATE.md`.
7. Save one run report file per run in `S30-examples/test-runs/`.
8. Repeat for PRD-02 through PRD-05.
9. Enforce repeatability rule: PRD-01 must pass twice consecutively with no contract edits.

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
- **Warning:** Non-blocking issue that preserves contract behavior and canonical routing (for example, wording/formatting issues with complete required sections still present).
- **Fail:** Any contract or routing violation, including missing canonical artifacts, writes outside README protected markers, ledger overwrite behavior, legacy path writes, or missing required Run Report sections.

## Acceptance Checklist
| Check | Pass/Fail | Notes |
|---|---|---|
| Canonical artifacts exist in canonical paths |  |  |
| README changed only inside protected markers |  |  |
| Run ledger appended and not overwritten |  |  |
| No writes to legacy paths in `S00-foundation/legacy-artifacts.md` |  |  |
| Run Report schema is correct (`Created`, `Updated`, `Skipped`, `Warnings`, `Next`, `Verification Checks`, `Path Audit`) |  |  |
| Save-map routing followed for each created/updated path |  |  |
| PRD-01 passes twice consecutively with no contract edits |  |  |
| Output artifacts match expected minimal schema |  |  |

## Failure Modes (Top 5) and Fix Location
1. **Canonical artifact missing after bootstrap.**
Fix in: `S20-workflows/initialize-project-contract.md` (required outputs and overwrite behavior).
2. **Output written to wrong path.**
Fix in: `S00-foundation/save-map.md` (canonical routing rule).
3. **Legacy path was written (`docs/`, `artifacts/`, root `task.md`).**
Fix in: `S00-foundation/legacy-artifacts.md` and `S20-workflows/initialize-project-contract.md` (legacy policy enforcement).
4. **Expected output mismatch during scoring.**
Fix in: `S30-examples/expected_outputs/initialize_project_expected.md` (golden schema/check definitions).
5. **Run Report missing required checks or path audit detail.**
Fix in: `S10-primitives/RUN-REPORT-TEMPLATE.md` (required report schema).
