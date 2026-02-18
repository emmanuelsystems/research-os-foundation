```text
PRD INPUT
project_name: ops-insights-hub
goal: Unify operational insights into a single hub for leadership reporting.
owner: ops-analytics
constraints: Ship in 1 week; must include 3 months of historical data; fully automated but requires manual approval for every update.
source: leadership email thread with mixed requirements

PRD:
# Product Requirements Document (PRD)
## Summary
Create an ops insights hub that consolidates metrics and narratives for leadership.

## Problem Statement
Leadership reports are inconsistent and require manual reconciliation across multiple sources.

## Goals
- Provide a single hub for weekly ops insights.
- Reduce time spent preparing leadership updates.
- Maintain accuracy with approval checkpoints.

## Non-Goals
- Replacing existing BI tools.
- Building a long-term data warehouse in v1.

## Users and Stakeholders
- Primary Users: ops-analytics
- Stakeholders: leadership team, finance, operations

## Requirements
### Functional
1. Aggregate metrics and narrative updates into one report view.
2. Support approvals for each update.
3. Refresh insights automatically after data changes.

### Non-Functional
- Timeline: production-ready in 1 week.
- Data coverage: include 3 months of historical data at launch.

## Success Metrics
- Leadership report prep time reduced by 50 percent.
- Approval turnaround under 24 hours.

## Constraints
- Must be fully automated but require manual approval for every update.
- Data sources not yet finalized.

## Risks
- Conflicting automation and approval requirements may delay launch.

## Open Questions
1. What data sources are authoritative?
2. Which approvals are required before publishing?
3. What is the minimum viable scope for week one?
```
