# Research OS Foundation
### The Operating System for Agentic Work

> **"Don't do the work. Define the work."**

This repository is the default starting point for projects that treat AI agents as coworkers, not just chatbots. It provides a structured file system, defined primitives, and repeatable workflows to ensure high-quality, reviewable outputs.

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

## 🚀 Getting Started

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
