# PR04 · Agent declaration primitives

How an agent is described so it can be registered, scoped and governed. Every agent is declared by picking exactly one value from each of four facets; this replaces the flat list of agent types. Governed by P20, P22.

## The four facets

| Facet | Question | Values (from the board and NOTES csv) |
|---|---|---|
| **Runtime** | Where it runs | **Remote Virtual Agent** (remote machine, cloud instance, hosted environment) · **Local Agent** (developer workstation or local infrastructure) · **Container Agent** (Docker or Kubernetes) · **Edge Agent** (near devices, networks or distributed systems) · **microVM Agent** (stronger isolation via lightweight VM) · **Serverless Agent** (short-lived, event-triggered functions; moved here from Trigger) · **GPU Compute Agent** (GPU-accelerated inference or workloads) |
| **Trigger / Lifecycle** | When it runs | **Scheduled Agent** (predefined intervals) · **Event Driven Agent** (webhooks, messages, system events) · **On-Demand Agent** (provisioned when a task, event or workflow requires it) · **Ephemeral Agent** (single-use session or task, works in isolation) · **Pooled Agent** (centrally managed collection of interchangeable agents; work assigned by availability, capability or load) · **Persistent Agent** (continuously available runtime). Consolidation note: On-Demand ≈ Ephemeral (same lifecycle, keep one). |
| **Surface** | What it touches | **Browser Agent** (navigate websites, web UIs) · **Desktop GUI Agent** (native desktop applications) · **Terminal / CLI Agent** (shell commands, development tools) · **IDE Agent** (works inside the editor) · **Mobile Device Agent** (Android / iOS devices or emulators) · **API Agent** (structured APIs) · **Hardware Agent** (interact with and validate physical devices) · **IoT Agent** (sensors, embedded systems, devices) · **Robotics Agent** (robots and physical actuators) |
| **Role** | Place in the topology | **Supervisor Agent** (manage subordinate agents and execution; Orchestrator ≈ Supervisor, keep one) · **Orchestrator Agent** (coordinate workflows and delegated tasks) · **Worker Agent** (specialized delegated tasks) · **Validation Agent** (verify generated outputs and behavior) · **Observability Agent** (collect traces, metrics, execution evidence) · **Recovery Agent** (restore interrupted workflows and failed executions) · **Peer to Peer Agent** (collaborate without a centralized supervisor) · **Federated Agent** (coordinate across independently governed environments) · **Policy / Guardrail Agent** (allow or deny actions against policy-as-code before they execute) *v2* · **Cost / Budget Agent** (track token and infrastructure spend against quotas; throttle or alert) *v2* · **Red-Team Agent** (probe other agents for prompt injection, data leakage, unsafe actions) *v2* · **Human-Escalation Router** (route low-confidence or high-risk decisions to the named accountable human) *v2* |

The Surface facet is enforced by identity: an agent's scoped credentials let it touch only what it was registered for.

## Agent Catalog entry

Registry and single storefront of approved agents and skills. No catalog entry, no run. Target coverage: 100%.

| Field | Meaning |
|---|---|
| Agent Owner | The named human accountable for promotion, demotion and retirement |
| Four facets | Runtime · Trigger/Lifecycle · Surface · Role |
| Risk class / tier | High (regulated, financial, safety, irreversible) · Medium (customer-facing, reversible) · Low (internal, easily reversed). Sets the risk ceiling. |
| Persona | The named role it plays (e.g. Autonomy Budget Governor, PDE Telemetry Synthesizer) |
| Maturity level | Current level 0–6 and target level for the stage |
| Autonomy budget | Per-agent allowance of autonomous execution privileges; throttled or revoked by the control plane |
| Cost quota | Token and infrastructure budget; changed only by the Finance Owner |
| Version | vN; each new version re-enters the lifecycle at Design & Baseline; AI Yield tracked per version |
| Status | Design · Offline eval · Pilot (HITL) · Production (HOTL) · Retired (archived, not deleted) |
| Identity | Own identity and scoped credentials, separate from users |

## Agent persona

A named agent role, grouped into reusable persona views per tier. The board's named personas:

- **Leadership & ROI:** Strategic ROI & Yield Forecaster · TCO & Capacity Allocation · Grassroots ROI & Investment Informer.
- **Delivery health:** Amplified Illusion Detector · Comprehension Debt & SLO Tracker · PDE Telemetry Synthesizer · Architectural Boundary & Scope Enforcer.
- **Quality & verification:** Specification Fidelity (SDD) Validator · Specification Execution (SDD) Auditor · Coverage & Mutation Auditor · Agentic SDLC Integration Gatekeeper · Mutation Test Generator.
- **Platform operations:** Ephemeral Sandbox Orchestrator · Environment Compliance & Drift Auditor · Autonomous Decommissioning Agent · Control Plane Throttler · Autonomy Budget Governor.
- **Governance:** Identity & SoD Gatekeeper · Resource Lineage & Ownership Synthesizer · Delivery Policy & Compliance Auditor.
- **Portfolio:** Strategic Initiative & Epic Tracer · Feature & Capability Synthesizer · PI Objective & Feature Synthesizer · Lean Portfolio & Epic Auditor · WSJF & Capability Forecaster.
- **Tool consolidation:** Local AI Pattern & Consolidation Auditor · Local Harness & Tooling Synthesizer · Feature Generation & Centralization Reporter.

Portfolio personas append annotations; they never alter source tickets or documentation (append-only annotation service).

**Source.** Agent Types as four facets; NOTES csv (TRIGGER / RUNTIME / SURFACE / ROLE areas); Agentic Platform Owners; Agent personas; Shared Capability Map.
