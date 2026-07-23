# Standard MCP Stack

A practical reference architecture for understanding, designing, and implementing Model Context Protocol systems.

This repository separates the MCP ecosystem into four clear roles:

1. **Host** — the application that contains and governs MCP clients.
2. **Client** — the protocol component that connects the host to one MCP server.
3. **Server** — the provider that exposes tools, resources, and prompts.
4. **Underlying systems** — APIs, databases, local files, command-line programs, and services used by the server.

## Core flow

```text
User / External System
        |
        v
Interface (CLI, GUI, Voice, API)
        |
        v
Host Application — for example, Nephew
        |
        v
Director -> Manager -> Worker
        |
        v
MCP Client === MCP Protocol === MCP Server
                                      |
                                      v
                        API / Database / Files / Tools
```

## Repository map

- `docs/architecture.md` — complete system architecture
- `docs/host.md` — the application containing MCP clients
- `docs/client.md` — MCP client anatomy
- `docs/server.md` — MCP server anatomy
- `docs/request-lifecycle.md` — end-to-end request flow
- `docs/trust-analogy.md` — trust and company mental model
- `docs/security.md` — identity, authentication, authorization, and secrets
- `matrices/master-matrix.md` — large side-by-side mapping
- `examples/` — starter implementation patterns
- `schemas/` — configuration examples

## Governing principles

- Identity and governance live outside any individual model.
- Models are replaceable brains, not the entire application.
- Directors plan, managers coordinate, and workers execute.
- Workers request access to protected assets through management.
- MCP is a protocol, not an API, database, model, or credential system.
- A host may contain multiple MCP clients.
- Each MCP client maintains a connection to one MCP server.
- One host can therefore connect to many servers.
- Servers may run locally, inside a private network, or remotely.
- Servers may wrap APIs, but they can also expose local files, databases, scripts, and applications.

## Status

Foundation phase. The repository currently defines the conceptual architecture and implementation blueprint for the Standard MCP Stack.
