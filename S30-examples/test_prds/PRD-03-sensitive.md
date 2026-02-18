```text
PRD INPUT
project_name: sensitive-governance-audit-assistant
goal: Support internal governance audit preparation with restricted handling rules.
owner: compliance-team
constraints: No external links; no data export; append-only ledger; no edits to protected sections.
source: internal compliance memo and audit checklist

PRD:
# Product Requirements Document (PRD)
## Summary
Create an internal assistant to prepare governance audit materials under strict handling rules.

## Problem Statement
Audit prep is manual and error-prone, and sensitive materials must not leave controlled storage.

## Goals
- Centralize audit preparation steps and evidence tracking.
- Enforce strict handling and access controls.
- Provide an auditable trail of changes.

## Non-Goals
- Any external distribution of audit materials.
- Automated submission to regulators.

## Users and Stakeholders
- Primary Users: compliance analysts
- Stakeholders: chief compliance officer, security team

## Requirements
### Functional
1. Track audit evidence requests and status.
2. Attach internal references to evidence items without external links.
3. Log all changes in an append-only run ledger.
4. Provide a final audit prep checklist export to markdown.

### Non-Functional
- Security/Privacy: internal-only access; no external links or exports.
- Reliability: all changes must be recorded; no destructive edits.

## Success Metrics
- 100 percent of evidence items have traceable internal references.
- Zero unauthorized external links in artifacts.

## Constraints
- No edits to protected sections or directories.
- No external integrations or API calls.

## Risks
- Overly strict restrictions could slow audit prep.

## Open Questions
1. What internal access group owns approvals?
2. Which evidence items require two-person review?
```
