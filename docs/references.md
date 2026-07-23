# Technical References

The trust and business analogies in this repository are original teaching models. Technical MCP statements should remain anchored to the official Model Context Protocol documentation and specification.

## Official MCP documentation

- Model Context Protocol specification index: `https://modelcontextprotocol.io/specification/`
- Architecture: `https://modelcontextprotocol.io/specification/2025-06-18/architecture`
- Lifecycle: `https://modelcontextprotocol.io/specification/2025-06-18/basic/lifecycle`
- Architecture learning guide: `https://modelcontextprotocol.io/docs/learn/architecture`

## Technical facts used by this repository

- MCP uses a host-client-server architecture.
- A host creates and manages multiple client instances.
- Each client maintains an isolated stateful session with a particular server.
- Servers can be local processes or remote services.
- Servers expose focused capabilities such as tools, resources, and prompts.
- Client and server capabilities are negotiated during initialization.
- MCP's data layer uses JSON-RPC 2.0 messages.
- Transport and protocol are separate layers.
- Hosts are responsible for user authorization, consent, model integration, context aggregation, and cross-server security boundaries.
- Servers should receive only the context necessary for their focused responsibility rather than automatically seeing the entire conversation or other server sessions.

## Maintenance rule

When this repository changes a protocol-specific claim:

1. consult the current official specification;
2. record the protocol revision being implemented;
3. distinguish normative MCP requirements from local Nephew architecture choices;
4. update examples and matrices together;
5. preserve older version notes when compatibility is relevant.
