# Capability Model

MCP connections begin with explicit negotiation. The client and server identify themselves, agree on a protocol version, and declare optional capabilities.

## Why capability negotiation exists

Without negotiation, a client might call a feature that the server does not implement, or a server might ask the client for behavior the host has not approved. Negotiation creates a session contract.

## Initialization flow

1. The host creates a client for a configured server.
2. The client opens the configured transport.
3. The client sends `initialize` with its protocol version, client information, and supported capabilities.
4. The server responds with the negotiated version, server information, instructions, and server capabilities.
5. The client rejects incompatible protocol versions.
6. The client sends `notifications/initialized`.
7. Normal operation begins.

## Client capability families

| Capability | Meaning | Nephew interpretation |
|---|---|---|
| roots | Client can expose bounded filesystem roots | Management grants a contractor access to approved work areas |
| sampling | Server can request model generation through the host | Vendor asks the trust's approved brain to help complete work |
| elicitation | Server can request structured user input | Contractor sends a clarification form back through reception |
| tasks | Client can participate in task-oriented long-running operations when supported | Management can track an operation as a managed work order |
| experimental | Client supports named non-standard extensions | A controlled pilot program |

## Server capability families

| Capability | Meaning | Nephew interpretation |
|---|---|---|
| tools | Server exposes callable operations | Vendor service catalog |
| resources | Server exposes readable context | Vendor records, documents, inventory, or reference materials |
| prompts | Server exposes reusable prompt templates | Approved forms or playbooks |
| logging | Server can emit structured log messages | Vendor status reports |
| completions | Server supports argument completion | Assistance filling out an order form |
| tasks | Server supports task-augmented operations when negotiated | Vendor can issue trackable work orders |
| experimental | Server supports named non-standard extensions | Vendor pilot feature |

## Capability registry

The host should store a normalized record for each active connection:

```yaml
server_id: github
protocol_version: negotiated-version
server_info:
  name: github-mcp
  version: 1.0.0
capabilities:
  tools:
    list_changed: true
  resources: null
  prompts: null
connection_state: ready
last_initialized_at: timestamp
```

## Rules

- Never call a capability that was not negotiated.
- Treat capability discovery as session-specific, not permanent truth.
- Rebuild the registry after reconnecting.
- Keep experimental capabilities disabled unless explicitly approved.
- Separate capability availability from authorization. A tool may exist but still be denied by policy.
