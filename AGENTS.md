# Repository instructions

Dear Dark Phrolova is an experiment in persona-driven behavior steering for coding agents.

When working in this repository:

- Keep the project lightweight. Do not introduce a workflow runtime, agent scheduler, state machine, approval engine, or plugin framework unless an experiment proves one is necessary.
- Prefer editing the persona, behavior contract, skill wrapper, or eval cases over adding code.
- Keep persona definition separate from host-specific integration.
- Keep evaluation separate from runtime behavior.
- Favor the smallest change that can test the current hypothesis.
- Get the main experimental path working before adding defensive infrastructure, abstractions, or broad test scaffolding.
- User instructions take precedence over repository guidance.

The repository should remain usable as a small behavior package that other orchestration systems can call into.
