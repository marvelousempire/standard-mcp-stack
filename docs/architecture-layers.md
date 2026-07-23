# Architecture Layers

## Purpose

The Standard MCP Stack uses numbered layers so every component has a visible place in the system.

| Layer | Name | Trust model | Business model | Main responsibility |
|---:|---|---|---|---|
| 0 | Governance | Trust instrument, bylaws, authority schedule | Charter, policy, brand, operating rules | Define identity, purpose, limits, and delegation rules |
| 1 | Interfaces | Petition, letter, authorized inquiry channel | Website, phone, CLI, GUI, public API | Receive and present requests and responses |
| 2 | Reception and Host | Trust office intake | Front desk and application shell | Validate intake, maintain sessions, own consent and context |
| 3 | Directors | Board or directing trustees | Executive leadership | Interpret governance and produce plans |
| 4 | Managers | Managing trustees | Operations management | Issue work orders, assign workers, control resources and approvals |
| 5 | Workers | Contractors and specialists | Employees, contractors, stations | Execute bounded tasks and return evidence |
| 6 | Shared Assets | Trust property and records | Company resources and departments | Supply brains, memory, knowledge, tools, skills, and credentials |
| 7 | MCP Communications | Authorized correspondence system | Integration and communications department | Connect host-managed clients to capability providers |
| 8 | Service Providers | Vendor desks or internal service offices | GitHub, Docker, WordPress, databases, local services | Expose tools, resources, prompts, and provider logic |
| 9 | Underlying Systems | Vendor inventory, machinery, archives | APIs, files, databases, CLIs, devices | Perform the actual operation or supply the underlying information |
| 10 | Evidence and Audit | Ledger, receipts, minutes, certificates | Logs, tickets, approvals, reports | Preserve reconstructable proof of the transaction |

## Downward flow

```text
Authority
  ↓
Governance → Directors → Managers → Workers → Controlled Capability
```

## Upward flow

```text
Evidence
  ↑
Requester ← Reception ← Directors ← Managers ← Workers ← Result/Receipt
```

## Cross-cutting concerns

Security, identity, observability, configuration, testing, and error handling cross every layer. They are not isolated destinations that can be postponed until the end.

## Layer rules

- A layer may call the layer immediately below it or a declared shared service.
- Lower layers must not silently invent policy for higher layers.
- External providers do not become directors or managers merely because they expose powerful tools.
- Governance is consulted, not rewritten, during ordinary request handling.
- Evidence should identify which layers participated in an action.

## Example

A request to update a GitHub repository moves through:

1. Interface receives the mission.
2. Host establishes identity, session, and consent.
3. Director creates a plan under governance.
4. Manager creates a work order and selects a Git worker.
5. Worker requests the GitHub capability.
6. Host uses its GitHub MCP client session.
7. GitHub MCP server exposes the relevant tool.
8. The server calls GitHub or local Git operations.
9. The result and receipts return up the chain.

## Common misconception

The layers are responsibilities, not necessarily separate computers or processes. A small implementation may place several layers in one Python application while preserving their boundaries in code.
