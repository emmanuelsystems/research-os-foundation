# Onboarding

- **Status:** reviewed
- **Owner:** operations-agent
- **Last Updated:** 2026-02-16

## 1) What this repo is for
- A repeatable operating system for turning ideas into reviewable project artifacts.
- A shared structure humans and agents can both execute without ambiguity.
- A workflow-first model where outputs are saved as files, reviewed, and banked.
- A foundation for scaling from one-off runs into reusable skills, workflows, and examples.

## 2) New idea checklist
1. Create a PRD draft from the template at `../S20-workflows/templates/prd-template.md`.
2. Choose a trigger source (Notion, Slack, or Manual) and define how the PRD enters the workflow.
3. Run the bootstrap workflow at `../S20-workflows/workflow-trigger-to-repo.md` to create the initial project artifact set.
4. Open the new project in Codex and execute the first run using `../S20-workflows/workflow-context-to-output.md`.
5. Run Save + Bank (`../.codex/skills/save-bank/SKILL.md`) to persist outputs, append the run ledger, and record promotion target(s).

## 3) Key links
- Trigger bootstrap workflow: `../S20-workflows/workflow-trigger-to-repo.md`
- PRD template: `../S20-workflows/templates/prd-template.md`
- Save + Bank skill: `../.codex/skills/save-bank/SKILL.md`
- Run ledger schema: `../S20-workflows/run-ledger-schema.md`

## 4) What “done” looks like
- Core artifacts are present and correctly named (PRD, plan, README, and run ledger).
- Artifacts intended for reuse are in **banked** state after review.
- `artifacts/run-ledger.md` is updated for the run.
- Promotion target is explicitly recorded (for example `S20`, `S30`, or a specific promoted file path).
