# Repo Structure Validation (Canonical Path Discipline)

- **Date:** 2026-02-24
- **Author:** codex (openclaw runtime)
- **Status:** completed
- **Mode:** non-destructive validation

## Scope
Validate startup artifacts, save routing controls, and validation packs before PRD execution proofs.

## Required Path Checks
| Path | Exists | Readable | Result |
|---|---|---|---|
| `S00-foundation/prd.md` | yes | yes | PASS |
| `S00-foundation/context.md` | yes | yes | PASS |
| `S20-workflows/project-plan.md` | yes | yes | PASS |
| `S20-workflows/run-ledger.md` | yes | yes | PASS |
| `S20-workflows/task.md` | yes | yes | PASS |
| `S00-foundation/save-map.md` | yes | yes | PASS |
| `S00-foundation/legacy-artifacts.md` | yes | yes | PASS |
| `S30-examples/test_prds/` | yes | n/a (dir) | PASS |
| `S20-workflows/validate_initialize_project.md` | yes | yes | PASS |
| `S10-primitives/RUN-REPORT-TEMPLATE.md` | yes | yes | PASS |

## What Must Be True by Default
1. Canonical startup artifacts remain addressable at canonical paths.
2. Save-map routing governs active writes for initialize flows.
3. Legacy paths remain read-only compatibility surfaces.
4. Ledger behavior is append-only, never overwrite.

## Divergence Risk Findings
1. `S20-workflows/project-plan.md` still lists legacy-path tasks (`docs/prd.md`, `artifacts/run-ledger.md`), which conflicts with canonical save-map.
2. Legacy files are present by design, but policy must continue to prevent new writes there.
3. Root-level `task.md` exists as legacy compatibility path and can be accidentally targeted by naive tooling.

## Legacy Path Write Snapshot
Observed last-write timestamps for legacy paths are dated 2026-02-17 (no evidence of today writes), supporting current compliance:
- `docs/prd.md`
- `docs/project-plan.md`
- `artifacts/run-ledger.md`
- `task.md` (root)

## Validation Conclusion
Canonical structure and required validation assets are intact and readable. Primary drift risk is procedural: legacy references still appear in planning content and should be cleaned to prevent accidental non-canonical routing.
