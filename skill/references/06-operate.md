## Stage 6 — Operate & Evolve: Observability, Reliability and Continuous Improvement

**Objective:** Maintain system effectiveness, detect failures, respond to incidents and reassess whether the agent remains justified.

**Observability is a precondition for debugging and tuning.** Capture useful run-level evidence: input constraints, retrieval provenance, explicit plans or execution state when available, tool calls and results, policy decisions, final output and supporting evidence. Do not depend on access to private model reasoning. Correlate traces across tools and agents, redact sensitive content and set appropriate retention and access policies.

Monitor quality signals (task success, escalation rate, reviewer rejection rate), operational signals (latency, cost per run, token use, failures) and safety signals (blocked actions, unexpected side effects, incidents). Establish service-level objectives (SLOs) for the measures that matter: maximum acceptable latency or cost, minimum success rate and relevant safety or reliability thresholds.

Reliability and cost engineering include routing, fallbacks, caching where appropriate, capacity management and execution budgets. A model cascade can route simpler steps to cheaper or faster models and escalate difficult cases to stronger ones, provided evaluation supports the routing policy. Account for total cost: tools, hosting, review time and incident handling, not just tokens.

Keep an identifiable operational owner. Define how to pause execution, revoke credentials, contain failures, reconcile side effects and escalate incidents. Feed representative incidents, regressions and new tasks back into evaluation; revise design or implementation when evidence warrants it. Monitor model and connector changes as dependencies evolve.

Event-driven hooks and lifecycle scripts (run on prompts, tool use, file changes or session start) are code with side effects, not passive automation. Review what they read, write or send; ensure a hook failure cannot silently skip a control such as an audit entry or memory write; and test and version them like other behavioral configuration.

Periodically reassess value, reliability, risk and continued need. When retiring an agent, stop scheduled work, drain or cancel in-flight tasks safely, revoke credentials, remove unnecessary dependencies and dispose of stored state and memory in accordance with retention requirements. Preserve required audit records.

Monitor whether permissions, oversight and risk controls remain effective. Review material changes in purpose, scope, autonomy, model or data access. Keep sufficient records to reconstruct consequential actions and decisions, and ensure incidents have an accountable response owner.

For systems that warrant additional documentation, useful artifacts include an agent card (purpose, scope and limitations), data-flow map, model/tool inventory, permission summary, evaluation and red-team results, oversight plan and incident response plan. Combine these into a short document for simpler projects; use more formal evidence where required by risk or applicable obligations.

External references for deeper risk, governance and security guidance include NIST AI RMF, ISO/IEC 42001, the EU AI Act where applicable, and OWASP guidance on agentic AI security. Assess applicable legal and regulatory obligations separately.

### Common pitfalls

Monitoring cost but not quality; logging sensitive content indiscriminately; leaving incidents outside regression testing; untested model fallbacks; untested hooks that can silently bypass controls; keeping obsolete agents and credentials active.

### Readiness questions

- Can we identify and investigate significant failures or unauthorized actions?
- Are quality, reliability, cost and safety signals monitored at an appropriate level?
- Is someone responsible for incidents, dependency changes and eventual retirement?
- Does production evidence feed back into evaluation and design?
