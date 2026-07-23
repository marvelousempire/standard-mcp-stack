# Roadmap

## Phase 1 — Conceptual standard

- [x] Define host, client, server, and provider-system boundaries
- [x] Define trust/company analogy
- [x] Create master client/server matrix
- [x] Document request lifecycle
- [x] Document security model
- [x] Add host configuration example
- [x] Add Python host skeleton

## Phase 2 — Formal specifications

- [ ] Add glossary with canonical terms
- [ ] Add architecture decision records
- [ ] Add JSON Schemas for host and server configuration
- [ ] Add capability naming conventions
- [ ] Add standardized error taxonomy
- [ ] Add audit-event schema
- [ ] Add approval-event schema
- [ ] Add worker work-order schema

## Phase 3 — Reference implementation

- [ ] Select official Python MCP SDK/runtime
- [ ] Build minimal host with one local server
- [ ] Add client registry and connection pool
- [ ] Add tool discovery and invocation
- [ ] Add resources and prompts
- [ ] Add structured logging
- [ ] Add allowlist-based policy enforcement
- [ ] Add human approval gate
- [ ] Add mock server and contract tests

## Phase 4 — Nephew integration

- [ ] Create governance directory
- [ ] Implement reception (`main.py`)
- [ ] Implement director planner
- [ ] Implement manager dispatcher
- [ ] Implement initial workers
- [ ] Add brain router for Mac and DGX inference
- [ ] Add NAS knowledge and model storage adapters
- [ ] Add GitHub MCP connection
- [ ] Add WordPress MCP connection
- [ ] Add local filesystem/NAS MCP server

## Phase 5 — Production hardening

- [ ] OAuth and secret-manager integration
- [ ] Sandboxing and filesystem roots
- [ ] Rate, cost, and concurrency controls
- [ ] Tracing and metrics
- [ ] Server trust registry
- [ ] Signed server manifests
- [ ] Threat modeling and penetration testing
- [ ] Backup, recovery, and incident procedures
