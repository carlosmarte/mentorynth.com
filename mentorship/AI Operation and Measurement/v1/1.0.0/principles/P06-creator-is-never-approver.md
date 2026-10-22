# P06 · Creator is never approver

**Statement.** The entity that produces a change (human or agent) never approves it. Separation of duties is enforced identically everywhere, by machine, for humans and agents alike.

**Why.** Agent output quality sets the downstream verification burden. Independent checking is what turns "the agent produced something" into "this counts", and it is what makes a closed loop auditable.

**Rules.**
- Creator–Verifier is the approved default coordination pattern: one agent builds, a different agent checks.
- One independent Validation / Creator-Verifier Service is shared by every tier instead of a validator per tier.
- An agent never approves or promotes itself, or another agent it depends on; never changes its own permissions, budget, level or policy.
- The Identity & SoD Gatekeeper intercepts PRs, deployment triggers and approvals and rejects merges or halts deployments that violate the configured separation of duties. The Delivery Policy & Compliance Auditor verifies after the fact that creator ≠ approver held without unauthorized overrides.
- Each agent has its own identity and scoped credentials, separate from users; secrets never appear in prompts or repos.
- Verification runs where the generator cannot see it (Isolated Specification Tests; the Mutation Test Generator probes the gates themselves).

**Primitives governed.** Creator–Verifier pattern, Separation of Duties, Validation Agent, Identity & SoD Gatekeeper, Agent Identity & Secrets Vault, Policy-as-code bundles (SoD).

**Related.** P04, P09, P12.

**Source.** Coordination patterns (Creator–Verifier approved default); Shared Capability Map (5 · Identity, Ownership & SoD; 8 · Validation Service); Agent Responsibility ("Never does"); Terminology (Separation of Duties).
