# MCP Client Anatomy

## Definition

An MCP client is the protocol component inside an MCP host that maintains a logical connection to one MCP server. The host may create many client instances from the same client library.

## Required building blocks

### 1. Client identity
- application name
- application version
- optional build/environment information

### 2. Server definition
- human-readable server name
- transport type
- local command and arguments, or remote URL
- environment variable references
- enable/disable state

### 3. Transport adapter
Carries protocol messages. Typical choices include a local standard-input/output connection or an HTTP-based transport.

### 4. Protocol engine
- serializes and parses JSON-RPC messages
- assigns and correlates request IDs
- handles requests, responses, errors, and notifications
- negotiates protocol versions and capabilities

### 5. Initialization and discovery
- initializes the connection
- advertises client capabilities
- records server capabilities
- lists tools, resources, and prompts
- handles capability-list changes where supported

### 6. Authentication and credentials
Credentials are not the MCP client itself. They are inputs used by the client or transport when a server requires authentication.

Possible inputs:
- OAuth access token
- API token
- HTTP headers
- local environment variable references
- operating-system keychain references
- secret-manager references

Raw secrets should not be inserted into model prompts or committed to configuration files.

### 7. Capability adapters
- tool-call adapter
- resource-read adapter
- prompt retrieval adapter
- optional sampling handler
- optional roots handler

### 8. Lifecycle manager
- connect
- initialize
- monitor
- reconnect when safe
- cancel requests
- close cleanly

### 9. Reliability controls
- timeouts
- retries with backoff
- idempotency awareness
- concurrency limits
- error classification

### 10. Governance hooks
- permission checks
- user consent
- approval gates
- spending and token limits
- allowed server/capability lists

### 11. Observability
- structured logs
- metrics
- traces
- audit records
- redaction

## Client configuration model

| Field | Example | Meaning |
|---|---|---|
| `id` | `github-primary` | Stable local identifier |
| `display_name` | `GitHub` | Human-readable label |
| `enabled` | `true` | Whether the host may connect |
| `transport` | `stdio` or `http` | Connection mechanism |
| `command` | `python` | Local server executable |
| `args` | `[-m, server]` | Local server arguments |
| `url` | `https://...` | Remote server address |
| `headers_from_env` | `GITHUB_TOKEN` | Secret reference, not secret value |
| `connect_timeout_seconds` | `10` | Connection deadline |
| `request_timeout_seconds` | `60` | Call deadline |
| `allowed_tools` | `[repo_read]` | Capability allowlist |
| `approval_required_for` | `[repo_write]` | Human approval policy |
| `max_concurrency` | `4` | Parallel request limit |

## What prevents a client from reaching a server?

- no compatible client library
- wrong or unsupported transport
- incorrect command, URL, hostname, or port
- network/firewall failure
- server not running
- protocol-version incompatibility
- missing or expired credentials
- insufficient authorization scope
- server capability not advertised
- governance policy denies the action
- malformed arguments
- timeout, quota, or rate limit

## Host-to-many-server pattern

```text
Nephew Host
  ├── Client instance: GitHub server
  ├── Client instance: Docker server
  ├── Client instance: WordPress server
  └── Client instance: Local NAS server
```

The host presents one identity to the user while managing multiple independent server connections.
