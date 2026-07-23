# MCP Stack Structure

This document places MCP inside the broader governed organization.

```text
Requester
  -> Interface
  -> Reception
  -> Directors
  -> Managers
  -> Workers
  -> Host-controlled capability request
  -> MCP client connection
  -> MCP server
  -> Tool, resource, prompt, local system, database, or provider API
```

## Host

The host is the application that owns:

- user interaction
- sessions
- context assembly
- governance enforcement
- approvals
- server registry
- client lifecycle
- cross-server boundaries
- result assembly

## Client

A client is the host-side protocol component associated with one server connection. It handles:

- initialization
- capability negotiation
- protocol messages
- transport
- request/response correlation
- notifications
- connection state

Credentials may be used by the surrounding host, transport, or integration, but credentials are not the client itself.

## Server

A server publishes capabilities through MCP:

- tools
- resources
- prompts

It may implement those capabilities directly or call underlying APIs, files, databases, scripts, and applications.

## One host, many connections

```text
Nephew host
  ├── GitHub MCP client <-> GitHub MCP server
  ├── WordPress MCP client <-> WordPress MCP server
  ├── Files MCP client <-> Files MCP server
  └── Docker MCP client <-> Docker MCP server
```

Each connection is isolated so capabilities, permissions, failures, credentials, and audit evidence remain attributable to the proper provider.