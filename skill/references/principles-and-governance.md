## Foundational Principles

- **Simplicity:** Choose the simplest architecture that satisfies the requirements. Additional tools, models, agents and orchestration must earn their place.
- **Proportionality:** The level of architectural complexity, documentation, testing and oversight should be proportionate to the system's autonomy, risk and potential impact.
- **Technology independence:** Keep engineering decisions, contracts and evaluation criteria applicable across models, vendors, SDKs and infrastructure wherever practical.
- **Evidence-driven engineering:** Use experiments, evaluations and production observations rather than assumptions or successful demos alone.
- **Bounded autonomy:** Define what an agent may do, what it must not do and when it must stop or escalate.

### Risk Tiers

For example, a team might tier its systems as follows. Adapt the tiers to your own risk appetite and regulation; the point is to decide depth of controls deliberately.

| Example tier | Typical signs | Suggested depth |
|---|---|---|
| Low | Read-only or advisory, local use, no sensitive data | Define purpose and non-goals, a basic evaluation, simple logging |
| Medium | Writes to internal systems or drafts for human approval, internal data | All stages, with enforced approvals, scoped credentials, a private evaluation suite and an accountable owner |
| High | External or irreversible actions, money, production systems, personal or customer data, multi-tenant | All stages in full, including adversarial testing, staged release, incident response and audit records |

If two tiers seem to fit, apply the higher. A human approval step lowers the tier only if it is enforced outside the model and the approver can see what will happen.

## Governance as a Continuous Engineering Discipline

Governance is not a separate lifecycle stage. It influences decisions throughout the lifecycle by establishing what an agent may do, under what conditions and with what accountability.

Design establishes autonomy, data access and acceptable risk; build and integration turn those boundaries into technical controls; evaluation tests their effectiveness; deployment and operation enforce, monitor and reassess them.

Four related disciplines answer different questions:

| Discipline | Fundamental question |
|---|---|
| Governance | Who decides, who is accountable, and what rules apply? |
| Risk management | What could go wrong, and is that risk acceptable? |
| Security | How are the system, its data and its actions protected? |
| Assurance | What evidence demonstrates that requirements are satisfied? |

A read-only research assistant does not require the same controls as an agent authorized to execute financial transactions. 

**Example — refund authorization:** If an agent must never issue a refund without authorization, design defines its authority to recommend but not independently execute refunds; implementation separates draft and commit and enforces authorization outside the model; evaluation tests bypass attempts; deployment requires those tests to pass; operation monitors and audits executed refunds. A single governance requirement becomes a concrete engineering constraint throughout the lifecycle.
