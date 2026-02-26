# Product Requirements Document (PRD)

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-26

## 1. Document Control
- **Project Name:** day3-prd03-sensitive
- **Owner:** ops-team
- **Version:** v0.1.0
- **Decision State:** draft

## 2. PRD Source Traceability
- **Primary Source:** day3 slack batch run prd03 sensitive (2026-02-26)
- **Source Input Block Fields:** `project_name`, `goal`, `owner`, `constraints`, `source`, `PRD`

## 3. Summary
Execute PRD-03 sensitive validation run via Slack trigger.

## 4. Problem Statement
Need assurance that stricter constraints do not break canonical behavior.

## 5. Goals
- Trigger initialize_project.
- Preserve canonical routing and reporting.
- Produce run evidence.

## 6. Non-Goals
- Security system implementation.

## 7. Users and Stakeholders
- **Primary Users:** ops-team
- **Stakeholders:** compliance-owner

## 8. Requirements
### Functional
1. Parse PRD INPUT.
2. Execute initialize_project.
3. Save run report and ledger row.

### Non-Functional
- Deterministic schema usage.
- No legacy writes.

## 9. Success Metrics
- One run report exists in canonical test-runs path for this invocation.
- Exactly one new append-only run-ledger row is added.
- Canonical naming and legacy write checks pass.
- Sensitive constraints are explicitly surfaced in run warnings when present.

## 10. Constraints
- Canonical paths only.
- No legacy writes.
- Append-only ledger.
- README summary markers protected.
- Explicit warnings if sensitive constraints are present.

## 11. Risks
- Sensitive-mode constraints may be inconsistently surfaced unless warnings are standardized.

## 12. Open Questions
1. Should sensitive constraints be represented by a structured warning code in run reports?
2. Should sensitive-mode fixture checks be added to automated validation scripts?
