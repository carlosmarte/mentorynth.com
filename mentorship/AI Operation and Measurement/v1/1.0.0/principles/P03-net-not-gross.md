# P03 · Net, not gross: every gain is taxed, and every hour is counted once

**Statement.** The real benefit of AI is what is left after the taxes are paid. Report net productivity, tracked separately for humans and agents and then added once. Net Productivity Gain is the source of truth for every productivity term on the board.

**Why.** Gross gain (hours saved, PRs merged, tickets closed) is the headline pilots report. Studies put the Verification Tax at ~37% of gross time savings in typical business work and 25–50% in regulated settings. Experienced developers were measured 19% slower on complex tasks while believing they were 20% faster (METR). A large gross saving can shrink to near zero, or go negative, once the taxes are counted.

**Rules.**
- Taxes subtracted from gross: Verification Tax (checking, testing, explaining, justifying), Rework Tax (fixing or regenerating what was wrong), comprehension debt (later time understanding code nobody wrote), agent run cost (tokens + licences), learning curve and adoption, friction and manual fallback.
- Net time saved (one task) = time AI saves on paper − Verification Tax.
- Individual net time saved = gross time saved − (prompt engineering + debugging + downstream rework).
- Human NPG = manual work removed − supervision (incl. Verification Tax) − learning curve − friction and fallback.
- Agent NPG = net-new agent output − Verification Tax − Rework Tax − comprehension debt − agent run cost.
- Total NPG = Human NPG + Agent NPG. Agent work that replaced a manual task is a Human gain; the Agent side keeps only output nobody would otherwise have produced. Each tax is subtracted once, on the side whose gross created it.
- Four traps this guards against: counting generated output as gain; counting the same hour on both sides; ignoring reallocation; measuring only at agent level when the team or value-stream net is lower.
- Measuring net-new agent output needs an explicit estimate of what a person would have taken; decide who estimates and how, or the Agent side becomes a guess.
- Pair perceived speed (SPACE Satisfaction) with measured performance; a widening gap is the early warning for comprehension debt.

**Primitives governed.** Gross time saved, the taxes, Net time saved, Human/Agent/Total NPG, Net Delivery Capacity, Net AI Value, Workforce Productivity Matrix.

**Related.** P01, P09 (the Verification Tax is the lever policy can move), P13 (CRV).

**Source.** Net Productivity Gain: What Is Left After the Taxes; Formulation (Verification Tax); SPACE Framework; Example: Verification Tax Erodes Gross AI Gains.
