# PR03 · Quality and yield indicator primitives

The indicators that say whether output is good, whether it matched intent, and whether it survived to production. Governed by P04, P05, P09, P19.

## Delivered-work unit and its yields

| Primitive | Definition | Rule / use |
|---|---|---|
| **Production-Qualified Change (PQC)** | The unit of delivered work that counts: a change that passed verification, its promotion gate and every automated gate, and reached production without incident. | Definition of done encoded as policy by risk class and agent level. Feeds Accepted Outcomes (numerator) and TCO (denominator). |
| **Qualification vector** | The full set of evidence, reviews and gates a change must clear before it counts as a PQC: review, integration, DAST, deployment. | Defined by the Engineering Manager / Tech Lead; routed by risk class. |
| **Production-Qualified Yield** | Volume of changes that pass the entire qualification vector first time without triggering an incident. | Leadership-focus metric based on PQC. |
| **Software Quality Yield (SQY)** | Percentage of pull requests (the fundamental unit) that satisfy business specifications on the first pass. Also called Quality Yield. | Bridge to replace OEE's quality (scrap) metric. Low SQY: the AI generates code the organization cannot use without heavy intervention. When SQY drops, autonomy is throttled. |
| **Product Delivery Efficiency (PDE)** | Rate at which generated code survives integration, passes security validation and runs reliably in production. | Counters raw "Author Velocity"; tracks systemic delivery health, not typing speed. |
| **Spec Fidelity (SF)** | Fraction of business requirements and system constraints verifiably satisfied by the AI-generated change. | The acceptance test for a PQC. |
| **Specification Execution Rate (SER)** | Percentage of agentic runs that reach production without human intervention. | The proof the loop is closed; keeps autonomous execution governed by documented human intent. |
| **Verified Task Success** | Share of agent tasks that pass an independent check 15 minutes after running. | Reference SLO 95%; the gate for HITL → HOTL promotion. |
| **Overall Effectiveness (OE / OEE)** | Lean-manufacturing effectiveness measure. | Board maps SQY onto OEE's quality component; cites OE for feedback-loop design. |

## Gate quality

| Primitive | Definition | Signals | Drives |
|---|---|---|---|
| **False Acceptance Rate (FAR)** | Flawed outputs accepted ÷ all flawed outputs. Bad output let through as latent defects. | Escaped defects and hotfixes traced to accepted AI changes; audit failures; security findings after merge. | Rework Tax, technical debt, risk cost; burns error budget; triggers demotion. |
| **False Rejection Rate (FRR)** | Usable outputs rejected ÷ all usable outputs. Good output thrown away by over-rigid gates or misread context. | Prompt iterations per usable output; rejections later overturned; falling active use. | Verification Tax, SPACE Satisfaction and Efficiency, abandonment. |
| **FAR/FRR pattern reading** | | Low/low stable → promotable within risk ceiling. High FAR/low FRR → tighten gate (tests, static analysis, scans), lower autonomy. Low FAR/high FRR → improve context/retrieval, fix skill, recalibrate judge and thresholds. High/high → not fit for task: keep HITL, back to offline eval, vN+1 or retire. | | |
| **Golden set** | Versioned, human-labelled ground-truth dataset with a held-out slice never used for tuning. | Agents evaluated against it for precision and recall; unseen items re-sampled at Periodic Review. | One per value stream (reusable asset). |
| **LLM-as-a-judge** | Language model scoring agent output, combined with heuristic checks, on captured prompt/response traces. | Needs calibration against human audit samples. | |
| **Evaluation flow** | ① Trace (exact prompt + response per run) → ② Evaluate (judge + heuristics) → ③ Gate (human or automated accept/reject) → ④ Audit sample (ground truth) → ⑤ FAR + FRR per agent, per skill, trended. | | |

## Tech-health indicators (Director lens)

| Primitive | Definition | Baseline → post-AI |
|---|---|---|
| **PR Review Saturation** | Downstream bottleneck where AI output outpaces human review. | Indicators: PR pickup time · median review time · % merged without adequate review. AI PRs ~400 lines vs ~150; wait up to 4.6× longer. |
| **Code churn** | Rapid write/delete/rewrite of AI output; high friction and poor initial quality. | +88% short-term churn. |
| **Refactoring (moved code)** | Share of changes that restructure existing code; signals long-term maintenance. | ~21% → <4% of changed lines (down >74%). |
| **Code duplication** | Duplicate blocks; a propagation tax (a bug must be hunted across copies). | ~40 → ~73 instances per million lines (+87%). Function connectivity −25%. |
| **Security flaw rate** | High-severity flaws introduced by AI generation; AI pattern-matches existing vulnerabilities. | Baseline human error rate → 45% of AI code introduces OWASP Top 10 flaws. Hard gate in promotion/demotion; mandatory static analysis and security scanning. |
| **Tech-health pipeline** | ① AI generation (volume) → ② review saturation → ③ merge gate → ④ structural quality → ⑤ long-term tech health (maintainability, debt ratio). | |

## SPACE dimensions (IC / DevEx)

| Dimension | Meaning | AI-era metrics | Signal source |
|---|---|---|---|
| **S · Satisfaction & well-being** | How fulfilled and unblocked people feel; driver is cognitive offloading. | DevEx pulse, perceived productivity, tool satisfaction, cognitive-offload score. Caution: perception ≠ velocity; pair with P. | Survey |
| **P · Performance** | Outcome quality, not output volume. | Acceptance/rejection ratio weighted by rework; escaped defects; hotfixes later in sprint; net time saved. | VCS + agent telemetry |
| **A · Activity** | Counts of actions. | AI sessions, suggestions shown/accepted, tasks completed with an agent, PRs opened. Never lines/words. | Agent + IDE telemetry |
| **C · Communication & collaboration** | How work moves between people and agents. | PR pickup time, reviewer load, handoff quality, reuse of shared prompts/skills/agents. Watch the creator → reviewer shift. | VCS + catalog |
| **E · Efficiency & flow** | Work with minimal friction and interruption. | Time-to-first-draft, context switches (leaving IDE for a browser sandbox), terminal and onboarding friction, focus time. Lever: toolkit/SDK in the local environment with cross-tool session continuity. | IDE / SDK telemetry |

## Dimensions SLI dictionary (what we measure, by lens)

**AI Adoption · usage & reach (10):** Active Users (DAU/WAU/MAU) L·IC · Change in Active Users L · New User Activation Rate L·IC · Dormant User Rate L · Team Adoption Coverage M · Role Adoption Coverage L·M · AI Session Duration IC · Task to AI Conversation Rate IC · Usage vs Capacity Offload L · Workflow Diversity Index M.

**AI Adoption · coverage & utilization (9):** AI Workflow Coverage M · AI Task Coverage M · Use Case Coverage M · Number of Toolchain M · Number of AI Skills M · Skill Utilization Rate M · Agent Utilization Rate L · Repo AI Knowledge Coverage M · Model Utilization Distribution L.

**AI Adoption · output, effort & accuracy (16):** Generate Code Acceptance Rate IC · AI Recommendation Acceptance Rate IC · AI Output Utilization Rate M · AI Output Edit / Change Rate M · AI Code Contribution Rate L · AI-Native Rate L · AI Assisted Rate M · Human In the Loop Rate M·L · PR AI Assistance Rate M · Prompt to Commit M · AI Test Generation Rate M · Instruction Adherence IC · Override and Fallback Frequency IC · Verification (time to verify safe/secure/correct) M·L · Rework (time fixing bad output) M · AI Related Defects M.

**Quality (9):** Build Success Rate M · Test Success Rate M · Acceptance / Rejection Ratio M · FAR M · FRR M · Output Quality (lint, complexity) M · Environment Consistency M · Configuration Drift M · Developer Experience Score IC·M.

**Economics (5):** Token Consumption L·M · Human Rework L·M · Human Verification L · Operation Latency (cost of waiting) L·IC · Model Identification L.

**Reliability (6):** Crash Rate M·IC · Failure Rate M · MTBF M · Kernel / System Errors IC · Tool Failure Rate IC·M · Dependency Failure Rate M.

**Performance (8):** CPU Utilization & Throttling IC · Memory Utilization & Pressure IC · Swap Utilization IC · Disk IOPS & Latency IC · Network Latency IC · GPU Utilization IC · Build & Test Duration IC · IDE (Extension) Responsiveness IC.

**Availability (4):** Uptime % IC · Service Availability IC · Development Environment (Sandbox) Availability IC·M · Tool Availability IC.

**Safety & Security (5):** Critical Vulnerabilities L · Secret Violations M · Policy Violations L · Patch Compliance L · Hardware Health L.

**Environments & Integrations (7):** Environment Setup Time M · Environment Wake Up Time M · Specific Tool Usage M · IDEs / Text Editor, Browser IC · UI Components IC · API Service IC · Schema / Payload IC.

**Recoverability (cascade menu):** MTTR · environment rebuild time · environment setup time · recovery success rate. **Distribution (cascade menu):** agentic assets (skills, prompts, instructions, agents, artifacts) · MCP components · API services · schema contracts.

Industry-standard terms used but not defined on the board: DORA metrics (lead time, deployment frequency, change failure rate, MTTR), MTBF, MTTR, MTTC (< 4 hrs SLA), TTFT/TPOT (P99), HIC, NCU.

**Source.** Indicators; Pyramid: PQC; Output Quality: FAR vs FRR; Protecting Long-Term Tech Health; SPACE Framework; Dimensions (SLI dictionary); Quality dimensions → example SLIs.
