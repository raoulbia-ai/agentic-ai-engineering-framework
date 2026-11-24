# Multi-agent systems, agent configs and hooks

Extra checks for reviews of agent teams, capabilities and anything with hooks or lifecycle scripts. These apply the framework's Stage 2, 3 and 6 ideas to artefacts the stage files do not name directly.

## Review the right unit

If a manifest (capability, bundle, catalog entry) lists agents, skills, steering and hooks, review them as one system. Check that the manifest includes everything the agents reference, and that lifecycle labels (experimental, production) are consistent across the parts.

## Permission audit table

Build this from the agent config files (tool lists, allow rules, MCP settings). It is the fastest way to see whether role boundaries are real.

| Agent | Stated role / "must not" | Tools it holds (write, shell, MCP write) | Enforced outside the model? | Gap |
|---|---|---|---|---|

When the runtime's defaults are not visible (for example an empty allow list), write "unknown: prompted by default?" in the "Enforced outside the model?" column, rate the finding at the lower of the two severities, and add the question to the owner list. Do not assume either way.

- A role that says "never edit" but holds a write or shell tool is a finding unless something outside the model blocks it.
- An empty allow list usually means the runtime prompts the user per call. That is a control, but it depends on the user not auto-approving. Record it as "prompted by default (runtime)" and list it as a question if the runtime is not visible.
- Check which agents load MCP servers from a shared config, and what credentials those servers hold.

## Delegation and handoffs

- Who may call whom, and does the callee get only what it needs?
- Content from tickets, reviews, documents or memory passed into write-capable agents: is it marked as data, not instructions?
- Can anything be promoted from one task into long-term memory without a gate? Who authorises it?
- Does the coordinator know which sub-tasks completed, failed or are unsafe to retry?

## Hooks and lifecycle scripts

Hooks run code on events (prompt, tool use, file save, session start). Treat them like tools with side effects.

- What does each hook read, write or send? Does it log content that may be sensitive?
- Can a hook failure block, or silently skip, a control (for example a memory write or an audit entry)?
- Are hook scripts tested and versioned with the agents?

## Credentials and generated config

- Scripts that copy secrets into config files: where do the files land, what file mode, are they git-ignored, and are they readable by other tools or agents?
- Tokens passed to MCP servers: least privilege, read-only where possible, rotation path.

## Evaluation for teams of agents

Look for tests of routing (does the right agent get the task), of the workflow (for example RED/GREEN/REFACTOR order), and of each hook. A team with no routing or workflow evaluation cannot show the benefit of having several agents.
