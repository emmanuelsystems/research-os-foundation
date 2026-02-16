# Run Outputs Ledger Schema

- **Status:** reviewed
- **Owner:** operations-agent
- **Last Updated:** 2026-02-16

## Purpose
Track what each run produced, where outputs were saved, and what was promoted to banked knowledge.

## Storage
- Default path: `artifacts/run-ledger.md` inside each project repository.
- One row per run.

## Required Columns
1. **run_id**: Unique identifier (e.g., `2026-02-16-001`).
2. **date_utc**: Run date in `YYYY-MM-DD`.
3. **operator**: Human or agent that executed the run.
4. **workflow_used**: Workflow or skill invoked (e.g., `workflow-context-to-output`).
5. **inputs_summary**: Short description of trigger/context.
6. **outputs_created**: File paths created.
7. **outputs_updated**: File paths modified.
8. **review_status**: `draft`, `reviewed`, or `banked`.
9. **promotion_target**: `none`, `S10`, `S20`, `S30`, or specific path.
10. **commit_ref**: Git commit hash associated with the run.
11. **notes**: Decisions, blockers, or follow-up items.

## Markdown Table Template

| run_id | date_utc | operator | workflow_used | inputs_summary | outputs_created | outputs_updated | review_status | promotion_target | commit_ref | notes |
|---|---|---|---|---|---|---|---|---|---|---|
| 2026-02-16-001 | 2026-02-16 | codex | workflow-context-to-output | Initial feature request | docs/spec.md; artifacts/result.md | README.md | reviewed | S30 | abc1234 | Ready for banking |

## Entry Rules
- Add a new entry immediately after each run.
- Use semicolon-separated file paths for multi-file fields.
- Do not delete historical rows; append only.
- If review is pending, set `review_status` to `draft` and update later.
- During the **Bank** step, update any row promoted to `banked` with final `promotion_target` and `commit_ref`.
