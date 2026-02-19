# Expected Outputs: initialize_project

- **Status:** draft
- **Owner:** qa-agent
- **Last Updated:** 2026-02-19

## Exact Canonical Artifact List and Paths
- `S00-foundation/prd.md`
- `S00-foundation/context.md`
- `S20-workflows/project-plan.md`
- `S20-workflows/run-ledger.md`
- `S20-workflows/task.md`
- `README.md` (summary block only)
- `.gitignore`
- `src/`
- `tests/`
- Run Report (validation runs): `S30-examples/test-runs/YYYY-MM-DD-initialize-project-prd-0X-run-report.md`

## Required Section Headers Per Artifact (Minimal Schema)
### `S00-foundation/prd.md`
- `# Product Requirements Document (PRD)`
- `## 1. Document Control`
- `## 2. PRD Source Traceability`
- `## 3. Problem Statement`
- `## 4. Goals`
- `## 10. Constraints`

### `S00-foundation/context.md`
- `# Project Context:`
- metadata block with Status, Owner, Last Updated
- `## PRD Content`

### `S20-workflows/project-plan.md`
- `# Project Plan`
- `## Objective`
- `## Phases`
- `## Milestones`
- `## First Implementation Tasks`

### `S20-workflows/run-ledger.md`
- `# Run Outputs Ledger`
- table header matching `S20-workflows/run-ledger-schema.md`
- exactly one appended row per run

### `S20-workflows/task.md`
- `# Task List`
- metadata block with Date, Author, Status
- checklist entries present

### `README.md`
- only text between `<!-- PROJECT_SUMMARY_START -->` and `<!-- PROJECT_SUMMARY_END -->` may change

### `.gitignore`
- file exists
- additive updates only

### `src/` and `tests/`
- directories exist at repo root

### Run Report
- Follows `S10-primitives/RUN-REPORT-TEMPLATE.md`.
- Includes `Created`, `Updated`, `Skipped`, `Warnings`, `Next`.
- Includes `Verification Checks`.
- Includes `Path Audit` mapping every created or updated path to the save-map rule.

## Naming Conventions
- Run Reports: `YYYY-MM-DD-initialize-project-prd-0X-run-report.md`.
- Versioned artifacts: append `-v2`, `-v3`, etc. when material changes occur.
- Use lowercase kebab-case filenames.

## Protected Marker Expectations
- README updates must remain inside protected summary markers only.
- No edits to protected sections listed in `S20-workflows/initialize-project-contract.md`.

## Evaluation References
- Run report schema: `S10-primitives/RUN-REPORT-TEMPLATE.md`
- Bank criteria: `S00-foundation/banking-definition.md`
