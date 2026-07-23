# Trust, Business, MCP, and Code Crosswalk

This matrix is the central translation table for the Standard MCP Stack.

| Layer | Trust model | Business model | MCP/technical role | Suggested Nephew code location | Inputs | Outputs | Authority level | Audit expectation |
|---|---|---|---|---|---|---|---|---|
| Request origin | Beneficiary or authorized third party | Customer, sponsor, regulator, partner | User or external caller | Outside repository boundary | Mission, question, records request | Submitted request | May request; does not automatically control assets | Identity, channel, timestamp, original request |
| Interface | Phone, portal, letter, meeting | CLI, GUI, voice, web app, API | Human or machine interface | `interfaces/` | Raw request | Structured intake payload | Entry only | Channel, authentication result, payload hash |
| Public gateway | Secure submission gate | Partner/customer API gateway | HTTP API, webhook endpoint | `interfaces/api/` | Structured external request | Validated request or rejection | Schema and access enforcement | Caller, scope, rate-limit decision, response code |
| Reception | Trust office reception and mailroom | Front desk and switchboard | Entry controller | `main.py`, `intake/` | Raw or validated request | Request envelope and routing decision | May classify and route; may not invent strategy | Request ID, classification, route, validation failures |
| Identity | Trust name, purpose, character | Brand and operating identity | Stable agent identity | `identity/` | Identity documents and settings | Identity context | Read-mostly; tightly governed | Version and change approval |
| Governance | Trust instrument, bylaws, resolutions | Charter, policies, brand book, security manual | Rules and policy engine | `governance/` | Mission, identity, law/policy rules | Applicable constraints and permissions | Highest durable authority beneath human owner | Policy version, rule matches, exceptions |
| Direction | Board of trustees | Board/executive committee | Planning agents or deterministic planner | `directors/` | Mission plus governance context | Strategic plan | May plan and request approval; should not directly execute high-risk work | Plan, assumptions, rejected options, approvals needed |
| Management | Managing trustee or administrator | Operations manager, dispatcher, expo | Orchestrator and policy enforcement | `managers/` | Approved plan, resources, worker registry | Work orders, permissions, sequence, reconciled results | Delegated operational authority | Assignments, grants, approvals, retries, reconciliation |
| Worker | Contractor or specialist | Employee, technician, analyst | Task-specific agent or function | `workers/` | Scoped work order and approved assets | Result, evidence, exception, resource request | Least privilege within task | Inputs, actions, tool calls, outputs, exceptions |
| Brain | Adviser, counsel, analyst | Consultant or AI specialist | LLM or other model | `brains/` | Prompt/context | Analysis, draft, classification, plan proposal | Advisory unless separately delegated | Model ID, version, parameters, prompt provenance |
| Memory | Trust operating records | CRM, ticket history, databases | Structured and semantic state | `memory/` | Events and facts | Retrieved state or updated record | Controlled read/write by policy | Read/write identity, record version, retention |
| Knowledge | Deeds, manuals, source records | Corporate library, NAS, GitHub, Obsidian | Authoritative source corpus | `knowledge/` | Documents and repositories | Retrieved evidence | Usually read-oriented; source-specific rules | Source, version, retrieval query, citations |
| Tools | Equipment and machinery | Cameras, Git, Docker, Bash, FFmpeg | Deterministic action modules | `tools/` | Validated arguments | Action result | Scoped by manager and security policy | Command, arguments, environment, result, side effects |
| Skills | Approved methods | SOPs, runbooks, training material | Reusable workflows | `skills/` | Work order and context | Standardized procedure execution | Bound by governance | Skill version, steps selected, outcomes |
| Prompts | Approved instruction sheets | Templates, briefs, scripts | Prompt assets | `prompts/` | Variables | Rendered instruction | No independent authority | Template version and variable provenance |
| Configuration | Administrative settings | IT configuration | Environment and application config | `config/` | Values and environment | Runtime settings | Change-controlled | Source, version, overrides, secret references |
| Security | Custodian of keys and delegated authority | Security office and IAM | Authentication, authorization, approvals | `security/` | Identity, credentials, requested action | Allow, deny, redact, escalate | Can block all downstream action | Decision, policy, principal, scope, expiry |
| Host | Trust administrative office | Company headquarters / AI application | MCP host | `host/` or application root | User session, governance, models, server config | Context assembly and managed connections | Owns user relationship and cross-server control | Session, client lifecycle, context disclosures |
| Client instance | Provider-specific communication desk | One vendor connector | MCP client, 1:1 logical server session | `mcp/clients/` | Server config, transport, credentials, request | Responses and notifications | Communication only under host policy | Server ID, protocol version, capabilities, request IDs |
| Protocol | Approved correspondence standard | Standard vendor communication format | MCP data layer / JSON-RPC semantics | SDK/library dependency | Requests, responses, notifications | No business authority by itself | Protocol version and validation errors |
| Transport | Courier route or secure line | stdio or HTTP channel | MCP transport layer | `mcp/transports/` or SDK | Encoded messages | Delivered messages | Connectivity only | Endpoint, session, TLS state, connection events |
| MCP server | Vendor service desk or internal records desk | Integration service | Capability provider | External or `servers/` | MCP messages | Tools/resources/prompts/results | Limited to advertised and authorized capability | Authentication, routing, tool execution, errors |
| Server tool | Authorized vendor service | Service catalog operation | `tools/call` target | Server implementation | Structured arguments | Structured action result | Action-specific | Input schema, principal, side effects, result |
| Server resource | Approved record or catalog | Readable vendor data | Resource primitive | Server implementation | URI or resource identifier | Context/data | Read according to policy | Resource ID, version, requester, returned fields |
| Server prompt | Approved form/template | Vendor playbook | Prompt primitive | Server implementation | Prompt name and arguments | Rendered messages | Template only | Prompt version and arguments |
| Provider backend | Vendor inventory or accounting office | REST API, database, SDK, CLI | Non-MCP implementation behind server | Vendor/internal integration | Provider-specific request | Provider-specific result | Provider-defined | Provider transaction ID and response metadata |
| Audit | Trust ledger and receipts | Compliance, accounting, observability | Logs, traces, evidence store | `audit/`, `observability/` | Events from all layers | Reconstructable decision and action history | Append-only or tightly controlled | Complete chain of custody and correlation IDs |
| Final delivery | Trustee report to beneficiary | Customer response or completed service | Response assembly | `responses/` or interface adapter | Reconciled result and evidence | Human- or machine-ready answer | Must preserve disclosure policy | Delivered content, recipient, channel, timestamp |

## Core design rule

Every action should be explainable as a path across this matrix:

```text
requester → interface → reception → governance → director → manager → worker
→ approved shared asset or MCP capability → evidence → manager → director
→ reception → requester
```

Any implementation that skips authority, custody, or audit boundaries should be treated as an architectural exception requiring explicit justification.
