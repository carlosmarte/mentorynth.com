# Primitives · AI Operation and Measurement framework

The atomic building blocks the framework is composed from, extracted from the DRAFT board (2026-10-22) and the NOTES csv. A primitive is a named thing with a definition, fields or values, and a rule for how it is used. Principles (see `../principles`) say how the primitives must be combined.

| File | Family | Contains |
|---|---|---|
| [PR01](PR01-measurement-chain.md) | Measurement chain | OKR, Key Result, Quality Dimension, SLI, SLO, SLA, Error budget, Burn rate, Lens, Baseline, Trace, Tier, control actions on breach, reference SLO stack, worked cascade |
| [PR02](PR02-value-economics.md) | Value and economics | Gross time saved, Verification Tax, Rework Tax, comprehension debt, run cost, Net time saved, Human / Agent / Total NPG, Net Delivery Capacity, Accepted Business Outcomes, Total Cost, AI Yield, Net AI Value, TCO, ROI tree, tuition cost, J-curve, CRV, Reallocation Rate, Value Differential, Workforce Productivity Matrix, Cost of Delay, CD3, WSJF, urgency profiles |
| [PR03](PR03-quality-and-yield-indicators.md) | Quality and yield indicators | PQC, qualification vector, Production-Qualified Yield, SQY, PDE, Spec Fidelity, SER, Verified Task Success, FAR, FRR, golden set, LLM-as-a-judge, PR Review Saturation, tech-health metrics, SPACE, the full Dimensions SLI dictionary |
| [PR04](PR04-agent-declaration.md) | Agent declaration | The four facets (Runtime · Trigger/Lifecycle · Surface · Role) with all values, Agent Catalog entry fields, agent personas |
| [PR05](PR05-autonomy-ladder.md) | Autonomy ladder | Maturity Levels 0–6, loop modes (HITL / HOTL / HOOTL / HIC), risk class and ceilings, autonomy budget, promotion gate, demotion, delegation by level, Agent Lifecycle Evaluation stages and Decide outcomes |
| [PR06](PR06-coordination-patterns.md) | Coordination patterns | Agent↔Agent and Human↔Agent patterns with approval status; tier wiring |
| [PR07](PR07-control-primitives.md) | Control | Policy-as-code, Policy Engine, Control Plane, Autonomy Budget Governor, Circuit Breaker, Kill-Switch Runbook, capacity control levers, SoD, Verification Pipeline components, progressive delivery, sandbox, identity vault, AI Gateway, Harness guarantees, side-effect ledger, audit trail |
| [PR08](PR08-work-artifacts-and-contracts.md) | Work artifacts and contracts | Specification, Handoff Contract, tier contract card, durable skill, golden path, golden evaluation set, versioned prompts/skills, reallocation roster, decision log, portfolio backlog, stage-gate scorecard, promotion schedule, append-only annotation |
| [PR09](PR09-platform-and-capability.md) | Platform and capability | Shareable / Repeatable / Reusable, the 8 shared capabilities, Foundation, Control functions, environment catalog (Standard / On-request / Out-of-scope), Intent / Context / Agentic layers, Platform Enablement groups |
| [PR10](PR10-operating-model.md) | Operating model | Rollout Stages 1–4, Five Pillars, Productivity Roof, Six domains, value stream, Framework goals, Continuous Learning Loop, Responsibility pyramid and owner roles, decision rights, precedence, source-of-truth rule, skill progression, scale concerns |

## How the families fit together

```
Operating model (PR10)  ── sequences ──▶  Autonomy ladder (PR05)  ── bounds ──▶  Agent (PR04)
        │                                          │                                  │
   sets OKRs                               gates on evidence                   runs inside
        ▼                                          ▼                                  ▼
Measurement chain (PR01) ◀── computed from ── Quality indicators (PR03) ◀── Control primitives (PR07)
        │                                          │                                  │
   rolls up to                               counts PQCs                     enforce policy on
        ▼                                          ▼                                  ▼
Value & economics (PR02)                 Work artifacts (PR08)  ◀── coordinated via ── Patterns (PR06)
                                                   │
                                           shared through
                                                   ▼
                                   Platform & capability (PR09)
```

## Open items carried over from the board's own glossary

- Verification Tax is sized differently in four places (Formulation; Portfolio Health; The How indicators; Net Productivity Gain's 0.4 h/agent-hour).
- Net time saved has two formulas (Formulation vs SPACE).
- Tier numbering runs both ways (cascade: Tier 4 = C-level; pyramid: Tier 1 = senior leadership).
- Pilot gate: AI Yield ≥ 1.0 (lifecycle) vs > 1.0 (maturity model).
- Used but never defined: Six domains · Single pipeline, Single Number Rule · HIC · MTTC · ROAI · Ralph Loops · NCU.
- Agent-type consolidation (NOTES csv): On-Demand ≈ Ephemeral (keep one); Serverless moved to Runtime; Orchestrator ≈ Supervisor (keep one).

Sources: `../DRAFT_2026-10-22_18-18-40.pdf` (board export), `../NOTES_2026-10-22_18-18-40.csv` (agent-type facets, wiring note).
