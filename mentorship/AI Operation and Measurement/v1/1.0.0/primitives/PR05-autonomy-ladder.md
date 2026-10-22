# PR05 · Autonomy ladder primitives

The objects that define how much an agent may do on its own, and how that changes. Governed by P10, P11, P12, P21.

## Maturity levels (per agent)

| Level | Name | Characteristics | Human role · loop mode | Promote to next when… |
|---|---|---|---|---|
| 0 | Experimental | AI exploration; individual tools, no governance | Human does the work · no loop | Use case, owner and baseline metrics defined |
| 1 | Assisted | Copilots; fragmented telemetry | Human drives every step, AI suggests · no loop | Telemetry captured end to end on the common platform |
| 2 | Standardized | Common platform; approved models, tools, standards | Human approves every output · open loop (HITL) | Offline eval meets baseline; human alignment labels in place |
| 3 | Governed | Controlled agents; policy-as-code, HITL, audit | Human approves each action · open loop (HITL). **Ceiling for high-risk agents** | Pilot SLOs met; human review finds no new failure modes; AI Yield > 1.0 |
| 4 | Agentic | Multi-step autonomy: workflows, DAGs, memory, tools | Human supervises, steps in on alerts · closed loop (HOTL) | Verification pipeline and supervisor alerts hold SLOs for a full review period |
| 5 | Adaptive | Dynamic systems: routing, optimization, self-evaluation | Human sets policy, agent self-evaluates · closed loop (HOTL). **Ceiling for medium-risk agents** | Self-evaluation agrees with human audits; error budget intact |
| 6 | Autonomous Enterprise | Outcome-driven, closed-loop execution with bounded governance | Human out of the loop; humans govern bounds and audit · sealed closed loop. **Low-risk agents only** | Top level: stays while AI Yield > 1.0 and SLOs hold; otherwise demote |

## Loop modes and oversight terms

| Term | Definition |
|---|---|
| **No loop** | Human does or drives the work (L0–1). |
| **Open loop · Human-in-the-Loop (HITL)** | Active human intervention: a human approves each output/action. Guards against comprehension debt but cannot scale with agent output (the Agentic SDLC Throughput Paradox). L2–3. |
| **Closed loop · Human-on-the-Loop (HOTL)** | Passive supervision: the verification pipeline and feedback telemetry (SQY) self-regulate while a supervisor governs from outside, intervening on flagged exceptions. L4–5. |
| **Sealed closed loop · Human-out-of-the-Loop** | Full automation: execution, verification and deployment run inside the boundary; humans govern bounds and audit after the fact. L6, low risk only. |
| **Human-in-Command (HIC)** | Humans retain overall authority and can override the system. Listed as a mode that, with HOTL, is downgraded to HITL on breach; not further defined on the board. |

## Ceilings and budgets

| Primitive | Definition |
|---|---|
| **Risk class** | High (regulated, financial, safety, irreversible) · Medium (customer-facing, reversible) · Low (internal, easily reversed). |
| **Risk ceiling** | Highest level an agent may reach by risk class: high → L3 (HITL) · medium → L4–5 (HOTL) · low → L6. A ceiling is a design choice, not a failure. |
| **Stage ceiling** | Highest level the organization's rollout stage unlocks: Stage 1 → L0–2 · Stage 2 → L3 · Stage 3 → L4–5 · Stage 4 → L6 (low risk only). |
| **Effective ceiling** | The lower of stage ceiling and risk ceiling. |
| **Autonomy budget** | Per-agent allowance of autonomous execution privileges; throttled or revoked by the control plane when SQY or stability degrades. |
| **Exception above risk ceiling** | Granted only by Risk & Compliance Owner + CISO, time-boxed, recorded in the audit trail. The Agent Owner cannot grant it. |

## Promotion and demotion

| Primitive | Definition |
|---|---|
| **Promotion gate** | Evidence required to move up exactly one level: offline eval meets baseline on the agent's eval set · SLOs held for a full review period with error budget intact · verification pipeline catches failures before output and human review finds no new failure modes · AI Yield > 1.0 at Periodic Review · telemetry and audit trail complete for every action. No skipping levels. Decided by the AI Transformation Lead on the Agent Owner's evidence; Risk & Compliance co-signs for high risk. Never automatic. |
| **Demotion** | SLO breach or error budget exhausted → drop one level, restore the human checkpoint · comprehension debt rising → back to HITL · incident or policy violation → back to L3, review before re-promotion · major change to model, prompts or tools → vN+1 re-enters at Design & Baseline. Decided automatically by the Autonomy Budget Governor or by the Agent Owner. Stands while appealed; never overridden. |
| **Progressive Autonomy / Earned Trust** | The maturity ladder as a coordination pattern: oversight relaxes as verified success rises. |
| **Delegation by level** | L0–2 suggest only, human takes every action · L3 acts, human approves each change before it lands · L4–5 acts alone inside scope, human watches and samples · L6 acts autonomously on low-risk work with a full audit trail. |
| **Agent-to-agent delegation rule** | Only to an agent at the same or lower level; receiver inherits the stricter scope; the orchestrator's Agent Owner is accountable for the whole chain. |

## Agent Lifecycle Evaluation (six stages, each measured on AI Yield)

| Stage | What happens | Gate |
|---|---|---|
| 1 · Design & Baseline | Define the job, owner, autonomy level (HITL → HOTL) and AI Yield target; build the golden set; record pre-agent baseline cost | Success criteria and target signed off |
| 2 · Offline Evaluation | Run against the human-labelled golden set: precision and recall, rubric scores, safety tests; estimate Step 2 costs | Clears the bar on unseen golden-set items |
| 3 · Pilot (HITL) | Limited users; a human reviews every output; measure Accepted Outcomes, Verification Tax and Rework Tax on real work | Pilot AI Yield ≥ 1.0, zero guardrail violations |
| 4 · Production (HOTL) | Scale out under SLIs, SLOs and error budgets; humans supervise from outside; sampled outputs go back to labelling | SLOs held, error budget not exhausted |
| 5 · Periodic Review | Monthly or quarterly per agent: AI Yield and Net AI Value; check drift; re-sample unseen golden-set items | |
| 6 · Decide | **Keep running** (AI Yield > 1.0 and SLOs met) · **New version vN+1** (AI Yield < 1.0 but fixable, or a model/tool/policy change; re-enters at stage 1 and earns autonomy back) · **Retire** (no longer needed, superseded, or AI Yield < 1.0 with no fix; archived with prompts, evals, telemetry, audit trail) | |

Mapping: lifecycle stages 1–2 ↔ levels 0–2; Pilot ↔ L3; Production ↔ L4–6. Runs on a continuous Assess → Prioritize → Execute → Measure → Adapt 90-day loop.

**Source.** Maturity Model + Loop Engineering; Maturity levels in detail; Agent Lifecycle Evaluation; HITL vs HOTL; Agent Responsibility; Human Responsibility (decision rights).
