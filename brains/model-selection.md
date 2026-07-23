# Brain and Model Selection Standard

Brains are replaceable reasoning components used by the host, directors, managers, or workers. A brain is not the whole system.

## Trust lens

A brain is an adviser retained for expertise. The trust remains the same when advisers change.

## Business lens

A brain is an analyst, engineer, designer, or specialist consultant selected for a particular assignment.

## Selection dimensions

- supported input types: text, image, audio, video
- reasoning quality
- coding ability
- tool-use reliability
- context length
- latency
- memory footprint
- licensing
- privacy and deployment location
- cost
- structured-output reliability

## Selection rule

Choose the smallest capable model that satisfies the work order and governance requirements.

## Registry example

```yaml
models:
  planner:
    provider: local
    model: qwen-planner
    inputs: [text]
    allowed_roles: [director]
  coder:
    provider: local
    model: coding-model
    inputs: [text]
    allowed_roles: [worker]
  vision:
    provider: remote
    model: vision-model
    inputs: [text, image]
    allowed_roles: [worker]
```

## Boundary

Models may advise, generate, classify, or plan. Authority comes from governance and delegated work orders, not from the model itself.