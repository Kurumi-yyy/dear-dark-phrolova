# Dear Dark Phrolova

A small experiment in persona-driven behavior steering for coding agents.

The core question is simple: **can a coherent personality improve an agent's engineering judgment before we add a large explicit ruleset?**

Dear Dark Phrolova targets several recurring coding-agent failure modes:

- agreeing too easily with a flawed user framing;
- premature abstractions and framework-building;
- defensive machinery before the main path works;
- low-value clarification pauses;
- verification effort disproportionate to the change;
- rebuilding capabilities already supplied by the host agent.

The project deliberately stays lightweight. It is a behavior package, not an agent runtime or workflow engine.

## Repository structure

```text
.
├── AGENTS.md                 # guardrails for developing this repository
├── persona/
│   ├── CORE.md               # distilled personality source
│   └── BEHAVIOR.md           # observable engineering behavior derived from it
├── skill/
│   └── SKILL.md              # thin host-facing wrapper
├── evals/
│   ├── RUBRIC.md             # scoring dimensions
│   └── CASES.md              # small diagnostic behavior cases
└── docs/
    ├── ARCHITECTURE.md       # package boundaries and DDP relationship
    └── EXPERIMENT_PLAN.md    # baseline vs persona vs persona+behavior experiment
```

## Experiment

Initial comparisons use three conditions:

1. **Baseline** — host/model defaults.
2. **Persona** — `persona/CORE.md` only.
3. **Persona + behavior** — persona plus `persona/BEHAVIOR.md` through the skill wrapper.

This lets us test whether the persona itself causes useful correction instead of attributing every improvement to explicit instructions.

## Relationship to DDP

Dear Dark Phrolova is intended to be one reusable behavior/persona module in the broader **DDP** direction.

The larger workflow — retrieval -> HITL -> planning -> execution -> independent audit -> pass/rework — is intentionally kept outside this repository. A separate orchestrator can call DDP modules without coupling persona experiments to one harness design.

## Design principle

Get the main experimental path working first. Add architecture only when an observed requirement earns it.
