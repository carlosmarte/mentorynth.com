# P08 · Promise less than you target; let the error budget decide

**Statement.** The internal SLO is set tighter than the external SLA, so problems are fixed before a promise is broken. The gap between the SLO and 100% is the error budget, and the error budget, not opinion, decides whether to release, widen autonomy, or freeze and tighten oversight.

**Why.** 100% is unreachable and each extra "nine" costs roughly 10× more effort. Budgets make failure tolerance explicit and turn reliability into an automatic control signal for autonomy.

**Rules.**
- SLI = good events ÷ valid events × 100%. Measure where the user feels it; track the worst cases (slowest 1–5%), not averages.
- Error budget = (1 − SLO target) × valid events, over a 28–30 day window.
- Budget left: ship features and give agents more autonomy. Budget spent: freeze releases, fix reliability, put agents back under human sign-off.
- Multi-window burn-rate alerts trigger rollback or the Kill-Switch Runbook at Tier 1.
- Reference 30-day SLO stack: platform availability 99.9% (0.1% budget); tool-call success 99.5% (0.5%); verified task success 95.0% (5.0%); factual correctness 99.0% (1.0%); first-response speed P99 ≤ 500 ms for 95% of requests; guardrail violations 0.0% (zero budget).
- Example: promise 99.0% verified accuracy externally, run the team to 99.5–99.9%.
- Capacity control levers are tuned as SLIs approach limits, before the SLO is breached, to preserve the budget.

**Primitives governed.** SLO, SLA, Error budget, Burn rate, Capacity control levers, Kill-Switch Runbook, Verified Task Success.

**Related.** P07, P10, P11.

**Source.** Reliability & outcome formulas: SLI → SLO → SLA → OKR; System Capacity Control; Breakdown of SLI, SLO, SLA and OKRs (consequence of breach).
