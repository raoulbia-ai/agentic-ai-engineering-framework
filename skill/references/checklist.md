## Quick-Reference Checklist

Use when scoping or reviewing an agent; apply items according to risk and complexity.

### Design
- [ ] Intended value, existing baseline and simpler alternatives considered; key assumptions tested where needed.
- [ ] Purpose, non-goals, autonomy, success thresholds and accountable owner defined.
- [ ] Architecture, data boundaries and oversight justified.

### Build
- [ ] Model and control pattern suit representative workloads; skills and other behavioral components are versioned where used.
- [ ] Tool contracts, side effects, authorization and appropriate preview/approval mechanisms are explicit.
- [ ] Each agent's granted tools are checked against its stated role and non-goals; unneeded capabilities are removed or gated.
- [ ] Context, task state, memory, knowledge and audit records have distinct responsibilities.
- [ ] Execution budgets, stop conditions, retry safety and recovery match the risk.

### Integrate
- [ ] Scoped identities, least privilege, delegated authorization, read/write separation and environment isolation are appropriate.
- [ ] Secrets in generated or local configuration are permission-restricted, kept out of version control, and have a rotation path.
- [ ] Retrieved content retains provenance and cannot override policy or permissions.

### Evaluate
- [ ] Private evaluation cases cover representative tasks, failures and relevant adversarial inputs.
- [ ] Repeated runs, baseline comparisons and acceptance thresholds support intended use; relevant control and regression tests pass.

### Deploy
- [ ] Compatible versions are identifiable; release checks and production monitoring are ready.
- [ ] Rollback and recovery address in-flight work and external side effects.

### Operate & Evolve
- [ ] Quality, safety, reliability, latency and cost are monitored; routing and fallback behavior are tested where used.
- [ ] Hooks and lifecycle scripts are reviewed, tested and versioned, and cannot silently bypass a control.
- [ ] Consequential actions are auditable; incident response and retirement responsibilities are clear.
- [ ] Production failures feed back into evaluation; ongoing value and risk are reassessed.
