# PR06 · Coordination pattern primitives

The approved vocabulary for how agents work with agents and how humans work with agents. Each pattern carries an approval status: **Approved default**, **Approved (with condition)**, **Proposed**, or **Not yet approved**. Governed by P06, P12, P21, P22.

## Agent ↔ Agent

### Who directs the work
| Pattern | Definition | Status |
|---|---|---|
| **Delegation** | One agent spawns another for a subtask. | Approved default |
| **Orchestrator–Worker** | One coordinator splits the plan, assigns tasks, merges results. | Proposed |
| **Hierarchical / Tiered** | Supervisors of supervisors: Portfolio → Delivery → CI/CD. | Proposed |
| **Router / Dispatcher** | Classifies each request and routes it to the right specialist. | Proposed |

### How work flows
| Pattern | Definition | Status |
|---|---|---|
| **Handoff Contract** | Explicit schema between tiers: goal · constraints · evidence · open questions. | Approved default |
| **Pipeline / Sequential Chain** | Each output is the next input: spec → code → test → review. | Proposed |
| **Fan-out / Fan-in** | Same task split across agents in parallel; results merged. | Proposed |

### How agents check each other
| Pattern | Definition | Status |
|---|---|---|
| **Creator–Verifier** | One agent builds, a different agent checks. Separation of concerns; enforces creator ≠ approver. | Approved default |
| **Reflection / Self-Critique** | Agent reviews and revises its own output before release. Cheaper, weaker. | Proposed |
| **Ensemble / Majority Vote** | Several agents answer independently; a judge or vote picks. High-risk only. | Proposed |
| **Debate / Adversarial Critique** | Two agents argue opposite sides; a judge decides. Red-Team Agent for safety. | Proposed |

### How agents communicate
| Pattern | Definition | Status |
|---|---|---|
| **Broadcast** | One agent sends status and shared context to many; coherence. | Approved with a channel contract |
| **Message Queue / Event Bus** | Async buffered messages with a durable log. Auditable alternative to direct talk. | Proposed (as replacement for Direct Communication) |
| **Federated Coordination** | Separately governed environments cooperate via contracts, no shared internals. | Proposed |
| **Direct Communication** | Agents talk peer to peer without a coordinator. | Not yet approved (hard to audit); requires a Supervisor and full trace |
| **Shared State / Blackboard** | Agents coordinate through a common, self-managed workspace. | Not yet approved; requires a Supervisor and full trace |
| **Negotiation / Auction** | Agents bid for tasks or bargain over resources. | Not yet approved; requires a Supervisor and full trace |

## Human ↔ Agent

### Where the human sits
| Pattern | Definition | Status |
|---|---|---|
| **Human-in-the-loop Escalation** | Pauses and routes to a named human on confidence, risk or policy thresholds. | Approved default |
| **Approval Gate (HITL)** | Every action in a class needs sign-off before it runs. Levels 0–3. | Proposed |
| **Human-on-the-loop Supervision (HOTL)** | Agent acts alone; human watches telemetry, intervenes on exceptions. Levels 4–5. | Proposed |
| **Veto / Kill Switch** | Human can stop any agent at any time, independent of escalation. | Proposed |
| **Human-out-of-the-loop + Audit** | Full autonomy in a sealed scope, reviewed after the fact. Level 6, low risk. | Proposed |

### How humans and agents share work
| Pattern | Definition | Status |
|---|---|---|
| **Copilot / Suggest-and-Accept** | Agent proposes, human accepts or edits each item. Source of the Verification Tax. | Proposed |
| **Draft-and-Review** | Agent delivers a whole artifact; human reviews it as a whole, not line by line. | Proposed |
| **Pair Collaboration** | Shared session; either side takes the next step, as in pair programming. | Proposed |
| **Intent Confirmation** | Agent restates what it will do and waits for a yes. Irreversible actions only. | Proposed |
| **Clarification / Interview** | Agent asks before acting instead of guessing; cuts rework on thin specs. | Proposed |

### How humans correct and teach agents
| Pattern | Definition | Status |
|---|---|---|
| **Correction Capture** | Human edits to agent output become test cases or prompt changes. | Proposed |
| **Feedback / Rating Loop** | Accepted and rejected outputs feed the agent's evaluation sets. | Proposed |
| **Progressive Autonomy / Earned Trust** | Oversight relaxes as verified success rises; the maturity ladder as a pattern. | Proposed |

### Safety
| Pattern | Definition | Status |
|---|---|---|
| **Circuit Breaker / Fallback** | Stop on error budget or loop detection; fall back to a human or safe mode. | Approved default |
| **Budget Governor** | Throttle or stop when cost or autonomy quotas are hit (the Autonomy Budget Governor). | Proposed |
| **Sandbox-then-Promote** | Act in an isolated copy first; a human or verifier promotes the result. | Proposed |

## Wiring: which pattern each tier uses

- **Executive Agent** → Creator–Verifier + Human-in-the-loop before distribution.
- **Portfolio → Delivery → CI/CD** → Delegation + Handoff Contract.
- **CI/CD** → Creator–Verifier + policy gates + Circuit Breaker.
- Direct Communication, Shared State and Negotiation are not yet approved (hard to audit); they require a Supervisor and full trace. Message Queue / Event Bus is the proposed auditable replacement for Direct Communication.

**Source.** Agent to Agent and Human to Agent coordination patterns; WIRING note (NOTES csv); Shared Capability Map (Reusable assets: coordination patterns).
