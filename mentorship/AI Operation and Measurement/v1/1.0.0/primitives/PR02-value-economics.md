# PR02 · Value and economics primitives

The units in which gain, cost and return are expressed. Source of truth for productivity terms: Net Productivity Gain. Governed by P01, P03, P13, P14.

## Gains and taxes (hours)

| Primitive | Definition | Formula / rule |
|---|---|---|
| **Gross time saved** | Raw hours reclaimed from routine tasks via AI, before any taxes. The headline pilots report. | Reported by source: agents · harness/orchestration · tooling (each a different investment). |
| **Verification Tax** | Human time spent checking, testing, explaining and justifying AI output before it can be trusted. Typically erodes ~37% of gross gains (25–50% in regulated settings). The largest tax line and the one policy can move. | = time checking + testing + explaining + justifying. Example: 10 h saved on paper − (2 + 1 + 0.5 + 0.2) = 6.3 h real. Illustrative rate: 0.4 h review per agent-hour. |
| **Rework Tax** | Time and cost of humans editing, fixing or regenerating AI output that was wrong or rejected. Includes the **Repair Multiplier** (re-prompting and regenerating failed code). | Illustrative: 10% of net-new output rejected or fixed by hand. |
| **Comprehension debt** | Growing gap between the code that exists and what any human understands; later time spent understanding code nobody wrote. | Rising debt triggers demotion to HITL. Signals: review depth, time per change, share of changes a human can explain. |
| **Agent run cost** | Cost of all agent runs (tokens + licences) converted to hours at the loaded rate. | Charged once, on the Agent side of NPG. |
| **Learning curve & adoption** | Training, spec/prompt authoring, new workflow habits. | Human-side tax. |
| **Friction & manual fallback** | Waiting on verification queues, tool churn, rescuing failed agent runs. | Human-side tax. |
| **Supervision** | HITL/HOTL oversight of agent output, including the Verification Tax. | Human-side tax. |
| **AI code blindness** | Code that looks right but is subtly wrong; can take longer to untangle than writing fresh. | Driver of Rework Tax and comprehension debt. |
| **Net time saved (one task)** | Time AI saves on paper − Verification Tax. Building block of Total NPG. | Individual form: gross − (prompt engineering + debugging + downstream rework). |
| **Human Net Productivity Gain (Human NPG)** | Manual work removed from people by agents, harness/orchestration and tooling, minus new human work. The freed capacity that feeds CRV. | = manual work removed − supervision (incl. Verification Tax) − learning curve − friction & fallback. Agent work that replaced a manual task counts here. |
| **Agent Net Productivity Gain (Agent NPG)** | Net-new agent output no human would have produced (accepted PQCs), minus its taxes. | = net-new output − Verification Tax − Rework Tax − comprehension debt − agent run cost. Replaced manual work is excluded. |
| **Total Net Productivity Gain (Total NPG)** | Human NPG + Agent NPG, each freed hour and each tax counted once. The framework's headline key result; the hours view of Net AI Value. | One-side rule: every hour on one side only; each tax subtracted once on the side whose gross created it. |
| **Net Delivery Capacity** | Executive metric enforcing "optimize for net capacity, not gross speed". | = Total NPG. |
| **Harness & orchestration automation** | Hand-offs, retries, routing and checks that now run without a person. | A source of Human NPG. |

Illustrative month (one team): pilot reports 400 agent hours; 150 replaced manual tasks (Human side), 250 net-new; taxes 170 → Agent NPG 80 (32% of gross). Human side: 550 gross manual work removed (300 moved to agents + 90 harness + 150 tooling, minus 350 overlap), 180 new human work → Human NPG 120 (40%). Total NPG = 200 hours; adding the headline 400 to human gross 300 would have claimed 700.

## Return (dollars)

| Primitive | Definition | Formula / rule |
|---|---|---|
| **Accepted Business Outcomes** | Dollar value of work accepted: merged, shipped, approved or independently verified. Rejected or abandoned output counts as zero. | AI Yield numerator. Acceptance labels come from the human alignment pipeline. |
| **Gross AI Gain** | Accepted outcomes in dollars before any cost is subtracted. | = Step 1. |
| **Total Cost** | Operational cost + Verification Tax + Rework Tax + technical debt + risk cost, in dollars. Same cost used in TCO. | 1 operational (tokens, compute, licences, platform) · 2 Verification Tax (hours × loaded rate) · 3 Rework Tax · 4 technical debt (AI-related defects, maintenance) · 5 risk cost (policy violations, security incidents, regulatory exposure, remediation). |
| **AI Yield** | Accepted Business Outcomes ÷ Total Cost. Tracked per agent and per version; a Tier 4 key result. | > 1.0 net-positive · = 1.0 break-even · < 1.0 negative ROI. Pilot gate ≥ 1.0 (lifecycle) / > 1.0 (maturity model) — the board flags this inconsistency. |
| **Net AI Value** | Accepted Business Outcomes − Total Cost. The money version of Total NPG. | Positive exactly when AI Yield > 1.0. |
| **Total Cost of Ownership (TCO)** | Full cost of running an agent; identical to AI Yield's Total Cost. Keeps ROI honest. | Managed by Finance Owner (CFO delegate) who signs off the TCO model. |
| **ROI / ROI tree** | Value delivered ÷ (cost + risk-adjusted loss). Exists only once gain is net of TCO's taxes; on the board expressed as AI Yield. | VALUE: lead time for change · throughput (features/quarter) · defect escape rate · incident MTTR · adoption. COST: token spend per feature · platform & infra · human review hours. RISK: policy violations · audit findings · data-residency breaches. Attribution: every action cost-tagged and traced, rolled up per team, value stream, region. |
| **ROAI** (Return on AI Investment) | Audited return on AI spend aggregated from CRM/ERP at Tier 4. | Not expanded on the board. |
| **Tuition cost** | Budgeted cost of the J-curve dip paid while adapting legacy verification systems to agentic output. | Planned capacity, not a failure. |
| **Delivery J-curve** | Temporary, budgeted dip in delivery stability and throughput as the organization (and each wave) adapts. | Looks like failure if the pre-AI baseline was not captured. |
| **Tokenmaxxing** | Vanity phenomenon of measuring gross token generation or drafting speed while ignoring validation costs. | Anti-metric. |
| **Amplified Illusion** | Rising agentic speed with falling stability; throughput that does not become deployed value. | Counts as a loss. Detected by the Amplified Illusion Detector. |

Worked quarter: Team A (Augmented Strategists) $100k accepted, costs $65k → AI Yield 1.54, Net AI Value +$35k. Team B (Low-Return Optimists) $100k accepted, costs $110k → AI Yield 0.91, Net AI Value −$10k.

## Capacity reallocation

| Primitive | Definition | Formula / rule |
|---|---|---|
| **Capacity Reallocation Value (CRV)** | Economic value of freed human hours actually moved to higher-value work. | = Human NPG × Reallocation Rate × Value Differential. Net of AI run cost it feeds AI Yield. Plain form: hours shifted × (strategic rate − routine rate) × weeks. |
| **Reallocation Rate** | Measured (not assumed) share of net freed hours actually moved to strategic work rather than absorbed by meetings or idle time. | Source example assumes 100%; 60% is realistic. |
| **Value Differential** | Difference between hourly value of strategic and routine work. | e.g. $200 − $75 = $125/hr. |
| **Capacity arbitrage** | Shifting freed hours from routine (~$75/hr) to strategic (~$200/hr) work. | 5 hrs/week → ~$32.5k per employee per year. |
| **Capacity Reallocation Resources** | Cross-trained people whose freed capacity lets them move to the bottleneck stage or a new initiative. | Tracked on a **reallocation roster**: skills, freed hours/week, current team, target initiative. Measures: reallocation rate, time-to-redeploy, % of freed hours on roadmap work. |
| **Velocity delta** | Variance in production speed between value-stream stages. | Invest in the slowest stage. Track per-stage cycle time + hand-off wait. |
| **Workforce Productivity Matrix** | Segments the workforce by gross time saved vs verification and rework burden into four cohorts (formerly "Net Productivity Matrix"). | **Observers** (baseline untapped: low saved, low burden → core workflow onboarding) · **Low-Return Optimists** (negative yield: low saved, high rework → remediation coaching) · **Misaligned Middle** (gain evaporator: high speed, line-by-line inspection → automated verification) · **Augmented Strategists** (target: high saved, calibrated automated verification; +$32.5k/employee/yr, ROI 4.3×). |

## Cost of Delay

| Primitive | Definition | Formula / rule |
|---|---|---|
| **Cost of Delay (CoD)** | Economic value lost per unit of time a capability is not in customers' hands. | $/week = revenue gained + cost saved + revenue protected + risk avoided. Review quarterly. |
| **Delay cost** | CoD × weeks of delay. Total delay cost = Σ across items until each ships. | |
| **CD3** (Cost of Delay Divided by Duration) | CoD ÷ duration. Do the highest first. | Quantified method, from Stage 3. |
| **WSJF** (Weighted Shortest Job First) | SAFe relative scoring: (user-business value + time criticality + risk reduction/opportunity enablement) ÷ job size, each scored 1, 2, 3, 5, 8, 13, 20. | Used in Stages 1–2 before dollar estimates are credible. |
| **Urgency profile** | Shape of value lost over time. | Standard (linear) · Fixed date (cliff) · Expedite (high, immediate) · Intangible (low now, rises later). |
| **Flow efficiency** | Active time ÷ total lead time. | |

**Source.** Net Productivity Gain; Formulation; AI Yield; Portfolio Health & CRV; Example: Verification Tax Erodes Gross AI Gains; Measuring the Cost of Delay; Terminology glossary.
