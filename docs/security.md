# Security Model

## Security is not a prompt

Prompts can explain intended behavior, but security must be enforced by software controls outside the model.

## Distinct concepts

### Identity
Who is acting: user, service, host, client, or server.

### Authentication
How identity is proven: token, OAuth, mTLS, local process boundary, signed assertion, or another mechanism.

### Authorization
What the authenticated identity may do: scopes, tool allowlists, repository boundaries, read/write permissions, spending limits, and approval requirements.

### Transport security
How messages are protected in transit: TLS, private networking, VPN, or local process isolation.

### Secrets management
How credentials are stored, injected, rotated, and revoked.

## Recommended boundaries

1. The model never receives raw API keys unless absolutely unavoidable.
2. Workers receive capability handles, not unrestricted credentials.
3. Managers enforce access before a tool call is dispatched.
4. MCP servers independently enforce authorization; they do not trust prompts.
5. Write operations are separated from read operations.
6. High-impact effects require explicit approval.
7. Filesystem servers operate within declared roots.
8. Shell tools use allowlists or isolated environments.
9. Logs redact tokens, passwords, private keys, and sensitive payloads.
10. Every externally visible effect receives an audit record.

## Credential flow

```text
Secret Manager
      |
      | temporary or referenced credential
      v
Host/Transport Credential Provider
      |
      v
MCP Server Authentication
      |
      v
Authorization Policy
      |
      v
Approved Capability Handler
```

## Threats to design against

- prompt injection in retrieved documents
- tool argument injection
- shell command injection
- path traversal
- server impersonation
- credential leakage
- overbroad OAuth scopes
- confused-deputy behavior
- unauthorized cross-tenant access
- malicious or compromised MCP servers
- silent data exfiltration
- unbounded cost or compute consumption
- unsafe retries of non-idempotent operations

## Trust levels

| Level | Example | Default treatment |
|---|---|---|
| 0 | Unknown remote server | Deny until reviewed |
| 1 | Read-only public-data server | Isolated, limited calls |
| 2 | Authenticated read server | Scoped credentials, audit |
| 3 | Write-capable business server | Approval gates and strict scopes |
| 4 | Local privileged server | Sandbox, allowlists, full audit |

## Server onboarding checklist

- identify owner and source
- inspect implementation and dependencies
- record transport and endpoint
- document capabilities
- document required scopes
- classify data sensitivity
- classify possible effects
- test malformed requests and errors
- configure timeouts and rate limits
- establish approval policy
- establish secret rotation and revocation
- add server to allowlist only after review
