# MCP Communication Diagram

```mermaid
sequenceDiagram
    participant U as Requester
    participant H as Nephew Host
    participant D as Director
    participant M as Manager
    participant W as Worker
    participant C as MCP Client Session
    participant S as MCP Server
    participant P as Provider System

    U->>H: Submit mission
    H->>D: Request governed plan
    D-->>H: Plan with limits
    H->>M: Issue plan
    M->>W: Assign scoped work order
    W->>M: Request capability
    M->>H: Approve capability use
    H->>C: Invoke server capability
    C->>S: MCP request
    S->>P: Optional API/DB/CLI/file operation
    P-->>S: Provider result
    S-->>C: MCP response
    C-->>H: Structured result
    H-->>M: Receipt and result
    M-->>W: Deliver approved result or asset
    W-->>M: Completion evidence
    M-->>D: Verified outcome
    D-->>H: Final response plan
    H-->>U: Response and evidence
```

## Boundary rules

- The host owns the client lifecycle, conversation, consent, and policy.
- A client session speaks MCP to one server.
- The server exposes capabilities and may call underlying systems.
- Credentials, transport, MCP, and provider APIs remain distinct layers.
