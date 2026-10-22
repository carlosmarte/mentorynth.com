# P07 · Every number traces to an outcome

**Statement.** Start from the OKR, name the quality dimensions that must hold for it to be true, measure them (SLI), set targets (SLO) and make promises (SLA). The same chain repeats at every tier, from the C-suite down to hardware and agents. Mandates cascade down; telemetry rolls up.

**Why.** Telemetry otherwise stays trapped in infrastructure logs. In traditional engineering SLIs/SLOs/SLAs evaluate deterministic uptime; in an AI operating model they must also govern stochastic quality, semantic correctness and verification economics, and they must unify with executive OKRs rather than create reporting silos.

**Rules.**
- Chain: OKR → Quality Dimensions → SLI → SLO → SLA. Telemetry measures the SLI; the SLI tells whether the SLO is achieved; the SLA defines the commitment; controls protect the SLO/SLA; the error budget determines how much failure is acceptable before corrective action.
- Every SLI must trace to a key result. An SLO with no owning OKR is a candidate to retire.
- Tier 1–2 SLIs roll up into Tier 3 flow metrics, which roll up into the Tier 4 key results (Total NPG, Verification Tax, AI Yield / Net AI Value).
- When an SLO's error budget is burned, that tier's control action fires (auto-throttle autonomy, freeze risky rollouts, HOTL → HITL, portfolio review).
- A DevEx SLO breach triggers the same Learn → Improve & Codify step as an error-budget burn.
- One accountable owner per metric: others contribute, but one person answers for each number.
- Quality Dimensions available: Availability, Reliability, Performance, Quality, Safety & Security, Recoverability, Economics, AI Adoption, Distribution.

**Primitives governed.** OKR, Key Result, Quality Dimension, SLI, SLO, SLA, Error budget, the Dimensions SLI dictionary, tier table.

**Related.** P02, P08, P19.

**Source.** From outcomes to telemetry: OKR → Quality Dimensions → SLI → SLO → SLA; OKR → Telemetry Cascade; Breakdown of SLI, SLO, SLA and OKRs; Shared accountability.
