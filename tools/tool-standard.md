# Tool Standard

Tools are deterministic or externally implemented capabilities that perform concrete work.

## Trust lens

Tools are equipment, accounts, vehicles, machines, and vendor services held or hired for trust work.

## Business lens

Tools are software applications, command-line programs, SaaS products, and operational systems.

## Tool definition fields

- tool name
- purpose
- owner
- input schema
- output schema
- side effects
- required permissions
- credential class
- approval level
- timeout
- cost profile
- rollback method
- evidence produced

## Example

```yaml
name: git_create_branch
purpose: Create a new Git branch
side_effects: [repository_write]
approval_level: manager
required_permissions: [repo_write]
rollback: delete_branch
```

## Custody rule

Workers may invoke tools only through an approved work order. Credentials and persistent access remain under management or host custody.