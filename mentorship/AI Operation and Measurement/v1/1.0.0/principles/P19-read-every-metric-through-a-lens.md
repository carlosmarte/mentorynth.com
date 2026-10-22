# P19 · Read every metric through a lens; never rank individuals

**Statement.** The value of an agent means something different depending on where you sit. Every indicator is read through one of three lenses, Leadership, Middle management or Individual contributor, and individual-level telemetry is reported at team level to improve the system, never to rank people.

**Why.** A metric that signals a major bottleneck to a developer is noise to an executive. Measuring raw generation volume rewards bloated repositories and ignores developer experience. Perception is not velocity: developers can feel 20% faster while measured 19% slower.

**Rules.**
- Leadership lens (strategic ROI and risk): Economics, Safety & Security, macro-adoption. Read together: token consumption vs usage vs capacity offload (heavy spend with high rework and verification means AI is a tax); critical vulnerabilities and secret violations; MAU and role adoption coverage (licenses must not become shelfware).
- Middle-management lens (velocity and process): Quality, Reliability, targeted adoption. Read together: acceptance/rejection ratio with AI output edit rate (lots of generated code plus hours of rework is friction, not velocity); build/test success and AI-related defects; team adoption coverage.
- IC lens (friction and flow): Performance, Availability, micro-adoption. Read together: IDE responsiveness and operation latency (when they slip, users switch the tool off and go dormant); instruction adherence and override/fallback frequency; CPU throttling and memory pressure.
- SPACE rules of use: track at least three of the five dimensions (Satisfaction, Performance, Activity, Communication, Efficiency), mixing perception (S) with system telemetry (P, A, E); never use a single metric or Activity on its own; report at team level, not to rank individuals; a DevEx SLO breach triggers the same Learn → Improve & Codify step as an error-budget burn.
- Pair S (perceived speed) with P (acceptance weighted by rework): a widening gap is the early warning for comprehension debt.
- Individual productivity is a net number: time-to-first-draft alone overstates the gain.
- Each tier has its own ROI question and its own middle-management scorecard; metrics must not be read out of context across tiers.

**Primitives governed.** Lenses (L / M / IC), SPACE dimensions, Dimensions SLI dictionary, DevEx SLOs, tier scorecards.

**Related.** P03, P07.

**Source.** Dimensions: Telemetry & ROI by organizational tier; SPACE Framework: Measuring the Individual Contributor & Developer Experience.
