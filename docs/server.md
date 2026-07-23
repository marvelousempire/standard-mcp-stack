# MCP Server Anatomy

## Definition

An MCP server is a capability provider. It implements the MCP protocol, advertises one or more capabilities, validates requests, invokes local or remote implementation logic, and returns standardized results.

A server is not merely a storage box. It is an active software service with a protocol-facing side and an implementation-facing side.

## Required building blocks

### 1. Server identity
- server name
- version
- implementation metadata

### 2. Transport listener
- starts a local standard-input/output session, or
- listens through a supported HTTP-based transport

### 3. Protocol engine
- parses JSON-RPC messages
- validates method names and parameters
- negotiates protocol versions and capabilities
- generates results, errors, and notifications

### 4. Capability registries

#### Tools
Executable operations such as:
- create an issue
- query a database
- run a build
- transform a file

#### Resources
Readable context such as:
- a repository file
- a document
- a database record
- a log stream

#### Prompts
Reusable prompt templates exposed by the server.

### 5. Request router
Maps incoming MCP methods and capability names to the correct handler.

### 6. Authentication
Confirms who or what is connecting when authentication is required.

Possible mechanisms depend on transport and deployment:
- local-process trust boundary
- bearer tokens
- OAuth
- mTLS
- reverse-proxy identity
- private-network identity

### 7. Authorization
Checks what the authenticated caller is allowed to do:
- allowed tool names
- read/write scope
- tenant or repository boundaries
- filesystem roots
- row-level or resource-level access
- approval requirements

### 8. Input validation
- required fields
- types and schemas
- size limits
- path validation
- command allowlists
- injection protection

### 9. Business logic
The actual implementation of the capability. It may be Python, TypeScript, Go, Rust, shell wrappers, or another language.

### 10. Provider adapters
The server may use:
- REST or GraphQL APIs
- vendor SDKs
- SQL drivers
- local filesystems
- Git
- Docker
- command-line programs
- hardware devices

### 11. Response builder
Returns protocol-valid structured content, errors, progress, and metadata.

### 12. Reliability and operations
- timeout enforcement
- cancellation
- concurrency controls
- rate limiting
- caching
- idempotency
- graceful shutdown

### 13. Observability
- structured logs
- metrics
- traces
- security audit events
- redaction of secrets and sensitive data

## Server configuration model

| Field | Example | Meaning |
|---|---|---|
| `server.name` | `nas-files` | Server identity |
| `server.version` | `0.1.0` | Implementation version |
| `transport.type` | `stdio` or `http` | Listener mechanism |
| `transport.bind` | `127.0.0.1` | Network binding when applicable |
| `auth.mode` | `oauth` | Authentication mechanism |
| `capabilities.tools` | `[search_files]` | Exposed executable operations |
| `capabilities.resources` | `[nas://docs]` | Exposed readable context |
| `policy.allowed_roots` | `[/data/docs]` | Filesystem boundary |
| `policy.read_only` | `true` | Effect boundary |
| `limits.max_concurrency` | `8` | Parallel work limit |
| `limits.timeout_seconds` | `30` | Execution deadline |
| `provider.base_url` | `https://api...` | Underlying service address |
| `provider.secret_ref` | `vault://...` | Secret reference |

## Server placement

A server can run:
- as a child process on the same Mac as the host
- in a container
- on the DGX system
- on the NAS or another private-network machine
- in a remote cloud environment
- alongside the provider it wraps

Placement is an operational decision, not part of the definition of MCP.

## Server-to-provider chain

```text
MCP Client
    |
    | MCP request
    v
MCP Server
    |
    | implementation-specific call
    v
API / SDK / SQL / Filesystem / CLI / Local Function
```

The MCP server can wrap an API, but it does not have to. It may directly implement the requested capability.
