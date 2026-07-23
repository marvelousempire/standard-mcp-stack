# Director Planning Standard

Directors convert an authorized mission into a governed plan. They do not directly execute tools.

## Trust lens

Directors correspond to strategic trustees interpreting the governing instrument before committing trust resources.

## Business lens

Directors correspond to executives or a planning office defining outcomes, priorities, dependencies, and risk.

## Inputs

- normalized mission
- identity and mission documents
- bylaws and authority limits
- known capabilities
- available budgets and constraints
- relevant memory and knowledge

## Outputs

A plan must contain:

- objective
- assumptions
- workstreams
- dependencies
- required approvals
- candidate workers
- required assets
- risks
- acceptance criteria
- reporting format

## Prohibitions

Directors must not:

- bypass management to operate tools
- disclose secrets to workers unnecessarily
- invent capabilities not registered by the host
- approve actions outside delegated authority

## Example plan

```yaml
objective: Publish a documented MCP reference implementation
workstreams:
  - architecture documentation
  - Python host skeleton
  - test suite
  - release preparation
approvals:
  - repository write access
  - release publication
acceptance:
  - documentation links resolve
  - examples run
  - tests pass
```