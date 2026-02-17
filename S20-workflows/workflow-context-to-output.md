# Workflow: Context to Output (The "Do The Thing")

- **Status:** reviewed
- **Owner:** operations-agent
- **Last Updated:** 2026-02-16

## Goal
To systematically transform initial context and constraints into a verified, high-quality output artifact, ensuring reproducibility and quality control.

## Inputs
1.  **Initial Context**: The raw material or request from the user (e.g., ticket description, email, voice memo).
2.  **Constraints**: Specific requirements or limitations (e.g., format, length, style, technology).

## Process
1.  **Gather Context**: Collect all necessary information, references, and definitions to fully understand the task.
2.  **Create a Plan**: Outline the specific steps, tasks, and expected outputs required to achieve the goal.
3.  **Execute the Run**: Perform the work according to the plan, generating intermediate and final artifacts.
4.  **Review Output**: Evaluate the results against the original constraints and a quality rubric.
5.  **Bank Learnings**: Document insights, improved prompts, or reusable snippets back into the system for future use, and log run outputs in the run ledger.

## Context Pack
*   **Sources**: URLs, files, or snippets provided as input.
*   **Constraints**: Must-haves and must-not-haves.
*   **Definitions**: Key terms and concepts relevant to the task.

## Plan
*   **Tasks**: Breakdown of the work into actionable items.
*   **Outputs**: List of deliverables for each task.
*   **Checks**: Validation steps for each output.

## Execution
*   **Work in Artifacts**: All work should happen in files or defined outputs, not just in chat or temporary buffers.
*   **Iterate**: Refine outputs based on initial drafts and self-correction.

## Review
*   **Rubric**: A checklist or set of criteria to measure success.
*   **Decision Deltas**: Document key decisions made during execution and the rationale behind them.

## Bank
*   **Save Learnings**: Update `skills.md` or `agents.md` if the process revealed a better way to work.
*   **Update Ledger**: Append run details to `artifacts/run-ledger.md` using `S20-workflows/run-ledger-schema.md`.
*   **Ledger Contract**: Use `S20-workflows/run-ledger-schema.md` as the table contract for ledger entries.
*   **Archive**: Store successful prompts or patterns.

## Outputs
*   **Named Artifacts**: The final deliverables with clear, descriptive filenames.
*   **File Paths**: Locations where artifacts are stored.

## Promotion Rule
### What Counts as Sandbox
*   Drafts, unreviewed code, temporary files.
*   Work that has not passed the review gate.

### What Counts as Production-Ready
*   Artifacts that have passed the review rubric.
*   Code that has been tested and linted.
*   Documents that are formatted correctly and free of errors.
