# Standard MCP Stack Rosetta Stone

This is the primary translation table for the repository. It maps trust, business, Nephew, Python, MCP, AI, security, and audit concepts to one another.

| Layer | Trust model | Business model | Nephew component | Python/code form | MCP relationship | AI role | Security meaning | Audit evidence | Example |
|---:|---|---|---|---|---|---|---|---|---|
| 0 | Trust instrument | Charter and policy | Governance | `governance/` documents and policy objects | Outside protocol; governs host use | Defines model boundaries | Source of authority | Policy version and decision trace | “Do not publish without approval” |
| 0 | Name, purpose, settlor intent | Brand, mission, operating identity | Identity | `identity/`, profile and system policy | Host-owned | Stable persona across models | Identity anchor | Identity version | Nephew remains Nephew after model swap |
| 1 | Beneficiary or authorized petitioner | Customer, owner, operator | Requester | CLI user, GUI user, API caller | Supplies host input | Human intent | Must be authenticated and authorized | Request identity and timestamp | “Summarize this repo” |
| 1 | Petition, letter, inquiry channel | Website, phone, voice, API | Interface | CLI, GUI, HTTP route, voice adapter | Host surface | Captures natural language | Input validation and rate limits | Raw request and channel | Terminal prompt |
| 2 | Trust office reception | Front desk | Reception | `main.py`, controller, router | Part of host | Minimal classification | Intake validation | Correlation ID and routing record | Route GitHub mission to planning |
| 2 | Trust office | Company headquarters | MCP host | Application process and session manager | Owns clients and user relationship | Integrates models and context | Consent, isolation, policy enforcement | Session and approval logs | Nephew application |
| 3 | Board/directing trustees | Directors/executives | Directors | Planner classes and plan schemas | Host logic above MCP | Reasoning and decomposition | Cannot grant itself authority | Plan, assumptions, governance citations | Plan repo update |
| 4 | Managing trustees | Operations managers | Managers | Orchestrator, scheduler, allocator | Selects client/server capability | May use model-assisted routing | Enforces work-order scope | Assignment and approval records | Assign Git worker |
| 5 | Contractor or specialist | Employee, contractor, station | Worker | Worker class/function/agent loop | Requests tools/resources through host | Task-focused reasoning | Receives least privilege | Execution log and result | Git worker edits files |
| 6 | Professional adviser | Analyst, engineer, designer | Brain | Model adapter/end point | Not inherently MCP | Generates, reasons, classifies | No independent authority | Model/version and prompt trace | Qwen coding model |
| 6 | Trust ledger and history | Operational records | Memory | SQLite, Postgres, vector DB, event store | May be exposed as resources | Supplies retained context | Data minimization and retention | Read/write history | Prior decisions |
| 6 | Deeds, manuals, source records | Documentation and source-of-truth data | Knowledge | NAS, GitHub, Obsidian, WordPress, files | Often exposed as resources | Grounds answers | Source access controls | Source citations and retrieval log | Architecture document |
| 6 | Equipment | Company tools | Tool | Python function, CLI wrapper, API operation | Server-exposed callable capability | Enables action | Invocation policy and parameter validation | Tool call and output | `git commit` |
| 6 | Approved procedure | SOP or reusable workflow | Skill | Prompt + code + schema + tests | May combine tools/resources | Reusable behavior | Predefined boundaries | Skill/version and steps | Publish repo workflow |
| 6 | Signature authority, key, badge | API key, token, certificate | Credential | Secret manager reference | Used during connection/provider calls | None | Proves identity; does not create policy | Secret identifier, never secret value | GitHub token |
| 7 | Communications office | Integration department | MCP client | Client library and one logical server session | Client side | Translates host requests | Connection-scoped permissions | Connect/disconnect and request IDs | GitHub client session |
| 7 | Standard correspondence format | Shared communications standard | MCP protocol | SDK message types and handlers | Shared by client/server | None | Does not replace auth | Protocol version and messages | Tool discovery request |
| 7 | Completed requisition | Work order/message | MCP request | Structured protocol message | Sent client to server | May contain model-selected arguments | Must be validated | Request ID and arguments | Call `create_issue` |
| 8 | Vendor or internal service desk | Provider department | MCP server | Server process with registries and handlers | Server side | May use AI internally, but need not | Authenticates and authorizes caller | Capability and invocation logs | GitHub MCP server |
| 8 | Service catalog | Product/service menu | Tool/resource/prompt registry | Registry objects and schemas | Advertised server capabilities | Describes available assistance | Advertisement is not permission | Capability snapshot | List GitHub tools |
| 9 | Vendor machinery and inventory | Backend systems | Underlying system | REST API, DB, filesystem, CLI, device | Behind server, optional | Usually deterministic | Provider-specific access rules | Provider receipt/transaction ID | GitHub REST API |
| 9 | Secure courier route | TLS/VPN/private network | Transport security | HTTPS, stdio, secure channel | Carries MCP messages | None | Confidentiality and integrity | Connection metadata | Encrypted remote transport |
| 10 | Receipt, minutes, certificate | Ticket, log, report | Evidence | Structured event, artifact, diff, result | Returned through stack | Supports verification | Nonrepudiation and review | Immutable or durable record | Commit SHA |
| 10 | Accounting ledger | Audit system | Audit trail | Event store and trace IDs | Cross-cutting | None | Reconstructs authority and action | Request-plan-approval-execution chain | Who changed what and why |

## Governing translations

- **Authority** in the trust model equals **policy-backed permission**, not technical capability.
- **Custody** equals control over secrets, models, data, tools, and infrastructure.
- **Delegation** equals a scoped plan or work order containing explicit limits.
- **Receipt** equals machine-verifiable evidence such as a diff, commit SHA, response, artifact, or log.
- **Vendor desk** equals an MCP server only when it actually speaks MCP.
- **Provider machinery** equals the API, database, file system, CLI, or service behind the server.

## Use this matrix when

- introducing a new AI or MCP concept
- deciding where a Python module belongs
- reviewing whether authority is enforced at the correct layer
- explaining the system to technical or nontechnical readers
- preventing one term from being used for several different responsibilities
