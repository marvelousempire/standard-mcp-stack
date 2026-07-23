# Worker Execution Standard

Workers perform narrowly scoped tasks under a manager-issued work order.

## Trust lens

Workers are contracted specialists: accountants, builders, researchers, technicians, or counsel retained for a defined purpose.

## Business lens

Workers are employees, stations, or service teams assigned a ticket by management.

## Worker contract

Every worker must receive:

- a work-order ID
- a defined objective
- allowed inputs
- allowed tools and assets
- forbidden actions
- time, cost, and token limits
- acceptance criteria
- reporting requirements

## Worker behavior

1. Validate the work order.
2. Request missing assets through management.
3. Execute only authorized steps.
4. Preserve evidence.
5. Report status and exceptions.
6. Return results and relinquish temporary access.

## Result package

```yaml
work_order_id: work-001
status: completed
outputs:
  - repository_summary.md
evidence:
  - source_uri: github://owner/repo/README.md
checks:
  - name: required_sections_present
    passed: true
exceptions: []
```

Workers may reason, call a model, run code, or invoke an MCP tool, but they remain bounded by the work order.