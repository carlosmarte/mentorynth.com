# P05 · Intent is the durable artifact: fix the spec, not the code

**Statement.** Under Spec-Driven Development (SDD) the durable artifacts of a change are the design specifications, architectural constraints and test definitions. Source code is ephemeral, regenerated build output. When generated code fails validation, refine the specification and regenerate; never hand-edit the syntax.

**Why.** Human attention cannot scale proportionally with agent output. Shifting human effort from manual code editing to impact analysis and specification engineering is the structural defense against the Verification Tax and comprehension debt, and it keeps human intent governing autonomous execution without halting delivery on manual review.

**Rules.**
- Regeneration is targeted: agents apply and regenerate only the specific requested change, never the whole codebase and never unprompted refactoring.
- Spec Fidelity (SF) and Specification Execution Rate (SER, % of agentic runs reaching production with no human intervention) replace lines of code as the measures of delivered intent. SER is the proof that the loop is closed.
- Isolated Specification Tests: spec-derived tests run in isolation from the generating agent so it cannot see or game them.
- Source of truth when sources disagree: what the agent should do → the spec wins; what is actually happening → production telemetry wins; code is evidence, never the authority over the spec; spec and production conflict → the agent stops and escalates to the Specification Engineer.
- An agent never edits the spec or tests it is judged against.
- The role shift: from Syntax Reviewer / Manual Code Editor (a bottleneck inside the loop) to Specification Engineer and System Governor (scales the operation from outside the loop).
- This is a transitional shift, not an overnight rollout; each owner needs their own transition plan.
- Platform maturity for SDD has three layers: Intent (codified goals, policies, testable specs), Context (enterprise knowledge, access controls, observability formatted for machines), Agentic (the agents that combine intent and context to act).

**Primitives governed.** Specification, Spec Fidelity, Specification Execution Rate, Isolated Specification Tests, Specification Engineer role, Intent/Context/Agentic layers.

**Related.** P04, P09, P12.

**Source.** Review Agent Skills (The Shift to SDD); HITL vs HOTL (How HOTL is enforced); Human Responsibility ("Own the spec"); Shared Responsibility (source of truth); Platform Quality at Maturity.
