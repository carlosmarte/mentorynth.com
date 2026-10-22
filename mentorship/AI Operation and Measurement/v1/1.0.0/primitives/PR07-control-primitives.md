# PR07 · Control primitives

The mechanisms that keep cost and risk bounded as autonomy grows. Policies are set by the Control functions and enforced here, in the platform and in the PQC pipeline. Governed by P06, P08, P09, P11, P22.

| Primitive | Definition | Behaviour |
|---|---|---|
| **Policy-as-code** | Machine-enforced guardrails evaluated before an agent acts. | Bundles: separation of duties · data classification · residency. Versioned reusable asset. |
| **Policy Engine** | Evaluates policy-as-code gates; invoked by the Harness before any action. | Enforces exceptions as time-boxed records. |
| **Control Plane** | Automated layer that applies policy: enforces autonomy budgets, throttles generation on SLO breach, records promotions and demotions. | Consolidates the Governor, cost quotas, circuit breaker and kill switch in one place. Replaces the separate Control Plane Throttler, Autonomy Budget Governor and Cost / Budget Agent duplicated on the board. |
| **Autonomy Budget Governor** | Automated safety valve. | On scope drift or falling SQY: lowers the agent's autonomy budget. On critical degradation beyond SLO thresholds: revokes permissions and takes the agent offline until stability returns. Owned by SRE / Reliability Owner. |
| **Circuit Breaker / Fallback** | Stop on error budget or loop detection; fall back to a human or safe mode. | Approved default pattern. Wired into CI/CD tier. |
| **Kill-Switch Runbook** | Pre-approved procedure to immediately halt or disable an agent. | Triggered automatically at Tier 1 on burn-rate alerts; manually by Agent Owner, SRE on-call or CISO without approval. Restart needs the Agent Owner. |
| **Capacity control levers** | Tuned as SLIs approach limits, before the SLO is breached. | **App throttle** (rate-limit per app/tenant) · **Agent concurrency limit** · **Workflow fan-out limit** (cap parallel sub-tasks) · **Service backpressure** (queue and slow callers instead of failing) · **Vendor-aware routing** (shift load across model and cloud vendors by capacity and health). Process: ① SLO goal → ② SLIs trending to limits (CPU, memory, P95 latency, queue depth, fan-out) → ③ controller tunes levers → ④ SLO protected → ⑤ error budget preserved. |
| **Separation of Duties (SoD)** | Creator ≠ approver rule for humans and agents. | Enforced identically everywhere by the Identity & SoD Gatekeeper; audited by the Delivery Policy & Compliance Auditor. |
| **Verification Pipeline** | Mechanical, automated auditor of agent output. | Components: pre-commit checks · CI/PR gates · mandatory static analysis and security scanning · **Isolated Specification Tests** (spec-derived tests the generating agent cannot see or game) · mutation-tested suites (score mutations, not line coverage) · multi-agent PR review · continuous post-merge analysis / fuzzing · **Ralph Loops** (running a coding agent repeatedly on the same spec until tests pass; not defined on the board). Teams configure thresholds, not tooling. |
| **Promotion gate (CI/CD)** | Gate that will not release an unqualified change. | Enforces promotion/demotion criteria and risk ceilings set by Control functions. |
| **Progressive delivery** | Feature flags, canary and staged rollouts, automatic rollback on SLO breach. | Bounds the blast radius of an agent change. |
| **Error-budget enforcement** | When an agent's changes burn the budget, the Governor demotes it and oversight tightens automatically. | |
| **Sandbox / Virtual Sandbox** | On-demand isolated execution environment; default runtime for agent execution. | Provisioned per PR or branch, seeded, drift-audited, decommissioned on merge/close/abandon. |
| **Agent Identity & Secrets Vault** | Agent identity separate from users; secrets never in prompts or repos. | Scoped credentials enforce the declared Surface; no standing access to production. |
| **AI Gateway / Model Gateway** | Single egress for all model calls. | Logging · cost tags · PII filter · rate limits · regional routing · model-version pinning · fallback and rate-limit handling. |
| **Harness (Agent SDK / runtime)** | Traces runs, tags cost, gives session IDs and replay, evaluates policy-as-code before any action. | Guarantees stated once for every tier: trace coverage · session and transaction IDs · replay · golden evaluation sets · cost tags · policy-as-code gates · kill switch. Includes HITL/HOTL controls and an audit trail. |
| **Side-effect ledger / checkpoint** | The agent checks before it acts and checkpoints state so a resume never repeats work. | Part of the durable-skill runtime (idempotency ledger). |
| **Audit trail / provenance** | Immutable record from intent → generation → approval → deployment; which agent, persona, model version and task produced a change, linked to its trace. | Lets a PQC be reconstructed and defended; lets leadership, auditors and regulators follow any action to its source and owner. |
| **Risk ceiling exception** | Time-boxed exception above the risk ceiling. | Risk & Compliance Owner + CISO; recorded; never grantable by the Agent Owner. |

**Source.** System Capacity Control; Shared Capability Map (2, 3, 5, Foundation, Harness guarantees); Pyramid: Control functions; Pyramid: PQC (Delivery & promotion); Human & Agent Environments; Terminology glossary.
