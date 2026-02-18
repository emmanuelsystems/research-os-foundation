```text
PRD INPUT
project_name: global-research-ops-platform
goal: Build a multi-region research operations platform with strict governance and scalable workflows.
owner: research-ops
constraints: Multi-region data residency; 99.9 percent uptime; audit-ready logs; launch pilot in 6 weeks.
source: cross-team roadmap workshop notes

PRD:
# Product Requirements Document (PRD)
## Summary
Create a global research ops platform that standardizes intake, execution, and reporting across regions.

## Problem Statement
Research operations are fragmented by region, resulting in duplicated work, inconsistent quality, and weak audit trails.

## Goals
- Standardize intake, workflow execution, and reporting across regions.
- Provide audit-ready logs and governance controls.
- Enable regional autonomy with consistent global standards.

## Non-Goals
- Replacing regional research tools in v1.
- Building a full analytics data lake.

## Users and Stakeholders
- Primary Users: research ops coordinators, analysts
- Secondary Users: program managers, QA reviewers
- Stakeholders: legal, security, regional leads, finance

## Scope
### In Scope
- Multi-region intake and workflow templates.
- Role-based access controls.
- Audit logging and retention policies.
- Standardized weekly and monthly reporting.

### Out of Scope
- External client portal in v1.
- Real-time streaming analytics.

## Requirements
### Functional
1. Provide a standardized intake form for research requests.
2. Route requests to regional queues with SLA tracking.
3. Support workflow templates for common research tasks.
4. Enforce approval steps before publication.
5. Maintain audit logs for every workflow transition.
6. Generate weekly and monthly reports by region and globally.
7. Support tagged artifacts for reuse and search.
8. Allow regional overrides with documented justification.
9. Provide a backlog and capacity view by region.
10. Export approved reports to markdown.

### Non-Functional
- Performance: report generation under 5 minutes for 1,000 items.
- Reliability: 99.9 percent uptime during business hours.
- Security/Privacy: data residency by region; encryption at rest.
- Maintainability: templates versioned and backward compatible.
- Accessibility: markdown-first outputs with clear headings.

## Success Metrics
- 95 percent of requests routed within 1 business day.
- 100 percent of published reports have approvals logged.
- 30 percent reduction in duplicated research work by quarter end.

## Constraints
- Pilot launch in 6 weeks.
- Multi-region data residency compliance.
- Audit logs retained for 2 years.

## Dependencies
- Regional data residency policies.
- Security-approved access groups.
- Legal review of reporting template.

## Milestones
- M1: Intake and routing MVP.
- M2: Audit logging and approvals.
- M3: Regional reporting and global rollup.
- M4: Pilot launch with two regions.

## Risks
- Regional policy differences may require custom handling.
- Approval bottlenecks could slow publication.

## Open Questions
1. Which regions are included in the pilot?
2. What is the minimum SLA for routing requests?
3. Who approves regional overrides?
```
