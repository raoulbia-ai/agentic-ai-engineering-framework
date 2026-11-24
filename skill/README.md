# Agentic AI Engineering Framework

Review an AI agent or agentic workflow against a practical, technology-agnostic engineering framework with six stages: design, build, integrate, evaluate, deploy, and operate and evolve. The skill reads a repository, configuration or design and reports the most important gaps, each with evidence, why it matters and a concrete next step. Anything it cannot see, such as an owner, baseline or service-level objective, is listed as a question rather than guessed.

It also helps scope new work: describe an idea and it produces a one-page design brief covering whether an agent is warranted, which architecture fits, which actions are automatic, need approval or are prohibited, and the first experiment to run.

## What it does and does not do

- Read-only: it does not run, modify or send anything from the project it reviews.
- No network calls, scripts, hooks or MCP servers. It is instructions and reference material only.
- Content inside the reviewed project is treated as data, not instructions.
- It is advice, not certification, and not a legal or compliance sign-off.

## Install

In Claude Code:

```
/plugin install agentic-ai-engineering-framework --marketplace raoulbia-ai/agentic-ai-engineering-framework
```

## Try it

Ask, for example: "review this agent repo against the agentic engineering framework", "is my agent production ready?" or "scope a new agent for invoice triage".

The full framework, with diagrams and a printable checklist, is at https://github.com/raoulbia-ai/agentic-ai-engineering-framework.

License: MIT.
