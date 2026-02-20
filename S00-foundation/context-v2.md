# Project Context: internal-notes-assistant

- **Status:** draft
- **Owner:** ops-team
- **Last Updated:** 2026-02-20

## Trigger Inputs
- **project_name:** internal-notes-assistant
- **goal:** Create a searchable internal notes assistant for weekly operations updates.
- **owner:** ops-team
- **constraints:** 2-week timeline; markdown-only outputs; no external integrations in v1.
- **source:** manual intake from planning call notes

## Operating Context
The project is focused on improving retrieval and reuse of weekly operations notes that currently exist as scattered markdown files. Version 1 must remain internal-only and avoid external system integrations.

## Delivery Boundaries
- Use markdown artifacts only.
- Keep implementation lightweight for a 2-week initial delivery window.
- Prioritize reliable keyword and tag-based retrieval over advanced integrations.

## Primary Outcomes
1. Designate a folder-based markdown intake path.
2. Build a searchable index strategy for keyword + tag filters.
3. Produce a weekly markdown summary artifact.

## Risks and Watchouts
- Tag inconsistency can degrade search quality and summary relevance.
- Folder and naming conventions must be defined early to prevent drift.
