# P15 · AI amplifies platform quality; it does not fix it

**Statement.** AI acts as an amplifier, not a fixer. On a high-quality platform (loosely coupled architecture, clear workflows, fast automated feedback loops) AI tools translate directly into product throughput. On tightly coupled legacy systems with slow manual feedback, agentic AI amplifies the dysfunction, turning generation volume into systemic instability and technical debt.

**Why.** Organizations cannot rely on localized tooling upgrades to mitigate escaped defects and comprehension debt; they must prioritize platform quality, workflow clarity and team alignment over the procurement of advanced coding tools. Teams should build products, not plumbing.

**Rules.**
- Platform teams provision and maintain environments, testing frameworks and deployment setups so product teams focus on Product Delivery Efficiency and producing PQCs.
- Platform Enablement supplies: run tracing and cost attribution on every execution; sandboxed runtimes, scoped credentials, pinned model serving; the Agent Catalog and control plane; golden paths, reusable skills and self-service onboarding; flow metrics split by agent-assisted vs human-only work.
- At maturity the platform shifts from serving human developers to governing what autonomous agents are allowed to do, through the Intent, Context and Agentic layers.
- Protect long-term tech health: track refactoring share, duplication, short-term churn and security flaw rate as tech-health SLIs with SLO thresholds and error budgets. (GitClear: refactoring down >74%, duplicate blocks up 87%, function connectivity down 25%, churn up 88%, 45% of AI code introduces OWASP Top 10 flaws.)
- Enforce architectural boundaries that restrict agents to targeted, localized fixes (Architectural Boundary & Scope Enforcer).
- Time to redesign workflows, not just add tools; agents must be designed into workflows, not bolted on.

**Primitives governed.** Platform Enablement layer, Platform Quality at Maturity, Intent/Context/Agentic layers, tech-health SLIs, Golden paths, Environment catalog.

**Related.** P05, P09, P17.

**Source.** Platform Quality at Maturity; Pyramid: Platform Enablement & Product Delivery Efficiency; Protecting Long-Term Tech Health; What Scale Demands (Integration challenges).
