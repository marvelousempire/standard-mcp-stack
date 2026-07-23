# Architecture Overview

## 1. The complete stack

```text
[Requesters]
Beneficiary | Authorized third party | External application
                         |
                         v
[Interfaces]
CLI | Web GUI | Voice | Mobile | Public API
                         |
                         v
[Reception]
main.py / HTTP controller / event handler
                         |
                         v
[Governance-aware company]
Directors -> Managers -> Workers
     |           |          |
     |           |          +--- execute scoped tasks
     |           +-------------- route, authorize, allocate assets
     +-------------------------- interpret mission and produce plans
                         |
                         v
[Shared company assets]
Identity | Bylaws | Rules | Skills | Prompts | Config | Brains
Memory | Knowledge | Tools | Credentials | Audit Logs
                         |
                         v
[Communication and integration]
MCP Host -> MCP Client(s) === MCP === MCP Server(s)
                                         |
                                         v
[Provider systems]
REST/GraphQL APIs | SQL | files | Git | Docker | SaaS | local programs
```

## 2. Host, client, and server

### Host
The host is the application the user experiences. Nephew would be the host. It owns identity, governance, conversation state, approvals, model selection, client creation, and the final response.

### Client
An MCP client is a protocol component created or managed by the host. A client maintains a logical connection to one server. A host may operate many clients at once—one per connected server.

### Server
An MCP server publishes capabilities in a standard format. Its capabilities can include tools, resources, and prompts. The server receives MCP messages, enforces access rules, invokes its implementation, and returns results.

### Provider system
The provider system is what actually holds data or performs work. It may be GitHub, PostgreSQL, a filesystem, Docker, WordPress, a local Python function, or a vendor API.

## 3. Nephew company model

### Reception
Receives input, validates its basic shape, creates a request ID, and forwards the request. Reception does not make strategic decisions.

### Directors
Read the request alongside identity, bylaws, rules, and available capabilities. They define the objective, constraints, approval requirements, and plan.

### Managers
Translate the plan into work orders. They choose workers, grant temporary access, select brains and tools, enforce budgets and permissions, and collect results.

### Workers
Perform narrowly scoped tasks. A worker may reason with a model, retrieve memory, call a tool, or request an MCP capability. Workers do not own shared credentials or unrestricted assets.

## 4. Shared assets

- **Identity:** name, mission, tone, values, ownership, allowed representation.
- **Bylaws:** non-negotiable operating rules and governance constraints.
- **Rules:** task-level policies and safety boundaries.
- **Skills:** reusable procedures for completing categories of work.
- **Prompts:** instructions supplied to models for specific roles.
- **Configuration:** endpoints, feature flags, model choices, limits, and environment settings.
- **Brains:** local or remote models used for reasoning, coding, vision, speech, or classification.
- **Memory:** conversations, structured records, vector indexes, notes, and learned preferences.
- **Knowledge:** documents and source material treated as evidence.
- **Tools:** deterministic programs capable of reading or changing systems.
- **Credentials:** secrets and identity proofs stored separately from code and prompts.
- **Audit logs:** records of requests, approvals, calls, results, and errors.

## 5. Two API positions

### Inbound API
An external application can call Nephew through a public or private API. This is an interface into the host and is separate from MCP.

### Provider API
An MCP server may call an underlying provider API to fulfill an MCP request. For example, a GitHub MCP server may translate an MCP tool call into GitHub REST or GraphQL API calls.

MCP does not eliminate APIs. It standardizes how AI hosts discover and invoke capabilities.

## 6. Placement rules

- MCP clients normally live inside the host process or beside it as a managed component.
- MCP servers can be local child processes, private network services, or remote services.
- Credentials may be managed by the host, client configuration, server, or an external secret manager depending on the transport and authentication design.
- The model should not be given raw secrets.
- Authorization should be checked before execution, not merely described in prompts.
