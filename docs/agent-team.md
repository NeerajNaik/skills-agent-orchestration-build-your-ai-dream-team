# Agent team

The team will use GitHub Copilot CLI in a Codespace to orchestrate work on Mona's Project Pulse dashboard.

| Agent | Model | Responsibility | Definition |
|---|---|---|---|
| Orchestrator | Claude Opus 5.5 (copilot) | Breaks work into tasks, delegates to specialists, coordinates dependencies, and verifies the integrated result. | `.github/agents/orchestrator.agent.md` |
| Planner | Claude Opus 5.5 (copilot) | Researches the codebase and produces implementation plans, including risks, dependencies, and validation steps. | `.github/agents/planner.agent.md` |
| Coder | GPT-5.5 (copilot) | Implements code-oriented tasks, fixes bugs, and validates changes within the assigned file scope. | `.github/agents/coder.agent.md` |
| Designer | Gemini 3.7 Flash (copilot) | Handles UI/UX, accessibility, information architecture, interaction flow, and visual design. | `.github/agents/designer.agent.md` |

The Orchestrator first asks the Planner for an implementation plan, then assigns scoped tasks to the Coder and Designer. Independent tasks may run in parallel; dependent or overlapping work runs sequentially. The Orchestrator reviews the integrated work and reports the outcome.
