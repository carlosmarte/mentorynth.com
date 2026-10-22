# P14 · Optimize the value stream, not the silo; price time with Cost of Delay

**Statement.** Measure the whole value stream, invest in its slowest stage, and price every week of waiting in dollars. If you quantify only one thing, quantify Cost of Delay.

**Why.** If engineering ships 30% faster but marketing cannot produce campaigns, localize content or deploy go-to-market assets at the same pace, net enterprise velocity stays flat and the product sits idle in staging. A finished feature waiting on the bottleneck still burns its CoD ($60K/week × 3 weeks = $180K is the hidden price of optimizing one silo).

**Rules.**
- Organize around value streams, not departments: one team spanning product, tech and design (with BA, QA, GTM) owns one outcome end to end. Synergy comes when AI collapses sequential hand-offs into parallel execution.
- Velocity delta = variance in production speed between stages. Track each stage's cycle time and the hand-off wait between stages; direct AI investment to the slowest stage, not the fastest.
- Measure: end-to-end lead time (idea → customer), hand-off wait time, % of stages running in parallel.
- Cost of Delay ($/week) = revenue gained + cost saved + revenue protected + risk avoided, per week once live. Delay cost = CoD × weeks of delay.
- CD3 = CoD ÷ duration; do the highest CD3 first (sequencing by CD3 rather than "biggest value first" saved $280K in the worked example with the same people and work).
- Use relative WSJF (CoD = user-business value + time criticality + risk reduction/opportunity enablement, each scored 1–20, ÷ job size) in Stages 1–2 when dollar estimates are not credible; move to quantified CoD/CD3 in Stage 3 as telemetry joins CRM/ERP.
- Urgency profiles shape the value lost over time: Standard (linear), Fixed date (cliff), Expedite (high and immediate), Intangible (low now, rises later, e.g. tech debt and Telemetry First foundations).
- What to measure: CoD per initiative (reviewed quarterly); total delay cost sitting in staging and review queues; flow efficiency = active time ÷ total lead time; % of portfolio sequenced by CD3/WSJF; forecast vs actual CoD after launch.
- Each week an agent waits below its earned maturity level delays its yield; verification queues add delay on top of the tax.

**Primitives governed.** Value stream, Velocity delta, Cost of Delay, Delay cost, CD3, WSJF, Urgency profiles, Flow efficiency, Portfolio backlog.

**Related.** P13, P16.

**Source.** Portfolio Health (A · Cross-functional velocity deltas); Measuring the Cost of Delay (CoD): Pricing Time in the Value Stream.
