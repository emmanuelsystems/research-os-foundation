# Slack Trigger Spec: PRD + Conversation Context

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-25

## Purpose
Define consistent Slack trigger phrases so OpenClaw can handle both:
1) `initialize_project` runs from PRD input blocks
2) General conversation analysis and context generation

## Scope
This spec applies to Slack channels/threads where the OpenClaw bot is present.

---

## Trigger Modes

## 1) Initialize Project Trigger (PRD Mode)

### Accepted Trigger Phrase
`Run initialize_project using the provided PRD block below.`

### Required Payload
A full `PRD INPUT` block with:
- `project_name`
- `goal`
- `owner`
- `constraints`
- `source`
- `PRD:` body

### Example
```text
Run initialize_project using the provided PRD block below.

PRD INPUT
project_name: internal-notes-assistant
goal: Create a searchable internal notes assistant for weekly operations updates.
owner: ops-team
constraints: 2-week timeline; markdown-only outputs; no external integrations in v1.
source: manual intake from planning call notes

PRD:
# Product Requirements Document (PRD)
## Summary
Create a lightweight, searchable notes assistant for weekly operations updates.
```

---

## 2) Conversation Analysis Trigger (Context Mode)

### Accepted Trigger Phrases
Use one of the following:
- `Analyze recent conversation in this channel (last N messages).`
- `Analyze this thread and generate context.`
- `Build context from recent discussion and recommend next steps.`

Where `N` is optional; default is 50 if omitted.

### Expected Behavior
On trigger, OpenClaw should:
1. Pull recent messages from the current channel or thread.
2. Extract decisions, blockers, open questions, and action items.
3. Return a structured context brief in markdown.

### Output Template
```markdown
## Conversation Context
### Summary
### Key Decisions
### Open Questions
### Blockers / Risks
### Action Items
- [ ] Item — Owner — Due (if known)
### Suggested Next Steps (Top 3)
```

### Example
```text
Analyze recent conversation in this channel (last 40 messages).
```

---

## Guardrails
- Do not post sensitive credentials/secrets in generated summaries.
- Keep analysis scoped to the requested channel/thread window.
- If message history cannot be read, respond with a clear fallback request (paste/export conversation text).
- Do not execute external integrations from context mode.

## Slack Channel Ops Recommendations
- Use one dedicated channel for trigger commands (example: `#openclaw-ops`).
- Keep each trigger in its own thread for auditable output.
- Pin this spec and one PRD template message.

## Test Plan (Smoke Test)

### Test A: PRD Mode
1. In Slack, post the PRD trigger phrase.
2. Paste a minimal valid PRD INPUT block.
3. Verify:
   - `initialize_project` run executes
   - run report produced
   - ledger entry appended

### Test B: Context Mode
1. Create 10–20 sample messages in one thread.
2. Post: `Analyze this thread and generate context.`
3. Verify output includes all sections from Output Template.
4. Spot check extracted action items against original messages.

## Success Criteria
- Trigger intent is correctly recognized (PRD vs Context).
- Context mode returns structured output with actionable next steps.
- Failures are explicit and recoverable (no silent no-op).
