# Standard MCP Stack Master Matrix

This matrix is the Rosetta Stone for the repository. It maps trust governance, business operations, Nephew architecture, Python implementation, MCP roles, AI concepts, authority boundaries, and concrete examples into one shared model.

| Layer | Trust analogy | Business analogy | Nephew role | Python/code location | MCP role | AI role | Authority | Typical input | Typical output | Example | Audit evidence |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Request origin | Beneficiary or authorized third party | Customer, client, regulator, partner | User or external caller | `interfaces/` | Host input | Human intent | May request within allowed scope | Natural-language request, form, event | Accepted or rejected request | “Summarize this repository” | Request ID, requester identity, timestamp |
| Interface | Mailbox, reception channel, appointment line | Website, CLI, app, phone, voice channel | CLI, GUI, voice, API | `interfaces/cli.py`, `interfaces/api.py` | Outside MCP proper | Input capture | No execution authority | User message, file, voice, API payload | Normalized request | Voice request becomes text mission | Interface logs |
| Reception | Trust office receptionist | Front desk or intake desk | `main.py` | `main.py` or `app.py` | Host entrypoint | Intake and normalization | Route only | Raw request | Request envelope | Adds request ID and source | Intake record |
| Identity | Name and legal identity of the trust | Brand and corporate identity | Nephew identity | `identity/` | Host policy | Stable assistant identity | Defines who the system is | Mission, profile, style | Identity context | Nephew remains Nephew after model swap | Versioned identity files |
| Governing instrument | Trust instrument and bylaws | Charter, policies, SOPs | Governance layer | `governance/` | Host governance | Rules and constraints | Highest internal authority | Rules, limits, approval thresholds | Policy decisions | No destructive action without approval | Policy version and decision record |
| Directors | Board of trustees | Board, executives, strategy office | Planning directors | `directors/` | Host planning | Reasoning/planning model or code | Plan, not execute | Mission and governance context | Strategic plan | Break “publish release” into phases | Plan artifact |
| Managing trustees | Administrative or managing trustees | Managers, dispatchers, operations | Managers/orchestrators | `managers/` | Host coordination | Routing and control | Delegate, approve, allocate | Plan and capability inventory | Work orders | Assign Git worker and docs worker | Assignment ledger |
| Workers | Contractors and specialists | Employees, contractors, stations | Workers | `workers/` | Host-controlled capability users | Task execution | Only scoped delegated authority | Work order and approved assets | Result package | Git worker reads repository | Worker report |
| Skills | Approved trade methods | Playbooks, SOPs, reusable procedures | Skills library | `skills/` | Host-side procedures | Prompt/program patterns | Used only within assigned scope | Task type and context | Reusable execution method | “Summarize repository” skill | Skill version |
| Brains | Advisers and experts | Analysts, engineers, counsel | Model adapters | `brains/` | Outside or behind host | LLM, VLM, embedding model | Advisory unless delegated | Prompt and context | Draft, classification, plan | Qwen drafts a summary | Model ID, prompt hash, settings |
| Memory | Trust records and operating history | CRM, logs, institutional memory | Memory services | `memory/` | Often exposed as MCP resources | Episodic and semantic memory | Read/write by policy | Events, messages, facts | Retrieved or stored memory | Prior decision recalled | Retrieval trace and write receipt |
| Knowledge | Deeds, manuals, certificates, archives | Documentation, repos, websites | Knowledge sources | `knowledge/` | MCP resources or external systems | Grounding data | Usually read-only | Query or document reference | Evidence and source material | Read README from GitHub | Source URI and checksum |
| Tools | Equipment owned or rented by trust | Cameras, terminals, software tools | Tool adapters | `tools/` | MCP tools or local functions | Deterministic action | Scoped and permissioned | Tool name and arguments | Action result | Run Git status | Tool call log |
| Host | Trust office or headquarters | Company operating system | Nephew application | `host/` | MCP host | Context, lifecycle, approvals | Owns sessions and policy enforcement | User request and server registry | Coordinated response | Nephew manages GitHub and WordPress connections | Session record |
| Client instance | Communications capability used by trust office | Vendor communications adapter | MCP client connection | `mcp/clients/` | MCP client | Protocol-speaking component | No independent business authority | Server config, credentials reference, request | MCP message and response | GitHub client connects to GitHub server | Connection log |
| Protocol | Standard forms and communication language | Standard ordering or EDI format | MCP message rules | SDK/library dependency | MCP protocol | Structured messaging | Defines format, not permission | Method, params, IDs | Valid protocol message | `tools/list` or `tools/call` | Protocol trace |
| Transport | Secured road, courier, phone line | Network channel | Connection transport | `mcp/transports/` | stdio or remote transport | Data movement | No policy authority | Bytes/messages | Delivered messages | Local stdio or HTTPS stream | Connection metadata |
| Credentials | Seal, signature authority, membership card | API key, OAuth token, account credentials | Secret references | `security/secrets.py` | Used by host/client/server | Authentication material | Proves identity; does not itself grant every action | Secret reference or token | Authenticated identity | GitHub token | Secret ID, never secret value |
| Authentication | Verification of seal or identity | Login or account verification | Identity verification | `security/authentication.py` | Often transport/server-specific | Security control | Verifies who is calling | Credentials | Authenticated principal | Verify OAuth token | Auth event |
| Authorization | Trustee checks delegated powers | RBAC, scopes, permission policy | Permission engine | `security/authorization.py` | Host and server enforcement | Security decision | Allows or denies action | Principal, action, resource | Permit or deny | Read repo allowed, delete denied | Decision log |
| MCP server | Outside service desk or internal records office | Vendor integration service | Capability provider | `mcp/servers/` | MCP server | Exposes tools/resources/prompts | Provides only declared capabilities | MCP requests | MCP responses | GitHub MCP server | Server logs |
| Tool registry | Approved vendor service catalog | Product/service catalog | Tool inventory | `mcp/servers/*/tools.py` | MCP tools | Callable actions | Defined per tool | Tool discovery or call | Tool schema or result | `create_issue` | Tool definition version |
| Resource registry | Trust records catalog | Data catalog | Resource inventory | `mcp/servers/*/resources.py` | MCP resources | Readable context | Usually read under policy | URI or resource query | Resource contents | Read repository file | Resource URI and checksum |
| Prompt registry | Approved templates and forms | Standard scripts/templates | Prompt inventory | `mcp/servers/*/prompts.py` | MCP prompts | Reusable prompt templates | Does not itself execute | Prompt name and arguments | Prompt content | Release-summary prompt | Prompt version |
| Provider API | Vendor’s internal counter and systems | REST, GraphQL, SDK, database | Underlying integration | `integrations/` | Behind MCP server | External service operation | Governed by provider permissions | Provider-specific request | Provider-specific result | GitHub REST API | Provider request ID |
| Approval gate | Trustee consent or co-signature | Manager approval workflow | Approval service | `governance/approvals.py` | Host control around MCP calls | Human-in-the-loop | Grants temporary execution authority | Proposed action and risk | Approved, denied, amended | Approve repo deletion | Approval record |
| Budget/quota | Trust budget and spending authority | Cost center and quotas | Resource limits | `governance/limits.py` | Host/server policy | Cost and usage control | Caps consumption | Estimated tokens, time, money | Allowed or blocked | Limit embedding job size | Usage ledger |
| Session | Matter file or active trust proceeding | Customer case or work order | Conversation/task session | `host/session.py` | Host session | Active context | Bounded by session policy | Requests, results, state | Session context | One repository review session | Session transcript |
| Context | Documents assembled for a matter | Briefing packet | Model context | `host/context.py` | Host-managed context | Prompt context | Curated by host | Governance, memory, resources | Context package | Repo files plus instructions | Context manifest |
| Router | Trustee or operations dispatcher | Traffic controller, expediter | Capability router | `host/routing.py` | Selects client/server/tool | Model or rule-based routing | Route only within policy | Work order and registry | Selected capability | Send Git task to GitHub server | Routing decision |
| Execution result | Contractor’s completed work | Deliverable | Worker result | `workers/results.py` | MCP result content | Generated or deterministic result | Must match work order | Tool output, artifact, status | Result package | Pull request created | Result ID and checks |
| Validation | Inspection by trustee or supervisor | QA, review, acceptance testing | Validator | `workers/validation.py` | Host-side verification | Model or deterministic checks | Accept, reject, request correction | Result and acceptance criteria | Validation report | Verify file exists | Test logs |
| Audit ledger | Trust accounting and receipts | Compliance and operations logs | Audit system | `audit/` | Cross-cutting | Observability | Append-only where practical | Events from all layers | Traceable record | Who approved a tool call | Correlation ID and event chain |
| Response assembly | Trustee report to beneficiary | Account manager response | Final response builder | `host/response.py` | Host output | Language generation | Must reflect verified results | Plans, results, citations | Human-readable response | “Repository updated successfully” | Response record |
| Amendment | Amendment to trust instrument | Policy or process revision | Versioned architecture change | `governance/amendments/` | Host governance update | System evolution | Requires designated approval | Proposed change | New policy/version | Add new worker authority | Change history |

## Operating chain

```text
Authorized requester
  -> interface
  -> reception
  -> identity and bylaws consultation
  -> directors create plan
  -> managing trustees create work orders
  -> workers request controlled assets
  -> host selects an MCP client connection
  -> MCP client speaks MCP to an MCP server
  -> server uses tools, resources, prompts, files, databases, or provider APIs
  -> result returns to worker
  -> manager validates and records custody
  -> directors assemble outcome
  -> reception returns the response
```

## How to use this matrix

When a new concept appears, add a row and answer all of these questions:

1. What is its trust equivalent?
2. What is its business equivalent?
3. Where does it live in Nephew?
4. Is it code, data, policy, model, protocol, or infrastructure?
5. What authority does it have?
6. What input does it accept?
7. What output must it produce?
8. What evidence must be retained?

That process prevents vague “AI magic” from entering the architecture.