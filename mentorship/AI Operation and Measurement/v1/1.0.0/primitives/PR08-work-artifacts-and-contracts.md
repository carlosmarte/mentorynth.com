# PR08 · Work artifact and contract primitives

The durable, versioned things that work is expressed in and handed over with. Governed by P04, P05, P17, P18.

| Primitive | Definition | Schema / fields |
|---|---|---|
| **Specification** | The durable artifact of a change under Spec-Driven Development: design specifications, architectural constraints and test definitions. Code is regenerated output. | Authored by the Specification Engineer. On failure, refine the spec and regenerate; never hand-edit. The agent may never edit the spec or tests it is judged against. The spec wins over code; production telemetry wins over the spec about what is happening. |
| **Production-Qualified Change (PQC)** | The accepted unit of delivered work (see PR03). | Carries: evidence · review level · gate approval, by risk class and agent level; provenance link to trace and catalog entry. |
| **Handoff Contract** | Explicit schema for passing work between tiers or agents. Approved default pattern. | goal · constraints · evidence · open questions |
| **Tier contract card** | Declares what a tier of the value-stream template is for and how it is governed. Onboarding a value stream = config + tier contract cards. | purpose · inputs · outputs · decision rights · human gate · metrics · owner |
| **Durable skill** | Reusable agent skill template that survives interruption. | externalized state · idempotency ledger · HITL suspend · exit gates. Runtime lives in the Skill & Tool Registry. |
| **Golden path** | Paved-road template and catalog-approved agent set for building, testing and registering agents so teams don't start from scratch. | Owned by the Platform / enablement team. |
| **Golden evaluation set** | Versioned, human-labelled ground truth with a held-out slice never used for tuning. One per value stream. | precision/recall targets · rubric · adjudicated disagreements · label-drift analysis |
| **Prompt and skill versions** | Prompts, skills, evals and workflows under change management with ownership and versioning. | Inner-source library; registered in the Skill & Tool Registry. |
| **Metric definitions** | Canonical definitions pulled into any value stream: SQY · PDE · Production-Qualified Yield · Net Delivery Capacity. | Source of truth: Net Productivity Gain. |
| **Policy-as-code bundle** | Versioned machine-readable policy: separation of duties · data classification · residency. | |
| **Reallocation roster** | Register of Capacity Reallocation Resources. | skills · freed hours/week · current team · target initiative |
| **Decision log** | What changed, why, and its measured effect. | Kept per Continuous Learning Loop cycle. |
| **Portfolio backlog** | Candidate agents and workflows built from the Agent Catalog. | tagged by value stream · risk class · target maturity level · CoD / WSJF score |
| **Stage-gate scorecard** | Telemetry-computed (not self-reported) status of each rollout stage's exit criteria. | S1 ≥95% traced runs, baselines, SLI dashboards by lens, 100% catalog · S2 pipeline live, Verification Tax falling · S3 AI Yield > 1.0 on top workflows · S4 quarterly cost vs audited P&L |
| **Promotion schedule** | Every agent's current level, target level for the stage, and gate status. | The bridge between the roadmap and PQC. |
| **Audit artifact / append-only annotation** | Knowledge artifact appended by portfolio personas to epics, features and stories, translating completion data into product-readable insight and surfacing deviations between what was asked and what was delivered. | Never alters the original ticket or document. |
| **Playbook / runbook** | Codified fixes and procedures (including the Kill-Switch Runbook) produced by the Improve & Codify step. | Published per wave. |

**Source.** Shared Capability Map (Reusable assets); Review Agent Skills (SDD); Implementation Roadmap; Pyramid: PQC; Portfolio Health (reallocation roster); Agent personas (Portfolio).
