# Initialize Project Contract

- **Status:** reviewed
- **Owner:** builder-agent
- **Last Updated:** 2026-02-19

## Purpose
Define the canonical behavior for the `initialize_project` command so execution is deterministic and reviewable.

## Scope
This contract is the single source of truth for `initialize_project` inputs, outputs, protections, overwrite policy, and run reporting.
This contract is runtime-agnostic and applies regardless of trigger surface or agent runtime.

## Canonical References
- Core integration seam: `S00-foundation/INTEGRATIONS.md`
- Save routing table: `S00-foundation/save-map.md`
- Legacy compatibility policy: `S00-foundation/legacy-artifacts.md`
- Bank criteria: `S00-foundation/banking-definition.md`
- Run report schema template: `S10-primitives/RUN-REPORT-TEMPLATE.md`

## Runtime-Agnostic Invocation
- Standard text invocation: `Run initialize_project using provided PRD block.`
- No runtime-specific UI assumptions are allowed.
- Trigger surface mappings are defined in `S00-foundation/INTEGRATIONS.md`.

## Required Inputs
1. **project_name**: Kebab-case project identifier.
2. **goal**: One-sentence objective for the project.
3. **owner**: Responsible person, role, or team.
4. **constraints**: Delivery, technical, resource, or compliance constraints.
5. **source**: PRD source reference (chat/ticket/file/link/workshop notes).

## Input Validation Rules
- If any required input is missing, stop before file edits.
- Return a Run Report with missing fields listed under **Warnings**.
- Do not silently infer `source` if none is provided.

## Required Outputs (Must Exist After Successful Run)
- `S00-foundation/prd.md`
- `S00-foundation/context.md`
- `S20-workflows/project-plan.md`
- `S20-workflows/run-ledger.md`
- `S20-workflows/task.md`
- `README.md` (only summary block is writable; see markers below)
- `.gitignore`
- `src/`
- `tests/`

## README Update Boundary
`initialize_project` may only update text between:
- `<!-- PROJECT_SUMMARY_START -->`
- `<!-- PROJECT_SUMMARY_END -->`

All text outside this block is treated as read-only for this command.

## Do Not Touch List
- `S10-primitives/**`
- `S20-workflows/templates/**`
- `S20-workflows/workflow-*.md`
- `.codex/skills/**` (except explicit maintenance requests)
- `.git/**`
- `S90-assets/**`

## Overwrite Policy
- `S20-workflows/run-ledger.md`: **append-only** (add one row per run; never delete historical rows).
- `S20-workflows/task.md`: update checklist by appending new tasks; do not remove completed task history.
- `S00-foundation/prd.md`, `S00-foundation/context.md`, `S20-workflows/project-plan.md`:
  - If missing: create.
  - If present and materially different: create a versioned file (`-v2`, `-v3`, etc.) rather than destructive overwrite.
- `README.md`: update only within protected summary block.
- `.gitignore`: additive updates only; do not remove existing lines unless explicitly requested.

## Run Report (Required Output Format)
Every `initialize_project` run must end with:

1. **Created:** semicolon-separated paths created this run.
2. **Updated:** semicolon-separated paths updated this run.
3. **Skipped:** protected or intentionally unchanged paths.
4. **Warnings:** missing inputs, overwrite prevention events, or policy conflicts.
5. **Next:** first executable task after initialization.
6. **Path audit:** map each created or updated path to the canonical routing rule in `S00-foundation/save-map.md`.
7. **Canonical Naming Check:** PASS or FAIL.
8. **Legacy Write Check:** PASS or FAIL.

Run reports must follow `S10-primitives/RUN-REPORT-TEMPLATE.md`.

## Source Routing
Use `S00-foundation/save-map.md` as the routing table for artifact destinations.
Path audits in the Run Report must reference the applicable save-map rules.

## Banking Gate
Bank state definitions and pass criteria are governed by `S00-foundation/banking-definition.md`.
