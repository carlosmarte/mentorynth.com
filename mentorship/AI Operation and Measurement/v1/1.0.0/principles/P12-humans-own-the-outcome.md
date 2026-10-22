# P12 · Stop beats go: humans own the outcome, agents produce the evidence

**Statement.** The agent produces the evidence; a named human owns the outcome. Certain decisions are never delegated to an agent, every escalation lands in a named human's queue with a response SLO, and any authorized human can stop any agent at any time without approval.

**Why.** Autonomy without a single accountable human creates governance ambiguity (the Ownership and Delegation domain exists to eliminate it). Escalations that wait on "someone" stall the loop; stops that need approval arrive too late.

**Rules.**
- Decisions only a named human can make: set intent and risk appetite; register an agent; promote an agent one level; grant an exception above the risk ceiling; change an agent's cost quota; retire an agent or start vN+1; accept a production change; own the spec; pull the plug; appeal an automatic demotion.
- Precedence when humans and agents collide: 1) policy (Control functions) beats everything below it; 2) stage ceiling and risk ceiling beat any owner's request; 3) automatic demotion stands, appealable never overridable; 4) stop beats go: any authorized pause wins until the Agent Owner restarts; 5) within those bounds, the Agent Owner decides.
- Pull the plug: Agent Owner, SRE on-call or CISO can take any agent offline at once; no approval needed to stop; restarting needs the Agent Owner.
- An agent must escalate when: sources of truth disagree; the spec is ambiguous or missing; an action would exceed its level, scope, budget or risk tier; confidence or a verification gate falls below threshold; it touches PII, secrets or a new external system.
- An agent never changes its own permissions, budget, level or policy; never approves or promotes itself; never edits the spec or tests it is judged against; never overrides a pause, kill switch or automatic demotion.
- Agent-to-agent delegation: only to an agent at the same or a lower level; the receiver inherits the stricter scope; the orchestrator's Agent Owner stays accountable for the whole chain.
- Skill progression for people: Reviewer → Specification Engineer → Agent Owner → Value Stream Owner, each step earned through Proficiency evidence tracked in SPACE. Reviewing agent output well comes before owning agents.
- Human-in-the-loop Escalation is the approved default human↔agent pattern; Veto / Kill Switch is independent of escalation.

**Primitives governed.** Named human decisions, Decision rights (Decides · Consulted · Enforced by), Precedence rule, Agent Owner, Human-Escalation Router, Kill switch, Delegation by maturity level.

**Related.** P06, P10, P11, P20.

**Source.** Ownership and Delegation (Human / Shared / Agent Responsibility); Coordination patterns (Human ↔ Agent).
