# P04 · Only Production-Qualified Changes count

**Statement.** The unit of delivered work that counts is a change that passed verification, its promotion gate and every automated gate, and reached production without incident. Output that was merely generated is gross; qualified output is net.

**Why.** Author velocity (how fast a human–agent pair drafts a PR) is deceptive. What matters is the rate at which generated code survives integration, passes security validation and runs reliably in production. PQC is how the roadmap's progress is measured honestly and how Throughput is adjusted for quality.

**Rules.**
- Definition of done for a PQC is encoded as policy, by risk class and agent level: the evidence, review level and gate approval a change must carry.
- Spec Fidelity (fraction of requirements and constraints verifiably satisfied) is the acceptance test.
- Risk-class routing: a low-risk L2 change takes a lighter qualification path than a high-risk L5 one.
- Provenance: which agent, persona, model version and task produced the change, linked to its run trace; immutable audit trail from intent → generation → approval → deployment; every PQC rolls up to a registered agent and its maturity level.
- Progressive delivery (feature flags, canary, staged rollout, automatic rollback on SLO breach) bounds the blast radius of an agent change.
- Throughput is measured as accepted outcomes, with Rework Tax and rejection rate tracked alongside. PQCs become the Accepted Outcomes in AI Yield; the cost of qualifying them flows into TCO.
- PQCs for net-new work feed the Agent side of NPG; PQCs that replaced a manual task feed the Human side.
- The Engineering Manager / Tech Lead stays accountable for every PQC, whoever or whatever wrote it.

**Primitives governed.** Production-Qualified Change, Qualification vector, Production-Qualified Yield, Spec Fidelity, Specification Execution Rate, promotion gates, provenance/audit trail.

**Related.** P01, P05, P06, P22.

**Source.** Pyramid: Production-Qualified Change (PQC); Indicators (Production-Qualified Yield, PDE); Business Outcomes & ROI ("Only Production-Qualified Change counts").
