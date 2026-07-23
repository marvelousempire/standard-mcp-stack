# Standard MCP Stack Manual

## Reading paths

### Learn the mental model

1. [Trust Architecture](trust-analogy.md)
2. [Business Operating Model](business-analogy.md)
3. [Architecture Layers](architecture-layers.md)
4. [Rosetta Stone Matrix](../matrices/rosetta-stone.md)
5. [Glossary](glossary.md)

### Design a governed AI application

1. [Architecture Principles](architecture-principles.md)
2. [Governance Bylaws](governance-bylaws.md)
3. [Architecture](architecture.md)
4. [Request Lifecycle](request-lifecycle.md)
5. [Security](security.md)

### Understand MCP itself

1. [Host](host.md)
2. [Client](client.md)
3. [Server](server.md)
4. [Capabilities](capabilities.md)
5. [Stack Structure](../mcp/stack-structure.md)
6. [Master Matrix](../matrices/master-matrix.md)

### Implement Nephew

1. [Phase 2 Stack](../PHASE-2.md)
2. [Planning](../directors/planning.md)
3. [Orchestration](../managers/orchestration.md)
4. [Worker Execution](../workers/execution.md)
5. [Model Selection](../brains/model-selection.md)
6. [Memory Model](../memory/memory-model.md)
7. [Tool Standard](../tools/tool-standard.md)
8. [Skill Standard](../skills/skill-standard.md)
9. [Authority Model](../security/authority-model.md)
10. [Python Host Skeleton](../examples/python-host-skeleton/README.md)

## Canonical documents

| Question | Canonical source |
|---|---|
| What is the central mental model? | `docs/trust-analogy.md` |
| How does the business parallel work? | `docs/business-analogy.md` |
| Where does a component belong? | `docs/architecture-layers.md` |
| What does a term mean? | `docs/glossary.md` |
| What principles cannot be violated? | `docs/architecture-principles.md` |
| How should documents be structured? | `docs/document-standard.md` |
| How do all vocabularies translate? | `matrices/rosetta-stone.md` |
| How does a request move? | `docs/request-lifecycle.md` |
| What controls permission? | `security/authority-model.md` |
| How do MCP roles differ? | `matrices/master-matrix.md` |

## Repository domains

### Governance

Identity, mission, bylaws, authority, delegation, permissions, audit, and amendment.

### Operations

Reception, host, directors, managers, workers, assets, MCP communications, providers, and evidence.

### Shared assets

Brains, memory, knowledge, tools, skills, credentials, configuration, and records.

### Assurance

Security, observability, testing, error containment, evidence, and conformance.

## Contribution rule

New documents should extend the canonical model rather than create a competing vocabulary. Add a term to the glossary and Rosetta Stone when introducing a genuinely new concept.
