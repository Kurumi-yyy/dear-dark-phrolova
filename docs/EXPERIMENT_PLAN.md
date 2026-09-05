# Experiment plan

## Primary question

Can a coherent persona improve coding-agent judgment before we add an explicit behavior-correction ruleset?

## Secondary question

When explicit behavior rules are added, do they improve the intended behaviors without making the agent rigid, contrarian, or under-engineered?

## Conditions

For each eval case, compare:

- **A — Baseline:** host/model defaults only.
- **B — Persona:** load `persona/CORE.md` only.
- **C — Persona + behavior:** load `persona/CORE.md` and `persona/BEHAVIOR.md` through the skill wrapper.

Where useful, repeat with multiple models or reasoning efforts, but do not expand the matrix until the initial cases reveal a reason to do so.

## Record

For each run capture:

- model / host / reasoning effort
- case id
- condition A/B/C
- final answer or patch
- rubric scores
- qualitative failure notes
- token / latency / cost if available

## First milestone

A successful v0 experiment should answer:

1. Does persona-only steering move independent judgment and over-engineering behavior at all?
2. Which explicit rules create additional useful lift?
3. Which rules cause regressions such as needless contrarianism, insufficient safety, or refusal to clarify when clarification is genuinely necessary?
4. Is the effect stable enough to justify packaging this as a reusable DDP module?

## Deliberate exclusions

The first experiment does not need:

- a large benchmark suite
- statistical claims about general model quality
- a custom agent runtime
- a subagent scheduler
- persistent memory
- an approval engine
- a dashboard

Add machinery only after the first runs identify a measurement problem that requires it.
