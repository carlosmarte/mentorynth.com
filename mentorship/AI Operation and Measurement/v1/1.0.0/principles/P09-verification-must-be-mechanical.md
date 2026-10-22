# P09 · Verification must be mechanical and scale with generation

**Statement.** Because human attention cannot scale with agent output, verification has to be an automated, continuous auditor of agentic output: pre-commit checks, CI/PR gates, specification and mutation tests, multi-agent review and post-merge fuzzing. Line-by-line human review is the bottleneck to remove, not the control to rely on.

**Why.** DORA research: effort saved during generation is transferred to the review phase. AI-assisted PRs average ~400 lines vs ~150 manual and wait up to 4.6× longer for review. If review capacity does not scale with generation capacity the repository bottlenecks and AI's promised velocity is negated (the Agentic SDLC Throughput Paradox). Reviewers approving code they do not understand to keep the pipeline moving is how comprehension debt accrues. The Verification Tax is the largest tax line and the one policy can move.

**Rules.**
- Mechanical Verification Pipeline components: pre-commit checks; CI/PR gates; mandatory static analysis and security scanning on every AI-generated change; Isolated Specification Tests; mutation-tested suites (score mutation, not line coverage, to catch tests that execute everything and assert nothing); multi-agent PR review; continuous post-merge analysis / fuzzing.
- Teams configure thresholds, not tooling; the pipeline is a shared capability.
- The pipeline must be paired with an automated Control Plane (see P11).
- Track PR Review Saturation: PR pickup time, median review time, % merged without adequate human review.
- Stage 2 exit gate: verification pipeline live and Verification Tax falling.
- The Agentic SDLC Integration Gatekeeper rejects PRs before a human ever sees the diff if baselines are not met.
- Read FAR and FRR together: a gate too lenient lets flawed output through (FAR); a gate too rigid throws usable output away and drives abandonment (FRR).
- Verification queues add delay on top of the tax; a faster pipeline cuts both.

**Primitives governed.** Verification Pipeline, Isolated Specification Tests, Mutation testing, PR Review Saturation, FAR/FRR, Agentic SDLC Integration Gatekeeper, Coverage & Mutation Auditor, Mutation Test Generator.

**Related.** P05, P06, P11, P03.

**Source.** HITL vs HOTL (Mechanical verification pipeline); Review Agent Skills (Enforcing the Process Structurally); Protecting Long-Term Tech Health; Output Quality: FAR vs FRR; Shared Capability Map (2 · Verification Pipeline Service).
