```text
PRD INPUT
project_name: client-research-briefing-pipeline
goal: Produce weekly client research briefings with standardized structure and approvals.
owner: delivery-lead
constraints: SOC2 handling; legal review required before publication; fixed weekly delivery window.
source: client statement of work and kickoff transcript

PRD:
# Product Requirements Document (PRD)
## Summary
Build a repeatable pipeline to produce weekly client research briefings with approvals and auditability.

## Problem Statement
Research briefings are inconsistent across teams and lack a reliable approval workflow, leading to rework and compliance risk.

## Goals
- Standardize briefing structure and metadata.
- Implement a review and approval workflow with audit trail.
- Ensure weekly delivery cadence is predictable.

## Non-Goals
- Replacing existing research sources or analyst workflows.
- Providing real-time market data feeds in v1.

## Users and Stakeholders
- Primary Users: research analysts, delivery managers
- Stakeholders: legal, compliance, client account owners

## Scope
### In Scope
- Briefing template and required sections.
- Approval workflow with version history.
- Weekly delivery schedule enforcement.

### Out of Scope
- Automated client distribution in v1.
- External data integrations beyond approved sources list.

## Requirements
### Functional
1. Generate briefing drafts from analyst inputs.
2. Enforce a standardized template with required sections.
3. Support reviewer comments and approval status changes.
4. Maintain version history per briefing.
5. Produce a final approved markdown export.

### Non-Functional
- Security/Privacy: SOC2-compliant handling; restrict access by role.
- Reliability: no missed weekly delivery window.
- Maintainability: template changes should not break existing briefings.

## Success Metrics
- 100 percent of briefings follow the template.
- Approval cycle time under 3 business days.
- Zero compliance violations in quarterly audit.

## Constraints
- Legal review required before publication.
- Weekly delivery window: Monday 08:00 to Tuesday 12:00 local time.

## Dependencies
- Approved research sources list from compliance.
- Legal review availability for weekly cadence.

## Milestones
- M1: Template and workflow defined.
- M2: Pilot with one client account.
- M3: Full rollout to all accounts.

## Open Questions
1. Who owns final approval in edge cases?
2. What is the minimum required data set per briefing?
```
