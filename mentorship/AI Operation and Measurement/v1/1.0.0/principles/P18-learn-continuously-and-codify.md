# P18 · Learn continuously and codify what you learn

**Statement.** Run a continuous learning loop, Adopt → Measure → Learn → Improve & Codify → Scale & Share, once per rollout wave and continuously inside each team. Each wave's learnings become the next wave's starter kit, so adoption gets faster and cheaper over time.

**Why.** Telemetry that nobody acts on, slow feedback from production defects back to prompts and skills, and metrics read out of context or gamed are the failure modes of scale. The loop turns signals into shared assets, guardrails and playbooks.

**Rules.**
- Adopt: onboard the next wave on golden paths (catalog-approved agents, templates, durable skills), with a champion in every value stream.
- Measure: instrument the Dimensions SLIs from day one (active vs dormant users, FAR/FRR and rework, token cost, Verification Tax); roll up via the OKR → Telemetry cascade.
- Learn: review signals by lens on a cadence: weekly team retros (IC), monthly value-stream reviews (M), quarterly OKR resets (L). Find where the J-curve dip is deepest and why.
- Improve & Codify: turn fixes into reusable assets (prompts, skills, guardrails, runbooks); recalibrate agent autonomy (HITL ↔ HOTL) against error budgets.
- Scale & Share: promote proven local tools into shared capabilities; publish playbooks; retire low-ROI workflows.
- Keep a decision log: what changed, why, and its measured effect.
- Human edits to agent output become test cases or prompt changes (Correction Capture); accepted and rejected outputs feed the agent's evaluation sets (Feedback / Rating Loop).
- The feedback loop is only as good as its labels: rubric-anchored, calibrated human labelers; a versioned golden set with a held-out slice never used for tuning; error taxonomy and label-drift analysis; bias toward recall where misses are costly. Human alignment and label QA are part of agent building, not an afterthought.
- Run experiments: A/B tests of prompts, models and skills; capture in-tool feedback (ratings, edits, overrides).
- The agent lifecycle itself runs the loop: Periodic Review (monthly or quarterly) → Decide (keep · vN+1 · retire), on a continuous Assess → Prioritize → Execute → Measure → Adapt 90-day cadence.

**Primitives governed.** Continuous Learning Loop, Loop cadence, Decision log, Golden set, Offline Human Alignment pipeline, Correction Capture, Feedback / Rating Loop, Periodic Review.

**Related.** P16, P17, P10.

**Source.** Continuous Learning Loop: From Pilot to Platform; Offline Human Alignment & Analysis; Agent Lifecycle Evaluation; What Scale Demands (Continuous Learning).
