# Standard MCP Stack

A governed reference architecture for understanding, designing, and implementing Model Context Protocol systems and AI applications such as **Nephew**.

The repository uses two parallel teaching models:

1. **Trust architecture** — authority, governance, custody, delegation, records, and controlled access.
2. **Business operations** — reception, directors, managers, workers, shared assets, communications, vendors, and audit.

Those analogies are not decorative. They are the organizing system for the technical architecture.

## The lasting mental model

```text
AUTHORIZED REQUESTER
        │
        ▼
INTERFACE
        │
        ▼
RECEPTION / HOST
        │
        ▼
DIRECTORS ───── consult governance, identity, bylaws, and mission
        │
        ▼
MANAGERS ───── issue work orders, approve access, control shared assets
        │
        ▼
WORKERS ────── execute bounded tasks
        │
        ├── brains
        ├── memory
        ├── knowledge
        ├── tools
        ├── skills
        └── credentials
                 │
                 ▼
         MCP CLIENT SESSION
                 │
            MCP PROTOCOL
                 │
                 ▼
             MCP SERVER
                 │
       tool / resource / prompt
                 │
      API / database / file / CLI
                 │
                 ▼
       RESULT / RECEIPT / EVIDENCE
                 │
                 ▼
WORKER → MANAGER → DIRECTOR → RECEPTION → REQUESTER
```

**Authority flows downward. Evidence flows upward.**

## Start here

- [`docs/manual-index.md`](docs/manual-index.md) — guided reading paths and canonical sources
- [`docs/trust-analogy.md`](docs/trust-analogy.md) — primary mental model
- [`docs/business-analogy.md`](docs/business-analogy.md) — parallel operating-company model
- [`matrices/rosetta-stone.md`](matrices/rosetta-stone.md) — translation hub across trust, business, code, MCP, AI, and security
- [`docs/architecture-principles.md`](docs/architecture-principles.md) — non-negotiable system principles
- [`docs/architecture-layers.md`](docs/architecture-layers.md) — numbered architecture layers
- [`docs/glossary.md`](docs/glossary.md) — canonical vocabulary

## Visual maps

- [`diagrams/trust-architecture.md`](diagrams/trust-architecture.md)
- [`diagrams/business-operations.md`](diagrams/business-operations.md)
- [`diagrams/mcp-communication.md`](diagrams/mcp-communication.md)

## Governance and operations

### Governance domain

Defines identity, mission, authority, delegation, permissions, custody, disclosure, audit, and amendment.

### Operations domain

Receives missions, creates plans, issues work orders, executes tasks, uses controlled assets, communicates with providers, and returns evidence.

### Shared assets

Brains, memory, knowledge, tools, skills, credentials, configuration, and records are controlled services. Workers receive task-scoped access; they do not own these assets.

## Technical MCP roles

1. **Host** — owns the user relationship, consent, governance enforcement, models, context boundaries, sessions, and MCP client lifecycle.
2. **Client** — a host-managed protocol component maintaining one logical session with one MCP server.
3. **Server** — a local or remote provider exposing negotiated tools, resources, prompts, or other capabilities.
4. **Underlying system** — an API, database, file system, command-line program, device, or service used by the server.

One host can manage many isolated client sessions:

```text
Nephew Host
├── GitHub MCP client session ─── GitHub MCP server
├── WordPress MCP client session ─ WordPress MCP server
├── Docker MCP client session ─── Docker MCP server
└── Files MCP client session ──── Local files MCP server
```

## Repository map

| Domain | Primary locations |
|---|---|
| Manual and mental models | `docs/`, `diagrams/`, `matrices/` |
| Governance | `governance/`, `security/` |
| Planning and operations | `directors/`, `managers/`, `workers/` |
| Shared assets | `brains/`, `memory/`, `knowledge/`, `tools/`, `skills/` |
| MCP communication | `mcp/`, `docs/client.md`, `docs/server.md`, `docs/host.md` |
| Schemas and examples | `schemas/`, `examples/` |
| Roadmap | `ROADMAP.md`, `PHASE-2.md` |

## Non-negotiable principles

- Identity and governance live outside any individual model.
- Models are replaceable brains, not the entire application.
- Directors plan, managers coordinate and control access, and workers execute.
- Workers never silently bypass management.
- Models may recommend; software must enforce.
- Credentials are controlled, scoped, revocable assets.
- Capability discovery is not permission.
- MCP is a protocol, not an API, model, credential system, or network tunnel.
- Each MCP client session maintains a clear server boundary.
- Every meaningful external action leaves reconstructable evidence.

## Documentation standard

New and revised chapters should follow [`docs/document-standard.md`](docs/document-standard.md), including purpose, responsibilities, authority, inputs, outputs, trust and business analogies, Python implementation, security, misconceptions, and review questions.

## Status

The repository is in the **reference-manual and implementation-blueprint phase**. It now defines a unified vocabulary, trust and business architecture, numbered layers, authority model, MCP boundaries, shared-asset model, diagrams, schemas, and the initial route toward a working Nephew host.
