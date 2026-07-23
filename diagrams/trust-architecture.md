# Trust Architecture Diagram

```mermaid
flowchart TD
    A[Authorized Requester / Beneficiary] --> B[Interface]
    B --> C[Reception / Host Intake]
    C --> D[Directors]
    G[Trust Instrument / Bylaws / Identity] --> D
    D --> E[Managing Trustees / Managers]
    E --> F[Contracted Worker]
    E --> H[Controlled Shared Assets]
    H --> H1[Brains]
    H --> H2[Memory]
    H --> H3[Knowledge]
    H --> H4[Tools]
    H --> H5[Skills]
    H --> H6[Credentials]
    F --> I[MCP Client Session]
    I --> J[MCP Server]
    J --> K[Tool / Resource / Prompt]
    K --> L[API / Database / Files / CLI / Device]
    L --> M[Result / Receipt / Evidence]
    M --> F
    F --> E
    E --> D
    D --> C
    C --> A
```

## Interpretation

- Governance grants authority but does not execute work.
- Directors interpret the trust purpose and create plans.
- Managers issue scoped work orders and control assets.
- Workers execute bounded tasks.
- MCP is the communications layer used to reach service providers.
- Results and evidence return upward through the same accountability chain.
