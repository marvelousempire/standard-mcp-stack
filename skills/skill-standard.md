# Skill Standard

Skills are reusable operating procedures that teach the system how to approach a recurring class of work.

## Trust lens

A skill is an approved method or professional procedure adopted for trust administration.

## Business lens

A skill is a playbook, SOP, recipe, checklist, or runbook.

## Skill fields

- name
- purpose
- triggering conditions
- required role
- permitted tools
- required knowledge
- required approvals
- execution steps
- validation steps
- failure handling
- outputs
- version

## Boundary

A skill does not create authority. It may only be used within the authority granted by governance and the active work order.

## Example

```yaml
name: summarize_repository
role: github_reader
permitted_tools: [repo_metadata, read_file]
steps:
  - inspect repository metadata
  - identify major files
  - read README and architecture documents
  - produce cited summary
validation:
  - all claims trace to retrieved evidence
```