## Stage 1 — Design: Requirements Before Architecture

**Objective:** Define a bounded system, its success criteria and the simplest architecture that can satisfy them.

### Problem and agent suitability

Start with the user, the existing process and the intended outcome. Identify what currently costs time or money, where errors occur and what improvement would justify building and maintaining a solution. Establish a baseline where possible: task completion time, quality, cost, volume or manual effort. Estimate the total cost of the proposed solution, including review, integration and maintenance, rather than token cost alone.

Screen the task before selecting an architecture:

| More suitable for an agent | Reasons to constrain or avoid agency |
|---|---|
| Ambiguous, multi-step tasks | Tasks better described by stable rules |
| Tool-dependent, adaptive actions | Irreversible or high-impact actions |
| Observable and evaluable outcomes | Outcomes that cannot be reliably assessed |
| Dynamic information or changing conditions | Restrictions on data access or delegation |

These are decision signals, not absolute exclusions. A regulated or high-impact workflow may still benefit from bounded, advisory assistance. Consider deterministic automation, a model-enhanced workflow, human assistance or no automation before defaulting to an agent.

Identify affected users, sensitive data, potentially harmful outcomes, applicable restrictions and who can decide whether the use case is acceptable. Establish an initial risk and impact assessment; a short note may be sufficient for a low-risk project.

### Requirements and architecture

Start with a product definition, not a model call:

| Decide | Captures |
|---|---|
| Who it serves | User role, job-to-be-done |
| What it may do | Autonomy level, tool inventory, data boundaries |
| What it must not do | Explicit non-goals (e.g. classify and draft, never issue refunds independently) |
| What counts as success | Measurable success metrics and acceptance thresholds |
| Where accountability lies | Owner, supervision points, escalation path |

Write requirements so they convert directly into evaluation cases ("must cite sources" → citation-relevance check). Identify representative tasks and a **failure taxonomy**: output errors, incorrect actions, policy violations, reliability or cost failures. Define an initial evaluation strategy before implementation.

Select the architecture family before choosing an implementation framework:

| Architecture | When to use it |
|---|---|
| Deterministic workflow | Rules and sequence are known; predictable execution matters |
| Model-enhanced workflow | A known process needs classification, extraction or generation at selected steps |
| Single bounded agent | Task requires adaptive tool use within clear limits |
| Planner–executor | Multi-step tasks benefit from explicit plans, execution and replanning |
| Multi-agent system | Distinct roles, independent verification or specialized capabilities justify coordination overhead |

These patterns can be combined. The choice depends on ambiguity, dependencies, reversibility, risk and the value of adaptation, not on how sophisticated the architecture appears.

Define the agent's identity and authorization model: which principal performs actions, when it acts on behalf of a user, and which permissions are available. Decide where task state lives and where human supervision or deterministic enforcement is needed.

Define autonomy boundaries, data restrictions, approval requirements and accountability before selecting tools. Distinguish actions that are automatic, require approval or are prohibited. Assess risks and choose controls that can be enforced outside model reasoning where necessary.

Test architectural, integration and safety assumptions with the smallest experiment that resolves the uncertainty. Use representative tasks, realistic tool responses, isolated environments and synthetic or authorized data. Reconsider the design if the evidence does not support it.

### Common pitfalls

Starting with a model or agent framework; automating a poorly understood process; assuming autonomy itself creates value; overlooking human review costs; vague success metrics; selecting a multi-agent architecture by default; relying on prompts alone for authorization; treating human oversight as a deployment-time addition.

### Readiness questions

- Is the problem and intended benefit clear enough to test?
- Have simpler alternatives and the existing process been considered, and is the proposed autonomy justified?
- Are purpose, non-goals, permissions and success criteria explicit?
- Have important architectural and safety assumptions been tested where necessary?
- Can requirements and safety boundaries be converted into tests?
- Is someone accountable for the system and its actions?
