# Skill: Save + Bank

## Purpose
Ensure every run ends with persisted artifacts and an updated run outputs ledger.

## Scope
- Applies after execution and review steps.
- Covers file persistence, ledger update, and promotion routing.
- Does not replace domain-specific QA or approval workflows.

## Inputs
1. Run context (task prompt, workflow used, operator).
2. List of files created/updated during the run.
3. Review status (`draft`, `reviewed`, `banked`).
4. Current run ledger file (`artifacts/run-ledger.md`).
5. Ledger schema reference (`S20-workflows/run-ledger-schema.md`).

## Outputs (Artifact Format)
- Saved run outputs at canonical file paths.
- Updated `artifacts/run-ledger.md` with a new appended row.
- Promotion note in ledger when artifacts move to `S10`, `S20`, or `S30`.

## Steps
1. **Collect Output Inventory**
   - Enumerate all files created and modified in the run.
   - Verify each output exists on disk.
2. **Route Outputs to Correct Paths**
   - Place procedural guidance in `S20-workflows/`.
   - Place primitives in `S10-primitives/`.
   - Place exemplars in `S30-examples/`.
   - Keep project-specific outputs in project-local folders.
3. **Apply Status Metadata**
   - Set each artifact to `draft`, `reviewed`, or `banked`.
   - Ensure filenames follow living file naming policy.
4. **Update Run Ledger**
   - Open `artifacts/run-ledger.md`.
   - Append a new row using `S20-workflows/run-ledger-schema.md` columns.
   - Include commit hash when available.
5. **Validate Completion**
   - Confirm no run output is left only in chat.
   - Confirm ledger row references all outputs.

## Stop Rules
- **Complete when** all outputs are saved and ledger entry is appended.
- **Fail when** required output paths are missing or ledger cannot be updated.

## Review Checklist
- [ ] Every declared output exists in the repository.
- [ ] Ledger row is appended (not overwritten).
- [ ] Review status is accurate for the run.
- [ ] Promotion target is recorded when banking occurred.

## Versioning
- v1.0.0 (2026-02-16): Initial release of Save + Bank skill.
- v1.1.0 (2026-02-16): Added explicit ledger schema dependency and clarified bank-step update requirements.
