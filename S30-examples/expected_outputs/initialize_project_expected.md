# Expected Outputs: initialize_project

- **Status:** draft
- **Owner:** qa-agent
- **Last Updated:** 2026-02-18

## Canonical Artifact List and Paths
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

## Required Sections Per Artifact
### `S00-foundation/prd.md`
- Title and metadata block (Status, Owner, Last Updated).
- Sections defined in `S20-workflows/templates/prd-template.md`.

### `S00-foundation/context.md`
- Title and metadata block (Status, Owner, Last Updated).
- `PRD Content` section that embeds a full PRD based on the template.

### `S20-workflows/project-plan.md`
- Title and metadata block (Status, Owner, Last Updated).
- Objective.
- Phases.
- Milestones.
- First Implementation Tasks.

### `S20-workflows/run-ledger.md`
- Title and metadata block (Status, Owner, Last Updated).
- Table header matching `S20-workflows/run-ledger-schema.md`.
- One new appended row per run.

### `S20-workflows/task.md`
- Title and metadata block (Date, Author, Status).
- Checklist items for the first execution cycle.

### `README.md`
- Only the summary block between `<!-- PROJECT_SUMMARY_START -->` and `<!-- PROJECT_SUMMARY_END -->` is updated.

### `.gitignore`
- File exists and is only additively updated.

### `src/` and `tests/`
- Directories exist at repo root.

### Run Report
- Follows `S10-primitives/RUN-REPORT-TEMPLATE.md`.
- Includes Created, Updated, Skipped, Warnings, Next suggested action.
- Includes Path audit mapping every created or updated path to the save-map rule.

## Naming Conventions
- Run Reports: `YYYY-MM-DD-initialize-project-prd-0X-run-report.md`.
- Versioned artifacts: append `-v2`, `-v3`, etc. when material changes occur.
- Use lowercase kebab-case filenames.
