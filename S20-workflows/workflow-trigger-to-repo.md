# Workflow: Trigger to Repo

- **Status:** reviewed
- **Owner:** builder-agent
- **Last Updated:** 2026-02-16

## Goal
Turn an initial trigger (idea/request) into a ready-to-run project repository with a standard startup artifact set.

## Inputs
1. **PRD Text**: The current draft requirement narrative in plain text or markdown.
2. **PRD Source**: Where the PRD text came from (chat transcript, ticket, notes file, workshop doc, or linked specification).
3. **Project Metadata**: Project name, owner, objective, timeline, and delivery constraints.

## Process
1. **Create PRD**
   * Create `docs/prd.md` from `S20-workflows/templates/prd-template.md`.
   * Record PRD source references in the PRD (links, filenames, and/or transcript IDs).
2. **Create Project Folder**
   * Create a new top-level project directory using kebab-case.
   * Add standard startup folders (`docs/`, `artifacts/`, `src/`, `tests/`) unless a domain-specific structure is already defined.
3. **Create Initial Artifacts**
   * Save `docs/prd.md`.
   * Save `docs/project-plan.md` with phases, milestones, and first implementation tasks.
   * Save `artifacts/run-ledger.md` initialized from `S20-workflows/run-ledger-schema.md`.
   * Save project `README.md` with purpose, setup, and operating loop reference.
4. **Initialize Repo**
   * Initialize Git if missing.
   * Create `.gitignore` appropriate for stack/tooling.
   * Make the initial commit with the startup artifact set.
5. **Open in Codex**
   * Open the project root in Codex.
   * Confirm `AGENTS.md` (or equivalent agent entrypoint) exists.
   * Start the first execution cycle using `workflow-context-to-output.md`.

## Outputs
A consistent startup file set is created:
- `README.md`
- `docs/prd.md`
- `docs/project-plan.md`
- `artifacts/run-ledger.md`
- `.gitignore`
- `src/`
- `tests/`

Also produced:
- Initial commit capturing startup artifacts.
- Codex-ready workspace with a clear first-run path.

## Quality Gate
- [ ] PRD includes measurable success criteria and source traceability.
- [ ] Folder and file names follow living file naming conventions.
- [ ] Run ledger is initialized before first implementation run.
- [ ] Repository is committed and can be cloned and run by another contributor.
