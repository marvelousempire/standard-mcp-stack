# Nephew Governance and Bylaws Model

This document defines the software equivalent of the trust instrument, bylaws, delegations, and administrative handbook that directors and managers consult before acting.

It is an architecture template, not a legal trust instrument.

---

## Article I — Identity

The governance package should define:

- system name;
- mission;
- owner or beneficiary relationship;
- operating values;
- personality and tone;
- visual and semantic identity;
- supported languages;
- prohibited impersonations;
- version and effective date.

Suggested files:

```text
governance/
├── identity.yaml
├── mission.md
├── values.md
├── personality.md
├── aesthetics.yaml
└── versions.yaml
```

A replacement model must not silently replace this identity.

---

## Article II — Purpose and powers

Define what Nephew exists to do.

Examples:

- research and explain;
- manage documents and knowledge;
- coordinate software-development work;
- operate approved tools;
- assist with media workflows;
- communicate with approved systems;
- maintain records and project continuity.

Also define powers Nephew does not possess without explicit approval.

Examples:

- spending money;
- publishing publicly;
- deleting records;
- changing credentials;
- executing destructive commands;
- making legal commitments;
- exposing confidential information;
- contacting new external parties.

---

## Article III — Beneficiaries and authorized requesters

The system should distinguish:

- owner/primary beneficiary;
- delegated users;
- household or team members;
- external partners;
- service accounts;
- anonymous or untrusted callers.

Each requester class should have:

- authentication requirements;
- permitted interfaces;
- request categories;
- spending or execution limits;
- disclosure limits;
- approval requirements;
- audit retention rules.

---

## Article IV — Directors

Directors interpret missions under governance.

Directors may:

- classify missions;
- identify applicable policies;
- decompose outcomes into workstreams;
- estimate risk and resource needs;
- propose workers, brains, tools, and servers;
- identify approval gates;
- define completion evidence.

Directors may not bypass management to grant uncontrolled access to workers.

A director plan should contain:

```yaml
plan_id: PLAN-0001
request_id: REQ-0001
objective: "..."
applicable_policies: []
assumptions: []
workstreams: []
required_assets: []
risk_level: low|moderate|high|critical
approval_gates: []
completion_evidence: []
stop_conditions: []
```

---

## Article V — Managers

Managers administer plans and assets.

Managers may:

- create work orders;
- select registered workers;
- grant temporary scoped access;
- choose approved server connections;
- enforce budgets and limits;
- request human approval;
- pause, cancel, retry, or reassign work;
- reconcile worker results;
- record receipts and exceptions.

Managers must apply least privilege.

A management grant should specify:

```yaml
grant_id: GRANT-0001
worker_id: repository_worker
request_id: REQ-0001
resources:
  - github:repository:read
  - github:pull_request:draft
constraints:
  repository: marvelousempire/example
  branch_prefix: agent/
  expires_at: timestamp
approval:
  required: true
  approval_id: APPROVAL-0007
```

---

## Article VI — Workers

Workers perform defined jobs.

Every worker should have a charter:

- worker identity;
- purpose;
- accepted task types;
- required inputs;
- permitted assets;
- forbidden actions;
- expected outputs;
- validation procedure;
- escalation path;
- timeout and retry policy.

Workers must not:

- expand their own authority;
- retrieve unrelated secrets;
- contact unapproved servers;
- conceal errors;
- treat model suggestions as authorization;
- bypass required approvals.

---

## Article VII — Asset custody

Shared assets remain under organizational custody.

### Brains

Record:

- provider/model identifier;
- modality;
- context window;
- cost class;
- data handling policy;
- approved roles;
- evaluation results;
- fallback order.

### Memory and knowledge

Record:

- source owner;
- classification;
- retention;
- allowed operations;
- citation requirements;
- synchronization policy;
- deletion authority.

### Tools and MCP servers

Record:

- capability owner;
- allowed workers;
- credential reference;
- risk class;
- required approvals;
- sandbox status;
- rate and spending limits;
- audit fields;
- emergency disable switch.

---

## Article VIII — Communications and MCP

The host is the communications authority.

The host must:

- create isolated client instances for configured servers;
- keep server sessions separate;
- disclose only necessary context;
- negotiate protocol and capabilities;
- verify authorization before capability use;
- protect credentials from models and workers where possible;
- validate server responses;
- preserve request correlation and audit evidence.

A server registry entry should include:

```yaml
server_id: github
trust_role: approved_vendor_service_desk
transport:
  type: streamable_http
  endpoint: "secret-or-config-reference"
authentication:
  method: oauth
  credential_ref: secrets/github
allowed_capabilities:
  tools:
    - repository.read
    - pull_request.create_draft
denied_capabilities:
  - repository.delete
approval_policy:
  read: automatic
  write: required
risk_class: high
```

---

## Article IX — Approval schedule

Suggested approval levels:

| Level | Description | Example |
|---|---|---|
| A0 | Read-only, low sensitivity | Read public documentation |
| A1 | Internal reversible operation | Create a local draft file |
| A2 | External reversible operation | Create a GitHub draft PR |
| A3 | External consequential operation | Send, publish, purchase, deploy |
| A4 | Destructive or privileged operation | Delete, rotate secrets, alter production access |

Governance should define who may approve each level and whether approval expires.

---

## Article X — Disclosure and privacy

Before releasing information, the system should evaluate:

- requester identity;
- purpose of disclosure;
- source classification;
- minimum necessary fields;
- redaction requirements;
- destination security;
- consent or legal authority;
- retention and audit requirements.

An MCP server must not automatically receive full conversation history or unrelated records.

---

## Article XI — Records and accounting

Every mission should produce a chain of custody:

```text
request → intake → policy decision → plan → work orders → access grants
→ capability calls → results → approvals → final delivery → retention
```

Minimum audit fields:

- correlation ID;
- requester;
- receiving interface;
- policy and governance versions;
- director plan;
- manager assignments;
- worker identity;
- model identity;
- tool/server identity;
- permissions and approvals;
- requests and responses;
- changes and side effects;
- validation results;
- final recipient;
- timestamps;
- errors and exceptions.

---

## Article XII — Amendments

Changes to identity, governance, permissions, or risk classifications should:

1. be proposed;
2. include rationale and impact;
3. receive the required approval;
4. be versioned;
5. have an effective date;
6. preserve prior versions for audit;
7. trigger re-evaluation of affected workers, skills, tools, and server connections.

This prevents silent personality drift, permission creep, and governance loss when the underlying models or software change.
