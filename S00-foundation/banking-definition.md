# Banking Definition

- **Status:** reviewed
- **Owner:** operations-agent
- **Last Updated:** 2026-02-19

## Purpose
Define the exact criteria for when an `initialize_project` run can be marked as `banked`.

## Bank Criteria
`Bank = PASS` only if all checks below pass:

1. All canonical startup artifacts exist in canonical paths.
2. No writes occurred in legacy paths.
3. `README.md` was updated only inside protected summary markers.
4. Naming conventions were validated.
5. Run Report schema is correct.
6. Run ledger was appended (not overwritten).
7. The appended ledger row includes `status: banked`.

## Scope Clarification
Bank status at this stage does not imply:
- Git commit completed.
- Tag creation completed.
- Release promotion completed.
