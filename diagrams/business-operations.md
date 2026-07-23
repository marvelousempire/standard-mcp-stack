# Business Operations Diagram

```mermaid
flowchart TD
    A[Customer / Owner / Operator] --> B[Website / CLI / GUI / Voice / API]
    B --> C[Reception / Application Controller]
    C --> D[Directors / Executive Planning]
    P[Charter / Policy / Brand / Rules] --> D
    D --> E[Operations Managers]
    E --> F[Workers / Specialists]
    E --> G[Shared Company Services]
    G --> G1[AI Models]
    G --> G2[Data and Memory]
    G --> G3[Knowledge Sources]
    G --> G4[Tools and Equipment]
    G --> G5[Skills and SOPs]
    G --> G6[Credentials and Accounts]
    F --> H[Integration Client]
    H --> I[Provider Service Desk]
    I --> J[Provider Systems]
    J --> K[Result / Ticket / Receipt]
    K --> F
    F --> E
    E --> D
    D --> C
    C --> A
```

## Restaurant parallel

- Reception receives the guest request.
- Directors define the menu and service plan.
- The expediter or manager breaks the order into station work.
- Specialized workers prepare bounded parts.
- Shared equipment and ingredients remain controlled resources.
- Tickets and completed plates return through the expediter.

## Photo-studio parallel

- Management checks cameras, lenses, storage, and credentials out to a scoped shoot.
- Workers do not permanently own company equipment.
- Every asset movement and completed deliverable leaves a record.
