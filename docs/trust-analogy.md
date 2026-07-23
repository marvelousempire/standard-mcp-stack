# Trust Architecture Analogy

This is the primary teaching model for the Standard MCP Stack. It is a software analogy, not legal advice, and it does not claim that software roles are legally equivalent to trust roles.

The analogy exists for one reason: to make every technical part answerable in plain language.

> Who is asking? Who has authority? Who makes the plan? Who controls the assets? Who performs the work? Who communicates with outside parties? Who records what happened?

If those questions are clear, the software architecture is clear.

---

## 1. The trust itself

The entire Nephew application is the trust estate and operating office taken together.

It has:

- a durable identity;
- a defined purpose;
- governing documents;
- fiduciary decision-makers;
- managing personnel;
- contracted workers;
- property and records;
- outside vendors;
- communication channels;
- authority boundaries;
- receipts and audit history.

The language model is not the trust. It is one adviser or reasoning asset available to the trust.

The MCP client is not the trust. It is a communications instrument operated by the trust office.

The MCP server is not the vendor itself. It is the standardized service desk through which that vendor exposes approved capabilities.

---

## 2. Full role map

| Software architecture | Trust analogy | Business analogy | Primary responsibility |
|---|---|---|---|
| User or requester | Beneficiary, settlor-authorized party, bank, auditor, or authorized third party | Customer, owner, executive sponsor, regulator, or partner | States a need, mission, request, or demand for records |
| Interface | Phone, letter, secure portal, scheduled meeting, front gate | Website, mobile app, CLI, voice line, service desk | Provides a channel into the organization |
| Public API | Authorized electronic submission gate | Partner API, customer API, webhook endpoint | Accepts structured outside requests under authentication and rate limits |
| `main.py` / entry controller | Reception desk and mailroom | Front desk, intake desk, switchboard | Receives, timestamps, validates, normalizes, and routes the request |
| Identity | Name and legal identity of the trust | Brand, corporate identity, operating profile | Answers who Nephew is regardless of which model is installed |
| Governance | Trust instrument, bylaws, resolutions, policies, delegations | Charter, bylaws, policy manual, brand book, security policy | Defines purpose, powers, restrictions, style, values, and decision boundaries |
| Directors | Board of trustees or directing fiduciaries | Board, executive committee, strategic leadership | Interpret the mission under governance and create the plan |
| Managers | Managing trustees or trust administrators | Department managers, dispatchers, operations management | Convert plans into work orders, assign workers, grant temporary access, enforce approvals, and reconcile results |
| Workers | Contractors, accountants, attorneys, builders, researchers, repair specialists | Employees, contractors, analysts, operators, technicians | Perform scoped work and return evidence and results |
| Brains | Advisers, counsel, analysts, subject-matter experts | AI models, consultants, specialists, analysts | Reason, classify, draft, compare, code, interpret, or recommend |
| Memory | Trust records, accounting history, correspondence, transaction history | CRM, databases, ticket history, operational records | Preserve continuity across time |
| Knowledge | Trust instrument copies, deeds, manuals, reports, source records | Document repositories, NAS, GitHub, Obsidian, WordPress, manuals | Supply authoritative source material |
| Tools | Equipment, calculators, filing systems, machinery | Git, Docker, Bash, databases, browsers, media tools | Perform concrete deterministic actions |
| Skills | Approved procedures and repeatable work methods | SOPs, runbooks, playbooks, job aids | Define how recurring jobs should be performed |
| Prompts | Standard instruction sheets and interview scripts | Templates, scripts, checklists, briefs | Shape how reasoning work is requested |
| Settings | Administrative preferences | Application settings, environment configuration | Control adjustable behavior without rewriting the organization |
| Credentials | Signature authority, account card, key, badge, seal | API key, OAuth token, certificate, password, service account | Prove identity or delegated authority |
| Authorization policy | Delegation schedule and spending authority | RBAC, scopes, approval limits, access policy | Defines what an authenticated party may do |
| MCP host | Trust office and administrative headquarters | Nephew application or AI desktop | Contains governance, models, policy, interfaces, and client connections |
| MCP client | Communications instrument operated by the office for one provider relationship | Connector instance inside the host | Maintains one logical session with one MCP server |
| MCP protocol | Standardized correspondence rules and approved forms | Shared communication standard | Defines message shape, lifecycle, negotiation, and semantics |
| MCP transport | Courier route, secure phone line, private delivery channel | stdio, Streamable HTTP, network channel | Carries the protocol messages |
| MCP request | Completed requisition, instruction letter, or work order | Structured operation request | Names the requested capability and supplies arguments |
| MCP response | Vendor reply, fulfillment notice, receipt, or denial | Operation result or error | Returns the result associated with a request |
| MCP notification | Status bulletin requiring no reply | Event or one-way update | Communicates a change without opening a response cycle |
| MCP server | Vendor's authorized service desk, records desk, or specialist representative | Integration service or local capability provider | Publishes approved capabilities and processes standardized requests |
| Server tool | Service the vendor is willing to perform | Callable function | Executes an action |
| Server resource | Record, catalog, document, or data source the vendor will provide | Readable context | Supplies information |
| Server prompt | Vendor's approved template or intake procedure | Reusable interaction template | Structures a recurring request |
| Provider API | Vendor's internal ordering, accounting, or inventory system | REST, GraphQL, database, CLI, SDK | Performs provider-specific operations behind the MCP server when needed |
| TLS/VPN | Sealed courier bag or protected private road | Encrypted transport | Protects information in transit |
| Audit log | Trust ledger, correspondence register, signed receipts | Logs, traces, transaction ledger | Records who requested, approved, executed, received, or denied work |
| Secret store | Locked records safe | Keychain, vault, secrets manager | Holds credentials separately from ordinary code and configuration |

---

## 3. The authority chain

The trust model separates **authority**, **coordination**, and **labor**.

### Beneficiary or authorized requester

The requester supplies the mission. The requester does not directly operate every asset or instruct every contractor.

Example:

> Repair the property, document the work, and keep the cost below the approved limit.

### Reception

Reception does not decide the strategy and does not perform the repair. Reception performs intake.

Reception should:

1. identify the requester;
2. verify the channel;
3. record the mission;
4. assign a request identifier;
5. classify urgency and sensitivity;
6. route the mission to the correct director;
7. preserve the original wording.

### Directors

Directors answer:

- Is this request within the trust's purpose?
- What bylaws or policies apply?
- What outcome is actually required?
- What workstreams are necessary?
- What must receive human approval?
- What evidence must be returned?

They produce a plan, not the final labor.

### Managers

Managers receive the approved plan and convert it into controlled work orders.

Managers answer:

- Which worker should receive each task?
- Which brain, tool, memory source, or vendor may be used?
- Which credentials and permissions are permitted?
- What budget, time, scope, and risk limits apply?
- Does the action require approval before execution?
- How will the result be checked and reconciled?

Managers are the control plane.

### Workers

Workers perform bounded tasks.

A worker receives:

- a specific objective;
- approved inputs;
- a permitted set of tools and resources;
- a deadline or stopping condition;
- a required output format;
- escalation instructions.

Workers do not own the trust assets. They receive temporary, task-scoped access through management.

---

## 4. The trust assets

The trust office operates several classes of shared assets.

### Brains

Brains are models or reasoning services. They are advisers, not identity.

One brain may be strong at coding. Another may be strong at vision. Another may be inexpensive and fast. The trust can replace a brain without replacing Nephew.

### Memory

Memory contains accumulated operating history.

Examples:

- conversation records;
- task state;
- preferences;
- account records;
- structured facts;
- vector indexes;
- SQL databases;
- project history.

Memory answers, “What has happened before?”

### Knowledge

Knowledge contains source material.

Examples:

- WordPress content;
- Obsidian vaults;
- GitHub repositories;
- NAS documents;
- manuals;
- contracts;
- reference datasets.

Knowledge answers, “What evidence or material can we consult?”

### Tools

Tools perform actions.

Examples:

- Git;
- Bash;
- Docker;
- FFmpeg;
- database clients;
- file operations;
- deployment commands.

Tools answer, “What can perform the actual operation?”

### Skills

Skills are reusable operating procedures that combine reasoning, tools, checks, and output requirements.

A skill is closer to a standard operating procedure than to a model weight.

---

## 5. The MCP communications office

The MCP portion of the trust is best understood as a **standardized communications office**.

### The host is the trust office

The host owns:

- the user relationship;
- the conversation;
- governance;
- model access;
- approvals;
- credentials policy;
- server configuration;
- client lifecycle;
- final context assembly.

Official MCP architecture gives the host responsibility for creating and managing multiple client instances, enforcing security policy, coordinating model integration, and controlling context across connections.

### A client is one provider desk inside the communications office

For every active MCP server relationship, the host creates one logical MCP client connection.

Therefore:

- GitHub server relationship → GitHub client instance;
- filesystem server relationship → filesystem client instance;
- WordPress server relationship → WordPress client instance;
- Docker server relationship → Docker client instance.

They may all use the same client library, just as several desks may use the same office procedures and forms. But each connection remains isolated.

This is why the correct model is:

> One host, many client instances, one logical client-to-server session per connection.

### The protocol is the approved correspondence standard

MCP is not the clerk, credential, vendor, or road. It is the standard governing how the two offices exchange messages.

It defines:

- initialization;
- protocol version agreement;
- capability negotiation;
- request and response shapes;
- notifications;
- tools, resources, and prompts;
- lifecycle and errors.

### Transport is the delivery route

A trust letter can travel by courier, secure portal, or internal mail while retaining the same approved form.

Likewise, MCP messages can travel over different transports. The protocol remains the communication standard; the transport is how the message moves.

### Credentials are proof of authority

A credential is not a client.

A client uses credentials in accordance with host policy. A credential may prove the trust's identity, a user's identity, or a delegated service identity.

### The server is the provider's MCP service desk

The server states:

> These are the tools, resources, and prompts I am authorized to expose through this standard.

It may be:

- local to the trust office;
- on another machine inside the organization;
- operated by a vendor;
- hosted remotely;
- a wrapper around an API;
- a direct interface to files, databases, or command-line tools.

The server does not automatically receive the entire conversation. The host decides what context is shared with each server, preserving separation between vendors and workstreams.

---

## 6. Full example: property repair and Home Depot procurement

### Phase A: mission intake

1. The beneficiary asks Nephew to repair a damaged room, document the work, and remain under budget.
2. The request enters through voice, CLI, GUI, or API.
3. Reception records the exact mission, requester identity, date, priority, and constraints.
4. Reception routes the mission to the appropriate director.

### Phase B: governance and planning

5. The director consults the trust instrument, bylaws, spending policy, safety rules, preferred vendors, and aesthetic standards.
6. The director creates a plan containing inspection, materials, labor, verification, documentation, and budget control.
7. Any step outside delegated authority is marked for beneficiary or human approval.
8. The approved plan goes to management.

### Phase C: work-order creation

9. Management creates a scoped inspection order for a worker.
10. The worker inspects the damage and reports that drywall, primer, paint, rollers, and protective material are needed.
11. The worker does not take the purchasing credential or freely access the vendor account.
12. The worker submits a requisition to management.

### Phase D: authorization

13. Management checks the budget, worker scope, vendor policy, quantity limits, and approval requirements.
14. Management approves, modifies, denies, or escalates the requisition.
15. Once approved, the host selects the configured Home Depot or procurement server connection.

### Phase E: MCP initialization

16. The host creates or reuses the isolated client instance assigned to that server.
17. The client opens the configured transport.
18. The client and server negotiate protocol version and capabilities.
19. The host records which tools, resources, prompts, and optional features are available for that session.
20. Capability availability is checked separately from authorization. A purchasing tool may exist while policy still denies its use.

### Phase F: MCP operation

21. Management asks the host communications layer to obtain prices or place an approved order.
22. The client builds a structured MCP request.
23. The client uses the configured credential mechanism without exposing secrets to the worker or model unnecessarily.
24. The request travels over the transport to the MCP server.
25. The server authenticates the caller and checks authorization.
26. The server routes the request to the appropriate tool implementation.
27. The tool may call a vendor API, query inventory, use an SDK, access a database, or perform local logic.
28. The provider operation returns a result.
29. The server converts that result into an MCP response.
30. The response returns to the isolated client instance.
31. The host validates and normalizes the result.

### Phase G: reconciliation and completion

32. Management records prices, approval, transaction identifiers, and receipts.
33. The worker receives only the information or supplies needed for the assigned task.
34. The worker completes the repair and submits photos, measurements, and completion notes.
35. Management verifies the work against the plan and records exceptions.
36. The director evaluates whether the mission outcome was satisfied.
37. Reception formats the final response for the requester.
38. The audit ledger preserves the chain from mission through approval, execution, and result.

---

## 7. Records request from a bank

Not every requester is a beneficiary.

A bank may request a trust certificate or abstract through an authorized external API.

1. The bank authenticates at the public API.
2. The API applies rate limits, schema validation, and authorization requirements.
3. Reception creates an intake record.
4. A director determines which governing rules apply and which disclosure is permitted.
5. Management assigns a records worker.
6. The worker requests the approved document from knowledge or memory.
7. Management checks redactions, disclosure authority, and recipient identity.
8. The result returns through reception and the public API.
9. The audit ledger records precisely what was disclosed, to whom, under what authority.

The public API is the front-facing electronic gate into Nephew. MCP may be used internally to retrieve or generate the records, but the outside bank does not need to know or speak MCP unless the system is intentionally exposed that way.

---

## 8. Local server example

Suppose Nephew runs a filesystem MCP server on the same Mac.

- The trust office and service desk are in the same building.
- The client still maintains a separate logical session.
- The server still exposes only approved roots and capabilities.
- The server may operate directly on local files without any outside API.
- The host still controls which context and permissions are shared.

“Server” describes the role of providing capabilities, not necessarily a distant machine.

---

## 9. Corrections that preserve the analogy

- **MCP is not a request.** MCP is the standard; the request is one message following that standard.
- **The client is not a form.** The client prepares, sends, receives, and manages the exchange; the request is the completed form.
- **The client is not a credential.** It uses credentials under host control.
- **The manager is not the MCP client.** Management decides and delegates; the host's communications layer performs the protocol operation.
- **The API is not the VPN.** An API defines available operations; TLS or VPN protects the communication route.
- **The server is not always outside.** It may be a local process, internal service, or remote provider.
- **The server does not have to wrap an API.** It may access files, databases, devices, or original logic directly.
- **One host does not mean one client instance.** The host normally creates a separate client for each server connection.
- **A capability being advertised does not grant permission.** Policy and authorization remain separate.
- **A model should not automatically see every credential or server result.** The host controls disclosure and context assembly.

---

## 10. The compact trust pipeline

```text
AUTHORIZED REQUESTER
        │
        ▼
INTERFACE / PUBLIC API
        │
        ▼
RECEPTION — main.py / intake controller
        │
        ▼
DIRECTORS — interpret mission under governance
        │
        ▼
MANAGERS — issue work orders and control access
        │
        ├────────────── consult shared assets ──────────────┐
        │                                                   │
        ▼                                                   ▼
WORKERS                                          BRAINS / MEMORY / KNOWLEDGE
        │                                                   │
        └──────── request approved capability ──────────────┘
                                │
                                ▼
                   HOST COMMUNICATIONS LAYER
                                │
                  one isolated MCP client instance
                                │
                         MCP over transport
                                │
                                ▼
                         MCP SERVER DESK
                                │
                 tool / resource / prompt implementation
                                │
                    optional provider API or local system
                                │
                                ▼
                         RESULT AND RECEIPT
                                │
                                ▼
WORKER → MANAGER → DIRECTOR → RECEPTION → REQUESTER
```

This pipeline is the core footprint for Nephew: governance at the top, controlled work in the middle, shared assets to the side, standardized communications at the boundary, and evidence flowing back up.
