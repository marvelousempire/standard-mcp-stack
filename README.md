# Standard MCP Stack

A practical reference architecture for understanding, designing, governing, and implementing Model Context Protocol systems.

This repository uses two parallel teaching models:

1. **Trust architecture** — authority, governance, custody, delegation, records, and controlled access.
2. **Business operations** — reception, directors, managers, workers, shared assets, communications, vendors, and audit.

Those analogies remain tied to the actual MCP host-client-server architecture rather than replacing it.

## Technical roles

1. **Host** — the application that owns the user experience, governance, model integration, consent, and MCP client lifecycle.
2. **Client** — a host-managed protocol component maintaining one logical session with one MCP server.
3. **Server** — a local or remote provider exposing tools, resources, prompts, and other negotiated capabilities.
4. **Underlying systems** — APIs, databases, files, command-line programs, devices, and services used by server implementations.

## Core flow

```text
AUTHORIZED REQUESTER
        │
        ▼
INTERFACE / PUBLIC API
        │
        ▼
RECEPTION — intake and routing
        │
        ▼
DIRECTORS — plan under governance
        │
        ▼
MANAGERS — issue work orders and control access
        │
        ▼
WORKERS — execute bounded tasks
        │
        ├── brains
        ├── memory
        ├── knowledge
        ├── tools
        └── skills
                  │
                  ▼
             MCP HOST
                  │
       isolated MCP client instance
                  │
             MCP protocol
                  │
                  ▼
             MCP SERVER
                  │
       tool / resource / prompt
                  │
       optional API / DB / CLI / files
                  │
                  ▼
        RESULT / RECEIPT / EVIDENCE
                  │
                  ▼
WORKER → MANAGER → DIRECTOR → RECEPTION → REQUESTER
```

## Start here

- `docs/trust-analogy.md` — primary mental model and full trust workflow
- `docs/business-analogy.md` — company, restaurant, studio, and software-company parallels
- `matrices/trust-business-code-crosswalk.md` — central translation table across analogy, MCP, and code
- `docs/architecture.md` — complete system architecture
- `docs/glossary.md` — precise vocabulary
- `docs/capabilities.md` — initialization and capability negotiation
- `docs/client.md` — MCP client anatomy
- `docs/server.md` — MCP server anatomy
- `docs/request-lifecycle.md` — end-to-end request flow
- `docs/security.md` — identity, authentication, authorization, approvals, and secrets
- `matrices/master-matrix.md` — client/server/host component matrix
- `schemas/host-config.example.yaml` — multi-server host configuration model
- `examples/` — starter implementation patterns
- `ROADMAP.md` — path from reference architecture to working Nephew stack

## Governing principles

- Identity and governance live outside any individual model.
- Models are replaceable brains, not the entire application.
- Directors plan, managers coordinate and control access, and workers execute.
- Workers receive task-scoped access rather than owning credentials or shared assets.
- The host owns the conversation, consent, cross-server coordination, and context boundaries.
- MCP is a protocol, not an API, database, language model, credential, or network tunnel.
- A host may create multiple MCP client instances.
- Each client maintains one logical session with a particular server.
- Servers may be local, internal, or remote.
- Servers may wrap APIs, but may also expose files, databases, scripts, devices, or original business logic directly.
- Advertised capability and granted authorization are separate decisions.
- Every meaningful action should leave a reconstructable audit trail.

## Status

Foundation and reference-manual phase. The repository now defines the conceptual architecture, trust and business teaching models, security boundaries, capability model, configuration patterns, and initial implementation blueprint for the Standard MCP Stack.
