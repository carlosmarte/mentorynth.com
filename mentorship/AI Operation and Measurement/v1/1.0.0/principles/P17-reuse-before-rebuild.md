# P17 · Reuse before rebuild: one platform, N instances

**Statement.** Build each capability once as a shared platform and instantiate value streams from a template on top of it. Each new value stream should cost less than the last.

**Why.** Local wins otherwise do not travel between teams; shadow and duplicate tools spread across value streams; agents get built where they are easy, not where they are valuable. Reuse makes the marginal cost of AI adoption fall as adoption grows.

**Rules.**
- Three capability classes: SHAREABLE (one instance for all, owned by Platform & DevEx, funded centrally), REPEATABLE (template instantiated per value stream with its own owners, OKRs and targets), REUSABLE (versioned asset pulled into many agents and skills).
- Shareable capabilities: Delivery Telemetry & Metrics Layer; Verification Pipeline Service; Control Plane & Autonomy Budget; Environment Lifecycle Service; Identity, Ownership & SoD; Portfolio Traceability; Skill & Tool Registry; Validation / Creator-Verifier Service. Foundation: SDK/Harness, Model Gateway, Identity Broker, Policy Engine, Runtime catalog, Coordination patterns.
- Harness guarantees are stated once for every tier instead of repeated per tier card: trace coverage, session and transaction IDs, replay, golden evaluation sets, cost tags, policy-as-code gates, kill switch.
- Onboarding a value stream = config + tier contract cards; no new platform build.
- Promotion path for tools and skills: 1) grassroots tool built locally; 2) registered and versioned in the Skill & Tool Registry → Reusable; 3) adopted by 2+ value streams; 4) promoted into the platform, owned by Platform & DevEx → Shareable.
- Grassroots innovation is a feature, not a rogue risk: the Local AI Pattern & Consolidation Auditor, Local Harness & Tooling Synthesizer and Feature Generation & Centralization Reporter find and consolidate local tools, filtering out one-off utilities that should not bubble up.
- The Agent Catalog is the single storefront for approved agents and skills. Golden paths are the paved road so teams do not start from scratch.
- Reward reuse and contribution; run a forum that promotes local tools into shared capabilities.

**Primitives governed.** Shareable / Repeatable / Reusable, Shared capabilities, Foundation, Harness guarantees, Skill & Tool Registry, Tool promotion path, Golden paths, Tier contract card.

**Related.** P15, P18, P20.

**Source.** Shared Capability Map (proposed); Framework Goals (Reuse before rebuild, Operate at scale); What Scale Demands; Agent personas (Tool consolidation).
