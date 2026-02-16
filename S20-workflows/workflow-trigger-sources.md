# Trigger Sources

## Overview
The PRD is the trigger object for starting work. The source of that PRD can vary (Notion, Slack, or manual entry), but each source should map into the same Trigger-to-Repo workflow and produce the same startup artifacts.

## 1) Notion (PRD database)
### Assumptions
- A Notion database exists for PRDs.
- Each row represents one project request.
- The team can read/write PRD status and repository metadata.

### Minimal PRD fields
- Title
- Summary
- Owner
- Status
- Repo URL
- CreatedAt

### Trigger event definition
- Trigger when `Status` changes to `Ready`.

### Expected automation steps
1. Create (or select) the target repository.
2. Copy PRD fields into `docs/prd.md` using `/S20-workflows/templates/prd-template.md`.
3. Create initial issues/tasks from requirements and milestones.
4. Create a Codex kickoff file (context + first-run checklist).

### Manual fallback (if automation is not wired)
1. Export/copy the Notion PRD content.
2. Run `/S20-workflows/workflow-trigger-to-repo.md` manually.
3. Paste PRD into `docs/prd.md` and commit startup files.
4. Open in Codex and run first cycle.

## 2) Slack (channel or slash command)
### Message format example
```text
/new-project
Title: Weekly Research Digest
Summary: Automate digest creation from tagged notes.
Owner: ops-lead
Status: Ready
```

### Trigger event definition
- Trigger on slash command submit or on a message in the intake channel that matches the required PRD fields and `Status: Ready`.

### Expected automation steps
1. Parse message fields and validate required PRD fields.
2. Create/select repository and scaffold startup folders/files.
3. Generate `docs/prd.md`, `docs/project-plan.md`, and `artifacts/run-ledger.md`.
4. Post confirmation with repo link and next-step Codex command.

### Manual fallback steps
1. Copy Slack message into a local PRD draft.
2. Use `/S20-workflows/templates/prd-template.md` to normalize fields.
3. Execute `/S20-workflows/workflow-trigger-to-repo.md` manually.
4. Commit and begin first run.

## 3) Manual (local or GitHub)
### How to start from this repo as a base
1. Create a new repo from this template (or clone and reinitialize for a new project).
2. Keep the same section structure (`S00`, `S10`, `S20`, `S30`, `S90`).

### Where to paste PRD
- Paste PRD content into `docs/prd.md` in the new project using `/S20-workflows/templates/prd-template.md`.

### How to start the first run
1. Execute `/S20-workflows/workflow-trigger-to-repo.md` to confirm startup artifacts.
2. Open the project in Codex.
3. Run `/S20-workflows/workflow-context-to-output.md`.
4. Close with `/.codex/skills/save-bank/SKILL.md` and append the ledger row.

## Security and permissions notes
- Follow existing tiering and approval boundaries from repo guidance (for example, Tier 2 permission requirements for sensitive foundation/primitives changes).
- Limit trigger integrations to least-privilege tokens/scopes.
- Require review before promoting outputs to `banked` status or high-trust sections.
