# P02 · Telemetry first: you cannot govern what you cannot see

**Statement.** End-to-end run tracing, cost attribution and pre-AI baselines come before the agent platform is built. Priority #1 of the whole framework.

**Why.** Without telemetry there are no baselines, no Verification Tax, no error budgets, and every later decision is argued from opinion instead of evidence. Launching agents first and "adding observability later" loses the pre-AI baseline for good, makes the Delivery J-curve dip look like failure, and leaves Shadow AI unseen.

**Rules.**
- One trace ID per task, linking prompt → agent → tool → output → review → merge.
- A complete trace captures: who/what (user, team, role, agent ID and version, model, skill); every step (prompt, retrieved context, tool and MCP calls, outputs, latency, tokens, cost); human touchpoints (accept/edit/reject, overrides, HITL approvals, review time); outcomes (build/test result, merge, defects traced to AI, rollbacks); safety events (policy and secret violations, guardrail blocks).
- Exit criteria before platform build-out: ≥95% of agent runs traced end to end; Dimensions SLI dashboards live by lens (L/M/IC); baselines captured for every in-scope workflow; Verification Tax and Net Time Saved computable straight from logs; PII/secret redaction and retention approved; alerts wired to SLOs and error budgets.
- Order of work: 1) Instrument, 2) Baseline, 3) Build the platform, 4) Scale with evidence.
- Costs (TCO, AI Yield) are computed from traces and cost tags, never estimated.

**Primitives governed.** Trace, Baseline, Harness guarantees, Delivery Telemetry & Metrics Layer, Observability Agent, Stage 1 exit gate.

**Related.** P07 (cascade), P16 (Stage 1 is Foundation).

**Source.** Telemetry First Platform Solution; Platform Enablement (Telemetry & observability); Phased Rollouts Stage 1.
