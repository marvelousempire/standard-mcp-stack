# MCP Stack Glossary

This glossary separates the pieces that are commonly blended together when people first learn Model Context Protocol.

## Host

The AI application that owns the user experience, policy, model access, approvals, and MCP connections. In the Nephew architecture, the host is the whole operating application—not merely the language model.

A host typically creates one MCP client instance for each MCP server connection.

## MCP Client

A software component created and managed by the host. It maintains one logical session with one MCP server, negotiates protocol version and capabilities, sends requests, receives responses, and handles notifications.

The client is not the user, worker, manager, credential, request form, or physical computer. Those may use or contain the client.

## MCP Server

A local process or remote service that exposes capabilities through MCP. A server may expose tools, resources, prompts, logging, completions, or other negotiated features.

A server may wrap an existing API, access a database directly, operate on local files, run command-line programs, or implement original business logic.

## Protocol

The shared rules both sides follow. MCP defines message shapes, lifecycle, capability negotiation, methods, notifications, and semantics. MCP messages use JSON-RPC 2.0.

## Transport

The channel carrying protocol messages. Common transport patterns include standard input/output for local processes and Streamable HTTP for remote services.

Protocol is the language. Transport is the road or wire.

## Request

A message that expects a response. A request has an identifier, method, and optional parameters.

## Response

The result or error returned for a request identifier.

## Notification

A one-way message that does not expect a response.

## Capability

A feature declared during initialization. Capabilities prevent either side from assuming unsupported behavior.

## Tool

An executable operation exposed by a server. Examples include creating an issue, querying a database, writing a file, or running a calculation.

## Resource

Readable context exposed by a server. Examples include a document, file, database record, repository history, or generated report.

## Prompt

A reusable interaction template exposed by a server for user or application selection.

## Sampling

A client capability that allows a server to ask the host to obtain a language-model completion while the host remains in control of model access and user policy.

## Roots

Filesystem locations the client makes available as bounded working areas to a server.

## Elicitation

A client capability allowing a server to request additional structured input from the user through the host.

## Credentials

Secrets or proof used to authenticate, such as OAuth tokens, API keys, certificates, or local process permissions. Credentials are not the MCP client itself.

## Authentication

The act of proving identity.

## Authorization

The decision about what an authenticated identity may do.

## API

An interface offered by a system. An MCP server may use an API behind the scenes, but MCP and API are not interchangeable terms.

## Worker

A Nephew application role assigned a scoped task. A worker may request a capability through management. It does not need to implement MCP itself.

## Manager

The Nephew coordination role that assigns workers, applies policy, controls access, and routes approved operations through shared services.

## Director

The Nephew planning role that interprets the mission under governance and produces an execution plan.

## Governance

The durable identity, mission, bylaws, policies, rules, permissions, aesthetics, and behavioral constraints that remain stable even when models and tools are replaced.
