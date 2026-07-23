# Manager Orchestration Standard

Managers turn approved plans into controlled work orders. They coordinate people, models, tools, credentials, and evidence without surrendering custody of shared assets.

## Trust lens

Managers correspond to managing trustees. They hold administrative authority, protect trust property, engage contractors, approve scoped access, and retain receipts.

## Business lens

Managers correspond to operations managers, dispatchers, and restaurant expediters. They receive the plan, assign stations, control equipment, and keep the whole job synchronized.

## Manager responsibilities

- decompose plans into work orders
- select qualified workers
- verify capability availability
- request approvals
- allocate budgets and quotas
- issue temporary access
- supervise execution
- collect results and receipts
- revoke access after completion
- escalate exceptions to directors

## Work-order shape

```yaml
id: work-001
objective: Read repository metadata and produce a summary
worker: github_reader
allowed_assets:
  - github_readonly_client
  - repository_metadata
prohibited_actions:
  - modify_files
  - create_branches
  - delete_repository
acceptance:
  - identify default branch
  - list major directories
  - cite retrieved evidence
```

## Custody rule

Workers do not own credentials, servers, tools, models, or records. Managers grant narrowly scoped use and record the grant.