# Research OS Foundation
### The Operating System for Agentic Work

> **"Don't do the work. Define the work."**

<!-- RULE: initialize_project may only update text inside the summary block below. -->
<!-- PROJECT_SUMMARY_START -->
Project `day3-prd03-sensitive` validates sensitive-mode style PRD handling through Slack trigger. Goal: confirm canonical-path-only initialize_project routing/reporting with append-only ledger evidence, protected README summary markers, and explicit sensitive-constraint warning surfacing under `ops-team` ownership.
<!-- PROJECT_SUMMARY_END -->

---

## 🏗️ The System Architecture

This repo is organized into **Semantic Sections (`S[XX]`)** to guide both human and agent behavior.

```plaintext
root/
├── .codex/                 # Agent configuration (Skills, Templates)
├── AGENTS.md               # The "Read Me" for AI Agents
├── README.md               # You are here
├── S00-foundation/         # The Kernel: Principles, Glossary, Rules
├── S10-primitives/         # The Type System: Agents, Skills, Tiers
├── S20-workflows/          # The Procedures: Step-by-step guides
├── S30-examples/           # The Training Data: Golden artifacts
└── S90-assets/             # The Filesystem: Raw media and assets
```

### Why this structure?
1.  **Predictable Navigation**: Everything has a place. No "misc" folders.
2.  **Agent-Legible**: Agents can easily categorize content by its section prefix.
3.  **Scalable**: New sections can be added without breaking the core logic.

---

## 🔄 The Operating Loop

We do not just "chat" with AI. We follow a strict operating loop to ensure quality:

1.  **Context**: Gather raw info, constraints, and definitions.
2.  **Plan**: Outline the steps and expected outputs.
3.  **Run**: Execute the plan (using Agents and Skills).
4.  **Review**: Validate the output against a Rubric.
5.  **Bank**: Save the artifact and learnings back to the repo, including a run ledger entry.

*See `/S20-workflows/workflow-context-to-output.md` for the detailed guide.*

*See `/S20-workflows/workflow-trigger-to-repo.md` for project startup from trigger/PRD to initialized repo.*


---

## Initialization Contract

`initialize_project` is contract-driven and should follow these canonical references:

1. Contract (single source of truth): `S20-workflows/initialize-project-contract.md`
2. Save routing table: `S00-foundation/save-map.md`
3. Legacy compatibility policy: `S00-foundation/legacy-artifacts.md`
4. Test cases for repeatable validation: `S30-examples/tests/initialize-project-test-cases.md`
5. Example run reports: `S30-examples/test-runs/`

---

## 🚀 Getting Started

*Start here: `S00-foundation/onboarding.md`*

### START HERE
1. Integration surfaces and bootstrap seam: `S00-foundation/INTEGRATIONS.md`
2. Bank state criteria: `S00-foundation/banking-definition.md`
3. Bootstrap contract: `S20-workflows/initialize-project-contract.md`
4. Runtime note: `initialize_project` is invocation-contract based and can run from Codex, OpenClaw, Slack, or Telegram trigger flows.
5. Validation runbook: `S20-workflows/validate_initialize_project.md`
6. PRD fixture pack: `S30-examples/test_prds/`
7. Expected output spec: `S30-examples/expected_outputs/initialize_project_expected.md`
8. Team quickstart + test guide: `S20-workflows/team-quickstart-and-test-guide.md`

### OpenClaw Initial Setup (Official Install Flow)
Use the official installer from `openclaw.ai` / `docs.openclaw.ai`.

#### Recommended: Installer script
1. macOS / Linux / WSL2:
   - `curl -fsSL https://openclaw.ai/install.sh | bash`
2. Windows (PowerShell):
   - `iwr -useb https://openclaw.ai/install.ps1 | iex`
3. The installer handles Node detection, installation, and onboarding.

#### Alternative: npm / pnpm install
Use this if you prefer manual package-manager control:
1. `npm install -g openclaw@latest`
2. `openclaw onboard --install-daemon`

or

1. `pnpm add -g openclaw@latest`
2. `pnpm approve-builds -g`
3. `openclaw onboard --install-daemon`

#### After install (official verification)
1. `openclaw doctor`
2. `openclaw status`
3. `openclaw dashboard`

#### Workspace attach for this repository
1. `cd F:\Antigravity\research-os-foundation`
2. Start OpenClaw in this workspace and attach to repo root.
3. Confirm runtime state file exists: `.openclaw/workspace-state.json`
4. Run the canonical preflight checklist below before PRD validation.

### OpenClaw Setup (Canonical Preflight)
Run these checks in order before executing PRD validations:
1. Confirm runtime root path is this repository (`pwd` should resolve to repo root).
2. Confirm runtime identity is visible (`whoami`, `hostname`).
3. Confirm heartbeat mode:
   - `HEARTBEAT.md` empty/comments only = no active heartbeat tasks.
   - Non-empty task list = periodic checks are expected.
4. Confirm callable tools used by this workflow (`rg`, `git`, `powershell`).
5. Confirm canonical files are readable:
   - `S20-workflows/initialize-project-contract.md`
   - `S00-foundation/save-map.md`
   - `S00-foundation/legacy-artifacts.md`
   - `S20-workflows/validate_initialize_project.md`
   - `S10-primitives/RUN-REPORT-TEMPLATE.md`
6. Confirm README marker integrity (exactly one each):
   - `<!-- PROJECT_SUMMARY_START -->`
   - `<!-- PROJECT_SUMMARY_END -->`
7. Use canonical invocation text:
   - `Run initialize_project using provided PRD block.`
8. Save each run report to `S30-examples/test-runs/` using dated filenames.

### OpenClaw Troubleshooting
1. If README markers are missing/duplicated, stop and repair marker boundaries before running `initialize_project`.
2. If tool discovery differs by shell/runtime, document the command and executable path in the run report.
3. If file create succeeds but move/delete fails, log it as environment behavior and keep validation artifacts in canonical paths.
4. If any write targets legacy paths (`docs/`, `artifacts/`, root `task.md`), mark run as FAIL and route fixes to `S00-foundation/save-map.md` and `S20-workflows/initialize-project-contract.md`.

### For Humans
1.  **Use this Template**: Click "Use this template" to start a new project.
2.  **Define your Goal**: Create a new issue or task.
3.  **Select a Workflow**: Browse `S20-workflows/` for the right procedure.
4.  **Execute**: Run the workflow, saving all work to files (not chat).

### For Agents (Codex)
1.  **Read Context**: Start by reading `AGENTS.md` and `S00-foundation/`.
2.  **Load Skills**: Check `.codex/skills/` for available tools.
3.  **Follow Protocol**: Never modify `S00` or `S10` without explicit authorization (Tier 2 permission).
4.  **Output**: Always produce named files in the appropriate directories.

---

## 📚 Key Primitives

*   **Agents (`S10-primitives/agents.md`)**: Defines *who* is doing the work (Research Agent, Builder, QA).
*   **Skills (`S10-primitives/skills.md`)**: Defines *how* the work is done (standardized instructions).
*   **Artifacts**: The atomic unit of work. If it's not in a file, it didn't happen.

---

## 🛠️ Codex Integration
This repo is "Codex-First". It includes:
*   **`.codex/skills/`**: A library of prompt-engineered skills ready for the agent to load.
*   **`AGENTS.md`**: A dedicated entrypoint optimizing the repo for LLM understanding.

---

*Built for the **Advanced Agentic Coding** initiative.*


