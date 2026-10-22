# P10 · Autonomy is earned one level at a time, and re-earned

**Statement.** Every agent climbs the maturity ladder one level at a time, each step earned with evidence, within a ceiling set by its risk class and by the organization's rollout stage. Autonomy relaxes as verified success rises and narrows again when SLOs breach. Promotion is never automatic; demotion is.

**Why.** The maturity ladder is how trust is calibrated against telemetry rather than opinion. A ceiling is a design choice, not a failure: a Level 3 agent with high AI Yield is a success.

**Rules.**
- Promotion gate (move up exactly one level) requires all of: offline eval meets baseline on the agent's eval set; SLOs held for a full review period with error budget intact; the verification pipeline's staged checks catch failures before output and human review stops finding new failure modes; AI Yield > 1.0 at Periodic Review; telemetry and audit trail complete for every action.
- No skipping levels: each one produces the evidence the next one needs. Do not skip gates to save time (FAR risk); invest in evaluation that shortens them.
- Demotion: SLO breach or exhausted error budget → drop one level and restore the human checkpoint; rising comprehension debt (people can no longer explain what the agent did) → back to HITL; incident or policy violation → back to Level 3, review before re-promotion; major change to model, prompts or tools → new version vN+1 re-enters at Design & Baseline.
- Risk ceiling: high risk (regulated, financial, safety, irreversible) stops at Level 3 (HITL); medium risk (customer-facing, reversible) stops at Level 4–5 (HOTL); low risk (internal, easily reversed) may reach Level 6. Effective ceiling = the lower of stage ceiling and risk ceiling.
- Stage ceilings: Stage 1 → L0–2; Stage 2 → L3; Stage 3 → L4–5; Stage 4 → L6 (low-risk only).
- An agent is production-ready when it has passed its own level's promotion gate and the organization has passed the stage gate that unlocks that level.
- Each new version starts again at lifecycle stage 1 and earns its autonomy back. AI Yield is tracked per version. Retired agents are archived, not deleted.
- Autonomy is reviewed at every Periodic Review against error budgets and Quality Yield.
- Decision rights: Agent Owner proposes with evidence; AI Transformation Lead approves within the stage ceiling; Risk & Compliance also signs for high-risk agents. Automatic demotion stands while an appeal runs.

**Primitives governed.** Maturity Levels 0–6, Promotion gate, Demotion, Risk ceiling, Stage ceiling, Autonomy budget, Agent Lifecycle Evaluation stages, Progressive Autonomy / Earned Trust pattern.

**Related.** P08, P11, P12, P16.

**Source.** Maturity Model + Loop Engineering; Agent Lifecycle Evaluation; Human Responsibility (decisions 3, 4, 10); Cost of Delay (promotion gates vs risk).
