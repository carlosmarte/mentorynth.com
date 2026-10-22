# P11 · Stability beats speed: the control plane throttles automatically

**Statement.** When operational stability or Software Quality Yield degrades, an automated Control Plane restricts the offending agent's autonomy budget and throttles generation until stability returns to baseline. The business never trades stability for speed; the throttle fires before customers feel it.

**Why.** Rising agentic speed with falling stability (the Amplified Illusion) is throughput that does not become deployed value. A spike in change failure rate from code churn or hallucinated dependencies must be contained by machinery, not by a meeting.

**Rules.**
- The Autonomy Budget Governor is the safety valve: on scope drift or falling SQY it lowers the agent's autonomy budget; on critical degradation it revokes permissions and takes the agent offline until stability returns.
- Control plane functions are consolidated in one place: autonomy budgets, cost quotas, circuit breaker, kill switch, throttling on SLO breach, recording of promotions and demotions.
- Circuit Breaker / Fallback (approved default): stop on error budget or loop detection, fall back to a human or safe mode.
- Capacity control levers: app throttle (per app/tenant), agent concurrency limit, workflow fan-out limit, service backpressure (queue and slow callers instead of failing), vendor-aware routing. Tune them as SLIs approach limits to protect the SLO and preserve the error budget.
- Progressive delivery with automatic rollback on SLO breach bounds the blast radius.
- Automatic demotion stands; it can be appealed, never overridden.
- Platform enablement is inextricably linked to reliable delivery: the Control Plane lives in the Platform & DevEx tier and enforces the policies set by Control functions.

**Primitives governed.** Control Plane, Autonomy Budget Governor, Circuit Breaker, Kill-Switch Runbook, Capacity control levers, Autonomy budget, SQY.

**Related.** P08, P09, P10, P12.

**Source.** System Capacity Control; Review Agent Skills (Enforcing the Process Structurally); Agent persona: Autonomy Budget Governor, Control Plane Throttler; Business Outcomes ("Stability is protected automatically"); Shared Capability Map (3 · Control Plane & Autonomy Budget).
