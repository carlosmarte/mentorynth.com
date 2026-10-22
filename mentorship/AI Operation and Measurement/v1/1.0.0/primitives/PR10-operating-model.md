# PR10 · Operating model primitives

The organizational units: stages, pillars, loops, roles and decision rights. Governed by P07, P12, P16, P18, P19.

## Rollout stages (organization-wide, time-boxed)

| Stage | Timing | Pillars built | Agent levels unlocked | Exit gate (telemetry-computed) | Team |
|---|---|---|---|---|---|
| **1 · Foundation** | Months 1–3 | 1 Adoption · 5 Governance | 0–2 (human approves every output) | Telemetry First criteria: ≥95% runs traced · pre-AI baselines · SLI dashboards by lens · redaction and retention approved · 100% of agents in the Agent Catalog | ~6–10 core + middle-management liaisons |
| **2 · Optimization** | Months 4–6 | 2 Proficiency · 4 Reliability | up to 3 (HITL pilots) | Verification pipeline live · Verification Tax measured and falling · offline eval suite per agent · HITL pilots hold SLOs | ~15–25 |
| **3 · Value Realization** | Months 7–12 | 3 Throughput · Productivity Roof | up to 5 (HOTL) | AI Yield > 1.0 on top workflows per function · telemetry joined to CRM/ERP/ITSM · error budgets and Governor enforcing demotion automatically | ~30–50 per wave, ~10–15 teams |
| **4 · Continuous Excellence** | Months 13+ | all five | 6, low-risk only | Ongoing: quarterly total cost vs audited P&L · agents with Verification Tax above time saved retired or re-versioned · full audit trail for every L6 agent | ~10–15 standing CoE + BU champions |

Stage 1 works from two angles that **meet in the middle**: top-down (leadership defines OKRs, SLAs, Total NPG and distills them into middle-management scorecards) and bottom-up (teams build Agent Catalog, harness, guardrails, SLIs, baselines), connected by middle managers.

## Structural model

| Primitive | Definition |
|---|---|
| **Five Pillars** | 1 Adoption · 2 Proficiency · 3 Throughput · 4 Reliability · 5 Governance. Built through the stages. |
| **Productivity Roof** | The top layer the pillars support (Tier 4 / C-level): throughput as accepted outcomes per unit of capacity. Reached in Stage 3. |
| **Six domains** | The framework's six operating domains, rolled out in sequence to avoid overload. Named on the board but never listed together (glossary flag). Those identifiable from section names: Ownership & Delegation · Measurement (The What) · Agent Building · Platform Enablement · Portfolio Governance · Continuous Learning. |
| **Value stream** | One cross-functional team (product, tech, design, BA, QA, GTM) owning one outcome end to end; the Repeatable unit instantiated from the tier template with its own owners, OKRs and targets. Stages: ① business analysis → ② product & design → ③ development → ④ QA → ⑤ marketing/GTM. |
| **Agent tiers per value stream** | Executive · Portfolio · Delivery · CI/CD agent tiers, each with a tier contract card. |
| **Lenses** | L Leadership · M Middle management · IC Individual contributor (see PR01). |
| **Framework goals** | 1 Measure outcomes, not activity · 2 Govern every agent · 3 Earn autonomy safely · 4 Protect quality, shrink the Verification Tax · 5 Reuse before rebuild · 6 Meet in the middle · 7 Learn continuously · 8 Operate at scale. |

## Continuous Learning Loop

| Step | Content |
|---|---|
| **1 · Adopt** | Onboard the next wave on golden paths: catalog-approved agents, templates, durable skills. A champion in every value stream. |
| **2 · Measure** | Instrument the Dimensions SLIs from day one; roll up via the OKR → Telemetry cascade. |
| **3 · Learn** | Review signals by lens: weekly team retros (IC) · monthly value-stream reviews (M) · quarterly OKR resets (L). Find where the J-curve dip is deepest and why. |
| **4 · Improve & Codify** | Turn fixes into reusable assets (prompts, skills, guardrails, runbooks). Recalibrate autonomy (HITL ↔ HOTL) against error budgets. |
| **5 · Scale & Share** | Promote proven local tools into shared capabilities. Publish playbooks. Retire low-ROI workflows. |

Runs once per rollout wave and continuously inside each team; each wave's learnings become the next wave's starter kit. Related loop: Assess → Prioritize → Execute → Measure → Adapt (90-day transformation loop).

## Responsibility pyramid (The How)

| Pyramid layer | Tier | Owners | Core mandate |
|---|---|---|---|
| **ROI · Strategic Direction** | 1 · Senior leadership | Executive Sponsor (CEO/CTO/CIO) · Board / Enterprise Strategy | Set direction, ROI thesis and risk tolerance; fund the J-curve; prioritize long-term ROI over task speed; optimize for Net Delivery Capacity; strict oversight of agents (data lineage, prompt monitoring). |
| **Control functions** | 2 | CISO / Security · Risk & Compliance · Legal & Privacy · Finance (CFO delegate) · Data Governance | Set the policy every agent must pass: identity and secrets, policy set and audit evidence, PII/residency/IP rules, cost quotas and TCO model, data classification and lineage. |
| **TCO · Strategic Direction (portfolio)** | 2 | Portfolio Governance Owners · Value Stream Owner · Product Owner | Decide which initiatives to pursue, continue or stop; own the TCO model; own the stream's NPG target; decide which agent-eligible work goes first. |
| **Implementation Roadmap** | 3 · Funding & prioritization | AI Transformation Lead · Agent Owner · Value Stream Owner (delegated) | Own the phased rollout, stage gates and HITL ↔ HOTL recalibration; each registered agent's promotion/demotion/retirement; the OKR → SLO cascade and baselines per stream. |
| **Production-Qualified Change** | 4 · Product delivery | Engineering Manager / Tech Lead · Specification Engineer · QA / Verification Owner | Accountable for every PQC and the qualification vector; author specs and refine them on failure; own verification thresholds and FAR/FRR targets. Diagnose and prevent the Amplified Illusion. |
| **Platform Enablement & DevEx** | 5 · Platform | Platform / DevEx Owner · Platform Governance Owners · SRE / Reliability Owner · Agentic Platform Owners | Runtimes, control plane, AI gateway, skill registry, telemetry; SLOs, error budgets and the Autonomy Budget Governor; the Verification Pipeline; throttle autonomy when stability or Quality Yield degrades. |

**Agentic Platform Owners:** Agentic Platform Owner (harness, orchestration runtime, roadmap; decides what is built once and shared) · Agent Catalog Steward (no catalog entry, no run) · Agent Identity & Access Owner (with CISO) · Agent Environments Owner · Orchestration & Coordination Owner (patterns, hand-off and escalation protocols, escalation queues and their response SLOs) · Skills, Tools & Context Owner · Agent Evaluation & Safety Owner (offline eval harness, red-team tests, guardrail library feeding every promotion gate).

Flow: mandates and "what matters" cascade down; evidence, metrics and exceptions flow up.

## Decision rights

| Decision | Decides | Consulted | Enforced by |
|---|---|---|---|
| Set intent and risk appetite | Executive Sponsor | Control functions turn it into policy | Policy |
| Register an agent | Agent Owner (named), with risk tier, four facets, catalog entry | Agent Catalog Steward | Agent Catalog |
| Promote one level | AI Transformation Lead, on the Agent Owner's evidence | Risk & Compliance (high risk) | Stage gate in PQC |
| Demote | Autonomy Budget Governor (automatic) or Agent Owner | SRE | Control plane |
| Take offline | Agent Owner, SRE on-call or CISO; nobody needs to approve | | Control plane kill switch |
| Exception above risk ceiling | Risk & Compliance + CISO, time-boxed | Agent Owner (cannot grant) | Policy engine |
| Cost quota change | Finance Owner | Value Stream Owner | AI gateway |
| Retire / version N+1 | Agent Owner, after Periodic Review | Value Stream Owner | Agent Catalog |
| HITL ↔ HOTL switch | AI Transformation Lead | SRE (error budget) | Control plane |
| Accept a production change | Engineering Manager / Tech Lead, whoever wrote it | | PQC gate |
| Own the spec | Specification Engineer | | |
| Appeal an automatic demotion | Agent Owner → AI Transformation Lead, with evidence | | Demotion stays in force while the appeal runs |

**Precedence (who wins):** 1 Policy beats everything below it · 2 stage ceiling and risk ceiling beat any owner's request · 3 automatic demotion stands, appealable not overridable · 4 stop beats go · 5 within those bounds the Agent Owner decides.

**Source of truth when sources disagree (proposed):** what the agent should do → spec · what is happening → production telemetry · code is evidence, never authority over the spec · spec/production conflict → agent stops and escalates to the Specification Engineer.

**Shared accountability:** the agent produces the evidence, the human owns the outcome · one accountable owner per metric · every escalation lands in a named human's queue with a response SLO · autonomy is earned and re-earned at each Periodic Review.

**Single pipeline, Single Number Rule:** rule enforced by the Ownership and Delegation domain to eliminate governance ambiguity; named but not further defined on the board.

**Skill progression (people):** Reviewer → Specification Engineer → Agent Owner → Value Stream Owner, earned through Proficiency evidence tracked in SPACE.

## Scale concerns (What Scale Demands)

| Dimension | What breaks | What addresses it |
|---|---|---|
| **Adoption** | Uneven uptake (power users vs shelfware) · trust gap from rework and override/fallback · Product, QA, Ops left behind Dev · change fatigue in the J-curve | Executive sponsorship + middle-management scorecards · AI champions network with protected time · role-based learning paths · office hours and pairing · license budget tied to active use · acceptable-use policy and safe-to-try zones · support desk SLA ≤ 30 min · recognition for reuse |
| **Integration** | Agents bolted on, not designed in · fragmented toolchains, APIs, schemas · context gaps (low repo AI-knowledge coverage) · Verification Tax shifting load to reviewers | MCP servers / connectors · harness with HITL/HOTL controls and audit trail · AI-aware CI/CD gates · observability (traces, SLIs, error budgets) · reference architectures and API/schema contracts · curated context (repo indexing, domain packs) · integration engineers embedded in value streams · time to redesign workflows |
| **Rollout** | J-curve dip per wave · Shadow AI and duplicate tools · uneven guardrail coverage · token cost growing faster than value | Readiness criteria per wave · error-budget rule (pause or roll back) · portfolio review halting low-ROI scale-up · a named owner per catalog agent · wave plan ~10–15 teams · tuition budget · security and governance reviewers sized per wave · shared platform with N instances · policy-as-code guardrails, secret scanning, PQC gates · feature flags · token budgets and model routing |
| **Continuous learning** | Telemetry nobody acts on · local wins don't travel · metrics read out of context or gamed · slow feedback from defects to prompts | Loop cadence (weekly/monthly/quarterly) · forum promoting local tools · decision log · evidence-based autonomy recalibration · Dimensions dashboard by lens with a named owner · eval harness (quality, FAR/FRR, adherence) · in-tool feedback capture · experiment tracking · community of practice · playbook and durable-skill repository · retro time in the sprint |

**Source.** Phased Rollouts; Rollout stages ↔ agent levels; Framework Goals; Continuous Learning Loop; The How (Responsibility Pyramid, owners); Ownership and Delegation; What Scale Demands.
