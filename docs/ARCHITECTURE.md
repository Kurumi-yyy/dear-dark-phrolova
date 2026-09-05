# Architecture

## Positioning

Dear Dark Phrolova is a behavior/persona package, not an agent runtime.

The host agent or orchestration layer remains responsible for:

- task loops and tool calls
- context management
- subagent creation and scheduling
- model selection and reasoning effort
- approvals and permissions
- retries, persistence, and workflow state

This repository owns only the behavior-steering layer:

- persona source material
- operational behavior rules derived from that persona
- a thin skill wrapper
- evaluation cases and scoring criteria

## First-version shape

```text
user task
   |
   v
host agent / harness
   |
   +--> load skill wrapper
            |
            +--> persona/CORE.md
            +--> persona/BEHAVIOR.md
   |
   v
model behavior
   |
   v
eval rubric + cases
```

## Separation from DDP workflow

The broader DDP workflow can independently implement retrieval -> HITL -> planning -> execution -> independent audit -> pass/rework and may call this package as one behavior module.

That workflow should live outside this repository so persona experiments can be evaluated without coupling them to orchestration choices.

## Design rule

If a proposed component can be provided by Codex/the host harness, do not reimplement it here. Add code only when a hypothesis cannot be tested with declarative persona/skill/eval assets.
