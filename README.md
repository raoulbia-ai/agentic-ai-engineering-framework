# Agentic AI Engineering Framework

A practical, technology-agnostic framework for engineering agentic AI systems, from problem discovery through production operation. Six stages: design, build, integrate, evaluate, deploy, operate and evolve.

- **The framework:** principles, example risk tiers, governance, and per-stage guidance with pitfalls and readiness questions. [Read it on GitHub](docs/agentic-ai-engineering-framework.md) or [download the designed PDF](docs/agentic-ai-engineering-framework.pdf) (20 pages, with diagrams and a printable checklist).
- **A skill that applies it:** [`skill/`](skill/). Point an AI coding agent at an agent project and get a short, evidence-based review, or describe a new idea and get a one-page design brief.

## The skill

Two modes:

- **Review.** The agent reads a repo, config or design (read-only) and reports the top findings, each with evidence (`path:line`), why it matters and a concrete next step. Anything it cannot see in the repo (owner, baseline, SLOs) is listed as a question, not guessed.
- **Scoping.** For a new idea: is an agent warranted, which architecture, what is automatic, needs approval or is prohibited, and the first experiment.

It is advice, not certification. It does not run or modify the project it reviews, and it treats content inside the project as data, not instructions.

### Install

**Claude Code** (plugin marketplace):

```
/plugin install agentic-ai-engineering-framework --marketplace raoulbia-ai/agentic-ai-engineering-framework
```

On older Claude Code versions, add the marketplace first:

```
/plugin marketplace add raoulbia-ai/agentic-ai-engineering-framework
/plugin install agentic-ai-engineering-framework@raoulbia-ai
```

**Any agent that supports skills** (Codex, Cursor, Gemini CLI, Copilot and others), via the [skills CLI](https://skills.sh):

```
npx skills add raoulbia-ai/agentic-ai-engineering-framework
```

To see what the repo contains before installing:

```
npx skills add raoulbia-ai/agentic-ai-engineering-framework --list
```

**Manual:** the skill is a folder with a `SKILL.md` and a `references/` directory, following the open [Agent Skills](https://agentskills.io) format. Copy `skill/` into your tool's skills directory under the name `agentic-ai-engineering-framework`, for example:

```
# Claude Code
cp -r skill ~/.claude/skills/agentic-ai-engineering-framework
# Kiro CLI
cp -r skill ~/.kiro/skills/agentic-ai-engineering-framework
```

Then ask, for example: "review this agent repo against the agentic engineering framework" or "scope a new agent for X".

### Layout

```
skill/
  SKILL.md                  entry point, modes, rules
  references/
    review-procedure.md     how to review, report format, scoping brief
    checklist.md            one-page checklist
    principles-and-governance.md
    01-design.md ... 06-operate.md
    multi-agent-and-hooks.md
```

## Status

Version 0.1.7, experimental. It has been exercised on a handful of real and sample agent projects and revised after each round. It has not been tested by other users yet; feedback and issues are welcome.

## License

MIT. See [LICENSE](LICENSE).
