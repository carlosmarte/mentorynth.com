# P21 · Hold the sweet spot between over-constrained and under-governed

**Statement.** Agent control sits on a spectrum from deterministic (more control, less flexibility, brittle) to creative (more agency, more creativity). Aim for high agency inside guardrails, and move along the spectrum only as telemetry earns it.

**Why.** Over-constrained: rigid HITL gates, narrow prompts and hard-coded flows make agents break on new use cases, stall adoption and push teams to route around the platform. Under-governed: unbounded autonomy drives up policy and secret violations, token cost and the Verification Tax.

**Rules.**
- Hold the sweet spot with golden paths + policy-as-code guardrails + error budgets.
- Widen autonomy (HITL → HOTL) only as telemetry earns it; narrow it again when SLOs breach.
- The target is high agency that generalizes across the marketplace, safely.
- The transition from open loop (HITL) to closed loop (HOTL) is enforced by: Spec-Driven Development; the mechanical verification pipeline; the automated control plane; the Specification Execution Rate as proof the loop is closed.
- Loop modes: no loop (human does or drives the work, L0–1); open loop / HITL (active human intervention, L2–3); closed loop / HOTL (passive supervision from outside, self-regulating via telemetry and SQY, L4–5); sealed closed loop / human-out-of-the-loop (full automation within bounded governance, L6, low risk only).
- Human-in-Command (HIC): humans retain overall authority and can override the system; listed with HOTL as a mode that is downgraded to HITL on breach.

**Primitives governed.** Agent Control spectrum, Loop modes, HITL / HOTL / HOOTL / HIC, Golden paths, Policy-as-code, Error budgets.

**Related.** P09, P10, P11.

**Source.** Agent Control: Deterministic vs Creative; HITL vs HOTL: Open Loop vs Closed Loop; Human in the Loop vs Related Concepts.
