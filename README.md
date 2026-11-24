# Agentic AI Engineering Framework

A practical, technology-agnostic framework for engineering agentic AI systems, from problem discovery through production operation. Six stages: design, build, integrate, evaluate, deploy, operate and evolve.

- **The framework:** [`docs/agentic-ai-engineering-framework.md`](docs/agentic-ai-engineering-framework.md). Principles, an example set of risk tiers, governance, and per-stage guidance with pitfalls and readiness questions.
- **A skill that applies it:** [`skill/`](skill/). Point an AI coding agent at an agent project and get a short, evidence-based review, or describe a new idea and get a one-page design brief.

## The skill

Two modes:

- **Review.** The agent reads a repo, config or design (read-only) and reports the top findings, each with evidence (`path:line`), why it matters and a concrete next step. Anything it cannot see in the repo (owner, baseline, SLOs) is listed as a question, not guessed.
- **Scoping.** For a new idea: is an agent warranted, which architecture, what is automatic, needs approval or is prohibited, and the first experiment.

It is advice, not certification. It does not run or modify the project it reviews, and it treats content inside the project as data, not instructions.

### Install

The skill is a folder with a `SKILL.md` and a `references/` directory, which is the format used by agent tools that support skills. Copy `skill/` into your tool's skills directory under the name `agentic-ai-engineering-framework`. For example, for Kiro CLI:

```
mkdir -p ~/.kiro/skills
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

Version 0.1.5, experimental. It has been exercised on a handful of real and sample agent projects and revised after each round. It has not been tested by other users yet; feedback and issues are welcome.

## License

MIT. See [LICENSE](LICENSE).
