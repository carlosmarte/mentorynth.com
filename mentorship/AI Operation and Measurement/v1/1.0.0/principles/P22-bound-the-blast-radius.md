# P22 · Bound the blast radius

**Statement.** Every agent acts inside a declared, enforced boundary: a sandbox by default, scoped credentials, a declared Surface, an autonomy and cost budget, targeted and localized changes, and progressive delivery with automatic rollback. Policy is evaluated before any action, not after.

**Why.** Agents make mistakes at machine speed. Containment, not perfection, is what makes earned autonomy safe; the cost of an error is bounded by how far it can reach.

**Rules.**
- Policy-as-code (separation of duties, data classification, residency) is evaluated by the Harness before an agent acts; the Policy / Guardrail Agent allows or denies actions against it.
- Sandboxed execution by default: virtual sandboxes, ephemeral workspaces and micro-VM runtimes; environments are provisioned just in time per PR or branch, audited for drift, and decommissioned the moment the PR is merged, closed or abandoned so forgotten sandboxes do not become shadow environments.
- Sandbox-then-Promote: act in an isolated copy first; a human or verifier promotes the result.
- Scoped credentials and a separate agent identity; secrets never in prompts or repos; no standing access to production.
- Single AI Gateway for all model calls: logging, cost tags, PII filter, rate limits, regional routing. Model-version pinning and fallback so behavior is reproducible.
- Agents make targeted, localized changes; no unprompted refactors or full regeneration.
- Agents check before they act (side-effect ledger) and checkpoint state so a resume never repeats work (durable skill: externalized state, idempotency ledger, HITL suspend, exit gates).
- Intent Confirmation for irreversible actions: the agent restates what it will do and waits for a yes.
- Progressive delivery: feature flags, canary and staged rollouts, automatic rollback on SLO breach.
- Red-Team Agent probes other agents for prompt injection, data leakage and unsafe actions; results feed promotion gates.
- Managed, compliant workstations only; personal devices are out of scope.

**Primitives governed.** Policy-as-code, Policy Engine, Sandbox, Ephemeral Workspace, microVM runtime, Environment Lifecycle Service, Agent Identity & Secrets Vault, AI Gateway, Durable skill, Side-effect ledger, Progressive delivery, Red-Team Agent.

**Related.** P06, P11, P20.

**Source.** Human & Agent Environments; Platform Enablement (Execution environments & runtimes); Agent Responsibility (Always does); Coordination patterns (Safety); Agent personas (Ephemeral Sandbox Orchestrator, Drift Auditor, Decommissioning Agent).
