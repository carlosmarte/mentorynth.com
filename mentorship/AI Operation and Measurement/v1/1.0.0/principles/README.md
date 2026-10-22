# Principles · AI Operation and Measurement framework

The core beliefs that govern how the framework's primitives (see `../primitives`) are combined. Extracted from the DRAFT board (2026-10-22) and the NOTES csv. Each file states the principle, why it holds, the concrete rules it implies, the primitives it governs, and where on the board it comes from.

## Measurement
- [P01 · Measure outcomes, not activity](P01-measure-outcomes-not-activity.md) — activity metrics are SLIs, never key results; the Amplified Illusion is a loss.
- [P02 · Telemetry first](P02-telemetry-first.md) — instrument and baseline before building the platform; ≥95% traced runs.
- [P03 · Net, not gross](P03-net-not-gross.md) — subtract the taxes; count every hour once; Net Productivity Gain is the source of truth.
- [P04 · Only Production-Qualified Changes count](P04-only-production-qualified-changes-count.md) — generated output is gross, qualified output is net.
- [P07 · Every number traces to an outcome](P07-every-number-traces-to-an-outcome.md) — OKR → Quality Dimensions → SLI → SLO → SLA at every tier.
- [P08 · Promise less than you target](P08-promise-less-than-you-target.md) — SLO tighter than SLA; the error budget decides.
- [P19 · Read every metric through a lens; never rank individuals](P19-read-every-metric-through-a-lens.md) — L / M / IC lenses; SPACE rules of use.

## Verification and control
- [P05 · Intent is the durable artifact](P05-intent-is-the-durable-artifact.md) — Spec-Driven Development; fix the spec, not the code.
- [P06 · Creator is never approver](P06-creator-is-never-approver.md) — separation of duties for humans and agents alike.
- [P09 · Verification must be mechanical](P09-verification-must-be-mechanical.md) — human attention cannot scale with agent output.
- [P11 · Stability beats speed](P11-stability-beats-speed.md) — the control plane throttles automatically.
- [P21 · Hold the sweet spot](P21-hold-the-sweet-spot.md) — between over-constrained and under-governed.
- [P22 · Bound the blast radius](P22-bound-the-blast-radius.md) — sandbox, scoped identity, policy before action, progressive delivery.

## Autonomy and accountability
- [P10 · Autonomy is earned one level at a time](P10-autonomy-is-earned.md) — promotion gates, demotion, risk and stage ceilings.
- [P12 · Stop beats go: humans own the outcome](P12-humans-own-the-outcome.md) — named human decisions, precedence, escalation queues.
- [P20 · No Shadow AI](P20-no-shadow-ai.md) — every agent has a catalog entry and a named owner.

## Value and portfolio
- [P13 · Freed capacity is only value when reallocated](P13-freed-capacity-must-be-reallocated.md) — CRV; leadership owns reallocation.
- [P14 · Optimize the value stream and price time](P14-optimize-the-value-stream-and-price-time.md) — velocity deltas; Cost of Delay, CD3, WSJF.

## Platform and scaling
- [P15 · AI amplifies platform quality; it does not fix it](P15-ai-amplifies-platform-quality.md) — platform quality, workflow clarity, team alignment over tool procurement.
- [P16 · Sequence the rollout and budget the tuition](P16-sequence-the-rollout-and-budget-the-tuition.md) — four stages, five pillars, the J-curve.
- [P17 · Reuse before rebuild](P17-reuse-before-rebuild.md) — one platform, N instances; Shareable / Repeatable / Reusable.
- [P18 · Learn continuously and codify](P18-learn-continuously-and-codify.md) — Adopt → Measure → Learn → Improve & Codify → Scale & Share.

## Principle → primitive family map

| Principle | Primitive families it governs |
|---|---|
| P01, P03, P13, P14 | PR02 Value and economics |
| P02, P07, P08, P19 | PR01 Measurement chain |
| P04, P05, P09, P19 | PR03 Quality and yield indicators |
| P20, P22 | PR04 Agent declaration |
| P10, P11, P12, P21 | PR05 Autonomy ladder |
| P06, P12, P21, P22 | PR06 Coordination patterns |
| P06, P08, P09, P11, P22 | PR07 Control primitives |
| P04, P05, P17, P18 | PR08 Work artifacts and contracts |
| P15, P17, P22 | PR09 Platform and capability |
| P07, P12, P16, P18, P19 | PR10 Operating model |

Sources: `../DRAFT_2026-10-22_18-18-40.pdf` (board export), `../NOTES_2026-10-22_18-18-40.csv`.
