# Master MCP Matrix

This matrix is the canonical side-by-side map for the Standard MCP Stack.

| Layer | Client/Host-side component | Purpose | Typical parameters or contents | Server-side counterpart | Purpose | Trust/company analogy | Failure when missing |
|---|---|---|---|---|---|---|---|
| Application | Host identity | Defines which application is operating | name, version, owner, environment | Server identity | Identifies capability provider | Trust name and vendor identity | Parties cannot be reliably identified |
| Governance | Identity profile | Preserves mission and personality | mission, tone, values, representation | Service policy | Defines provider operating policy | Trust declaration and vendor policy | Inconsistent behavior |
| Governance | Bylaws/rules | Constrains plans and actions | allow/deny rules, approval thresholds | Server policy | Constrains exposed operations | Trust instrument and vendor terms | Unsafe or unauthorized actions |
| Application | Interface | Receives user or system requests | CLI, GUI, voice, inbound API | Not applicable | Server is normally not the user interface | Front desk or mail room | No entry point |
| Application | Reception/controller | Normalizes and routes incoming work | request ID, actor, payload, channel | Protocol listener | Accepts server connections/messages | Receptionist and receiving desk | Requests are lost or malformed |
| Planning | Director | Creates objective and plan | goals, constraints, steps, success criteria | Not required by MCP | A server can have internal planning but MCP does not require it | Board of directors | No coherent plan |
| Coordination | Manager | Assigns workers and controls access | routing, budgets, approvals, retries | Request router | Maps protocol methods to handlers | Managing trustee and service-desk dispatcher | Work reaches wrong capability |
| Execution | Worker | Performs scoped task | task, context, permitted assets, deadline | Tool/resource implementation | Performs operation or retrieves content | Contractor and vendor specialist | No work is performed |
| Models | Brain adapter | Invokes a selected model | provider, model ID, temperature, context limit | Optional model integration | Server may use a model internally | Professional adviser | Weak or absent reasoning |
| MCP | Client instance | Maintains one logical server connection | server ID, transport, lifecycle state | Server instance | Provides MCP capabilities | Trust communications clerk and vendor desk | No MCP communication |
| MCP | Protocol engine | Creates and interprets MCP messages | protocol version, JSON-RPC methods, IDs | Protocol engine | Parses and generates MCP messages | Shared forms and language | Ends cannot understand each other |
| Discovery | Initialization handler | Negotiates protocol and features | protocol version, client info, capabilities | Initialization handler | Negotiates server features | Opening conference and terms | Incompatible assumptions |
| Discovery | Capability discovery | Learns what server offers | tools, resources, prompts, changes | Capability registries | Publishes available capabilities | Vendor catalog | Host cannot know what is available |
| Transport | Transport adapter | Carries MCP messages | stdio, Streamable HTTP, headers, timeout | Transport listener | Receives messages over selected transport | Phone line, courier route, or private road | No connection path |
| Addressing | Server registry | Stores server connection definitions | name, command/URL, transport, environment | Bind/listen config | Defines where server accepts connections | Address book and vendor location | Client cannot find server |
| Session | Connection manager | Opens, monitors, and closes connections | state, timeout, keepalive, reconnect | Session manager | Tracks connected clients and state | Communications switchboard | Unstable or leaked sessions |
| Messaging | Request builder | Builds valid method calls | method, params, request ID, metadata | Request parser | Validates incoming request | Completed requisition form | Invalid requests |
| Messaging | Notification handler | Sends/receives messages without replies | progress, cancellation, list changed | Notification publisher | Emits server-side events | Status updates | Stale state and poor coordination |
| Messaging | Response parser | Converts replies into host objects | result, error, request correlation | Response builder | Produces valid MCP result/error | Receiving clerk and vendor receipt | Results cannot be used |
| Capabilities | Tool caller | Invokes an advertised tool | tool name, arguments | Tool registry | Lists and dispatches executable operations | Work-order request and service catalog | Actions unavailable |
| Capabilities | Resource reader | Reads advertised context | URI, range, metadata | Resource registry | Exposes readable data | Records request and archive room | Knowledge unavailable |
| Capabilities | Prompt consumer | Retrieves reusable prompt templates | prompt name, arguments | Prompt registry | Publishes prompt templates | Approved form/templates library | Reusable guidance unavailable |
| Capabilities | Sampling handler | Allows server-requested model generation when supported | model preferences, messages, limits | Sampling requester | Requests host model assistance | Vendor asks trust adviser for analysis | Server cannot delegate reasoning |
| Capabilities | Roots handler | Declares filesystem/workspace boundaries when supported | allowed root URIs | Roots consumer | Restricts operations to declared roots | Authorized jobsite boundaries | Excessive or missing file access |
| Security | Actor identity | Identifies user/service initiating work | user ID, tenant, role, session | Client identity | Identifies connected host/client | Beneficiary or authorized requester | No accountability |
| Security | Credential provider | Supplies tokens without exposing them to models | token reference, secret manager path, expiry | Authentication handler | Verifies identity proof | Membership card and credential desk | Access denied or secrets leaked |
| Security | Authorization policy | Determines allowed capabilities and scope | roles, scopes, resource rules, approvals | Authorization enforcement | Enforces access per operation | Trustee approval and vendor permissions | Privilege escalation |
| Security | Consent/approval gate | Requires human approval for sensitive calls | risk level, approval record, expiration | Optional confirmation policy | May reject or require confirmation | Trustee signature | High-impact work executes unchecked |
| Security | Secret store | Protects API keys and credentials | keychain, vault, environment injection | Server secret store | Protects provider credentials | Locked safe | Credential compromise |
| Integration | Provider adapter | Usually not needed on client when MCP is used | optional direct fallback | API/SDK adapter | Calls underlying provider | Vendor employee using internal register | Server cannot fulfill request |
| Integration | Local adapter | Invokes local process/server | executable, args, environment | Local implementation | Uses files, Git, shell, DB, hardware | On-site contractor and equipment | Local systems unavailable |
| Data | Memory service | Supplies prior state and preferences | SQL, vector DB, conversation store | Optional server storage | Stores server state/cache | Trust records | No continuity |
| Data | Knowledge service | Supplies evidence and documents | NAS, Obsidian, WordPress, GitHub | Resource provider | Publishes selected knowledge | Trust archive and vendor catalog | Unsupported answers |
| Operations | Timeout policy | Stops stalled requests | connect/read/total timeout | Execution timeout | Stops long-running handler | Work-order deadline | Hung work |
| Operations | Retry policy | Retries safe transient failures | attempts, backoff, retryable errors | Idempotency support | Prevents duplicate effects | Resubmission rules and receipt number | Duplicate or abandoned work |
| Operations | Cancellation | Stops no-longer-needed work | request ID, cancellation token | Cancellation handler | Attempts to stop execution | Cancelled work order | Wasted resources |
| Operations | Rate limiting | Controls demand | calls/minute, concurrency, quotas | Rate limiter | Protects provider | Purchasing limits | Overload or surprise costs |
| Operations | Budget controls | Limits tokens, money, and compute | token cap, dollar cap, GPU time | Usage accounting | Reports/limits consumption | Trustee spending authority | Unbounded spending |
| Reliability | Error manager | Classifies and handles failures | error code, retryability, user message | Error mapper | Converts implementation failures to protocol errors | Exception report | Confusing silent failures |
| Reliability | Health monitor | Tracks server availability | heartbeat, latency, failure count | Health endpoint/state | Reports readiness | Vendor status board | Calls go to unhealthy provider |
| Observability | Logger | Records connection and call events | timestamp, request ID, server, method | Server logger | Records handling and provider calls | Communications logbook | No traceability |
| Observability | Audit trail | Records security-relevant actions | actor, approval, arguments hash, result | Audit events | Records executed effects | Trust ledger and vendor receipt | No defensible history |
| Observability | Metrics | Measures performance and use | latency, success rate, tokens, costs | Server metrics | Measures handler/provider behavior | Operations dashboard | Cannot improve or diagnose |
| Configuration | Client config | Declares connected servers | server name, command/URL, transport, env refs | Server config | Declares listeners and integrations | Vendor directory and service setup | Misconfiguration |
| Configuration | Feature flags | Enables staged behavior | server enabled, experimental methods | Feature flags | Enables capabilities | Board-authorized pilot | Risky all-at-once rollout |
| Testing | Mock server | Tests client without real provider | canned tools/resources/errors | Test client | Tests server methods | Training simulation | Unsafe production-only testing |
| Testing | Contract tests | Verifies expected protocol behavior | initialization, listing, calls, errors | Contract tests | Verifies server compliance | Standard inspection checklist | Hidden incompatibilities |
| Lifecycle | Startup | Loads governance and creates clients | configs, secret refs, server definitions | Startup | Registers capabilities and begins listening | Opening the office | Stack never becomes ready |
| Lifecycle | Shutdown | Closes clients and flushes logs | cancellation, disconnect, persistence | Shutdown | Stops listeners and work safely | Closing and securing office | Corruption or leaked processes |

## Important cardinality

```text
One host
  -> can contain many client instances
  -> each client instance connects to one server
  -> each server can expose many tools, resources, and prompts
  -> each server can use zero, one, or many underlying provider systems
```

A reusable client library may create many client instances. Therefore, people sometimes casually say “one client talks to many servers,” but architecturally this is normally a host managing a separate client connection for each server.
