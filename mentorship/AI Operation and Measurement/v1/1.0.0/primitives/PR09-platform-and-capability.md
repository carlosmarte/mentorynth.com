# PR09 · Platform and capability primitives

The things built once and consumed by every value stream, and the environments agents run in. Scaling model: one shared platform, N value-stream instances. Governed by P15, P17, P22.

## Capability classes

| Class | Definition | Ownership / funding |
|---|---|---|
| **SHAREABLE** | One platform instance for all value streams. | Platform & DevEx; funded centrally. |
| **REPEATABLE** | Template instantiated per value stream, with its own owners, OKRs and metric targets. | Value stream; onboarding = config + tier contract cards; no new platform build. |
| **REUSABLE** | Versioned, change-managed asset pulled into many agents and skills. | Skill & Tool Registry. |

**Promotion path for tools and skills:** 1) grassroots tool built locally → 2) registered and versioned in the Skill & Tool Registry (Reusable) → 3) adopted by 2+ value streams → 4) promoted into the platform, owned by Platform & DevEx (Shareable).

## Shared capabilities (Shareable; one instance each)

| # | Capability | What it does | Serves |
|---|---|---|---|
| 1 | **Delivery Telemetry & Metrics Layer** | DORA / SPACE plus SQY, PDE, Production-Qualified Yield and Net Delivery Capacity, computed once from Harness traces and cost tags. | Leadership & ROI, Delivery health views |
| 2 | **Verification Pipeline Service** | Pre-commit checks, CI/PR gates, mutation testing, spec fidelity checks. Teams configure thresholds, not tooling. | Quality & verification views, CI/CD tier |
| 3 | **Control Plane & Autonomy Budget** | Throttle or revoke autonomy, cost quotas, circuit breaker, kill switch in one place. | Replaces Control Plane Throttler, Autonomy Budget Governor, Cost / Budget Agent |
| 4 | **Environment Lifecycle Service** | Provision → audit for drift → decommission, over Virtual Sandbox, Ephemeral Dev Environment and Micro VM runtimes. | Platform operations views |
| 5 | **Identity, Ownership & SoD** | Identity Broker + Policy Engine + one ownership / resource registry. Creator ≠ approver enforced the same way everywhere. | Governance views |
| 6 | **Portfolio Traceability** | Canonical portfolio data model spanning every tool + append-only annotation service (never alters source tickets). | Portfolio views, Portfolio & Executive tiers |
| 7 | **Skill & Tool Registry** | Versioned, change-managed skills and harnesses, plus the durable-skill runtime (state, idempotency ledger, exit gates). | Tool consolidation views, every agent |
| 8 | **Validation / Creator-Verifier Service** | One independent verifier used by every tier instead of a validator per tier. | Every tier's human gate |

**Foundation (Shareable):** SDK / Harness · Model Gateway · Identity Broker · Policy Engine · Runtime catalog · Coordination patterns.

**Control functions** govern every instance with one policy set: Security · Risk & Compliance · Legal & Privacy · Finance · Data Governance.

**Agent Catalog:** registry and single storefront of approved agents and skills (see PR04).

## Environment catalog

| Class | Environments |
|---|---|
| **Standard Agent Environments** | Cloud Compute (on-demand elastic processing) · Cloud WorkStation (persistent remote development) · Virtual Sandbox (on-demand isolated execution) · Ephemeral Workspace (short-lived provisioned workspaces) · CI Build Runner (automated build and validation) · Browser Worker (browser-based execution) · Persistent Agent Worker (long-running agent execution) · Model Serving Infrastructure (dedicated model endpoints) · AI Gateway (single egress: logging, cost tags, PII filter, rate limits, regional routing) · Policy Engine (policy-as-code gates evaluated before any action) · Agent Identity & Secrets Vault · Micro VM Runtime (stronger isolation boundary) |
| **On Request Agent Environments** | GPU Workstation (GPU-equipped development machine) · GPU Compute (dedicated accelerated processing) · Mobile Dev Environment (mobile development and testing) · Parallel Agent Runners (parallel execution) · Edge / Embedded Device (resource-constrained execution) · Physical Device Lab (testing against physical devices) |
| **Out of Scope** | Personal Device: only managed, compliant developer workstations are permitted; no personal devices. |

Pyramid of the agentic platform: Agentic Platform · Agent Environments · Agent Types (four facets) · Coordination Patterns.

## Platform layers at maturity (for SDD)

| Layer | Contents |
|---|---|
| **Intent Layer** | Codified goals, security policies and testable specifications agents plan against, so they do not hallucinate architectural changes. Where SDD lives. |
| **Context Layer** | Enterprise knowledge, access controls and observability pipelines formatted for machine consumption; the structural boundaries agents need to operate safely. |
| **Agentic Layer** | The autonomous agents that combine intent and context to act without line-by-line human oversight. |

## Platform Enablement capability groups

- **Telemetry & observability:** run tracing per execution (task, persona, model, tokens, tools, outcome, cost); shared metrics store and SLI dashboards by lens; cost attribution per run/agent/workflow.
- **Execution environments & runtimes:** the environment catalog; isolation and secrets management; model serving and routing with version pinning.
- **Agent platform & control plane:** Agent Catalog; control plane; tool and context infrastructure (MCP or equivalent tool servers, approved tool allowlists, retrieval over internal knowledge, shared skills and playbooks).
- **Developer experience & enablement:** golden paths and templates; inner-source library of skills, prompts, evals and workflows; self-service onboarding, docs and training by persona; DevEx surveys and adoption telemetry.
- **Delivery efficiency:** CI/CD and infrastructure-as-code agents can drive safely (ephemeral environment per change, fast feedback, deterministic builds); flow metrics split by agent-assisted vs human-only; capacity management of compute, licence and token budgets with reallocation across teams.

Boundary: Platform / DevEx owns the shared infrastructure (compute, CI, AI gateway, telemetry layer); Agentic Platform Owners own what is specific to agents on top of it.

**Source.** Shared Capability Map (proposed); Human & Agent Environments; Pyramid: Platform Enablement & Product Delivery Efficiency; Platform Quality at Maturity; Agentic Platform Owners.
