# Living Files Policy

- **Status:** banked
- **Owner:** foundation-maintainers
- **Last Updated:** 2026-02-16

## Purpose
Define how artifacts evolve from draft work into durable system knowledge.

## Status States
Every living file must carry one status value in its metadata/header.

1. **draft**
   - Created during active work.
   - Not yet validated against rubric/checklist.
   - Can change rapidly.
2. **reviewed**
   - Checked by a human or designated QA agent.
   - Meets format and quality requirements.
   - Ready for promotion decisions.
3. **banked**
   - Accepted as reusable system knowledge.
   - Stored in its canonical section (`S10`, `S20`, or `S30`).
   - Changes require version/changelog updates where applicable.

## File Naming Rules
1. Use lowercase kebab-case for filenames.
2. Prefix workflow files with `workflow-`.
3. Prefix example files with `example-`.
4. Use `-template` suffix for reusable templates.
5. Avoid ambiguous names like `notes.md`, `final.md`, or `misc.md`.
6. If versioning is needed in filename, use `-vX-Y-Z` (e.g., `skill-save-bank-v1-0-0.md`).

## Promotion Rules

### Promote to `S30-examples/` when:
- The file is a high-quality exemplar of output form.
- It teaches by demonstration.
- It is stable enough to imitate directly.

### Promote to `S10-primitives/` when:
- The content defines system-level concepts, schemas, or rules.
- It applies broadly across many projects and workflows.
- It changes slowly and should be treated as a reference primitive.

### Promote to `S20-workflows/` when:
- The content is a repeatable, ordered procedure.
- It can be executed step-by-step by humans or agents.
- It includes clear inputs and outputs.

## Minimum Metadata for Living Files
Include at top of file (where practical):
- **Status:** draft/reviewed/banked
- **Owner:** person or agent role
- **Last Updated:** YYYY-MM-DD

## Governance
- Files can only move to **banked** after review.
- Banked files should be referenced by workflows/skills, not duplicated.
- Superseded banked files should be archived or marked deprecated with replacement links.
