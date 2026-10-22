# PR01 · Measurement chain primitives

The atomic objects that turn an outcome into a number and a number into a control action. Chain: OKR → Quality Dimension → SLI → SLO → SLA, with the Error Budget as the control signal. Governed by P07, P08, P19.

| Primitive | Definition | Core question | Fields / values |
|---|---|---|---|
| **OKR** | Strategic business and technical targets quantifying value realization, revenue acceleration and capacity reallocation. Top of the chain. | What outcome do we want? | Objective; 2–3 Key Results; owner (tier) |
| **Key Result (KR)** | Measurable result under an objective. Every SLI must trace to one. | | e.g. Total NPG ≥ 15% of engineering capacity; Verification Tax ≤ 30% of gross AI gains; 100% of AI assets in the Agent Catalog |
| **Quality Dimension** | A quality that must hold for the outcome to be true. The menu each tier picks SLIs from. | Which qualities define "good"? | Availability · Reliability · Performance · Quality · Safety & Security · Recoverability · Economics · AI Adoption · Distribution |
| **SLI** (Service Level Indicator) | Continuous automated telemetry ratio of good events to valid events at the user/system boundary. | What do we measure? | SLI = Good ÷ Valid × 100%. Measure where the user feels it; track worst cases (slowest 1–5%), not averages. No consequence directly; triggers burn-rate alerts. |
| **SLO** (Service Level Objective) | Internal target, set tighter than the SLA; its gap to 100% defines the error budget over a 28–30 day window. | What is the target? | target %; window; owning OKR (an SLO with no owning OKR is a retirement candidate) |
| **SLA** (Service Level Agreement) | External contractual or cross-departmental commitment on availability, verified accuracy and containment, with consequences on breach. | What do we promise? | commitment; consequence (penalties, service credits, fee waivers, audit escalation) |
| **Error budget** | (1 − SLO target) × valid events: failures affordable in the window. | How much failure can we afford? | Budget left → ship and widen autonomy. Budget spent → freeze releases, fix reliability, restore human sign-off. |
| **Burn rate** | Speed at which the error budget is consumed relative to the window. | | Multi-window burn-rate alerts trigger rollback or Kill-Switch Runbook. |
| **Lens** | Primary audience through which an indicator is read. | Who reads this? | L Leadership (strategic ROI & risk) · M Middle management (velocity & process) · IC Individual contributor (friction & flow). Each has its own ROI question. |
| **Baseline** | Pre-AI workflow time, quality and cost, captured before agents run, so Net Time Saved and Verification Tax have a starting point. | | Captured per in-scope workflow; Stage 1 exit criterion. Lost for good if agents launch first. |
| **Trace** | One trace ID linking every step of a task: who/what, every step (prompt, context, tool/MCP calls, outputs, latency, tokens, cost), human touchpoints, outcomes, safety events. | | ≥95% of runs traced is the Stage 1 gate. Retained per data policy. Captured via e.g. the `gen_ai.client.inference.operation.details` event. |
| **Tier** (measurement) | The altitude at which the chain repeats. | | Tier 4 C-level / Productivity Roof · Tier 3 VP / Functional (flow and focal points) · Tier 2 Individual & Role (ownership and delegation) · Tier 1 Hardware, Event & Software (Agent Catalog & mandates). Mandates cascade down; telemetry rolls up. |
| **Control action on breach** | The automated consequence wired to each tier's error budget. | | T1: burn-rate alerts → rollback / kill switch. T2: below target 2 sprints → coaching; quality breach → HOTL to HITL. T3: budget exhausted → freeze feature velocity, downgrade HIC/HOTL → HITL. T4: KR breach → investment and portfolio review; ungoverned asset → remediated ≤ 30 days. |

## Reference 30-day SLO stack (target · allowed failure)

| SLI | SLO | Budget |
|---|---|---|
| Platform availability | 99.9% | 0.1% |
| Tool-call success | 99.5% | 0.5% |
| Verified task success | 95.0% | 5.0% |
| Factual correctness | 99.0% | 1.0% |
| First-response speed | P99 ≤ 500 ms for 95% of requests | |
| Guardrail violations | 0.0% | zero budget |

## Worked cascade (one outcome: "turn AI into measurable engineering productivity")

| Tier | OKR | SLI | SLO | SLA / consequence |
|---|---|---|---|---|
| 4 · C-Level | Total NPG ≥ 15% of capacity; Verification Tax ≤ 30%; 100% assets governed | Total NPG (hrs/eng/week) · Verification Tax % · AI spend per value stream · % assets in catalog | Total NPG ≥ 4 hrs/eng/week · Verification Tax ≤ 30% · cost per AI-assisted change ↓ QoQ · catalog = 100% | Quarterly ROI report to board · KR breach → portfolio review · ungoverned asset remediated ≤ 30 days |
| 3 · VP / Functional | 99.95% dev-platform availability; lead time for AI changes −25%; ≥80% teams onboarded | Dev-platform & sandbox availability · lead time · change failure rate · team & role adoption · PR AI-assistance rate | Availability ≥ 99.95% (≈21.6 min/month) · CFR ≤ 10% · adoption ≥ 80% | 99.9% commitment · P1 response ≤ 15 min · P1 restore ≤ 4 hr · budget burned → freeze risky rollouts |
| 2 · Individual & Role | Reduce workstation interruptions 50%; AI code acceptance ≥ 30% | P95 IDE/build latency · build & test success · generated-code acceptance · AI output edit rate · HITL rate | P95 latency < 800 ms · build < 5 min · build success ≥ 95% · edit rate ≤ 40% | Support response ≤ 30 min · below target 2 sprints → coaching · quality breach → HOTL to HITL |
| 1 · Hardware, Event & Software | Reduce build failures 30%; 99.95% agent & tool availability | Tool failure · crash rate · MTBF · CPU throttling · memory · MTTR · rebuild time · policy & secret violations · tokens per run | Tool failure ≤ 1% · CPU throttling < 2% · recovery < 15 min · 0 critical secret violations · tokens within budget | Hardware replacement ≤ 1 business day · critical vuln patched ≤ 72 hr · budget burned → auto-throttle agent autonomy |

Terminology caution (from the board's own glossary): tier numbering runs both ways. The cascade uses Tier 4 = C-level … Tier 1 = hardware; the responsibility pyramid in "The How" uses Tier 1 = senior leadership … Tier 5 = DevEx. "Role tier 1–3", SPACE's "Level 2 IC / Level 3 Director" and Maturity Levels 0–6 are separate scales.

**Source.** From outcomes to telemetry; OKR → Telemetry Cascade; Breakdown of SLI, SLO, SLA and OKRs; Reliability & outcome formulas; Telemetry First.
