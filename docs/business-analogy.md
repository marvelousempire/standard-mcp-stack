# Business Operating Model Analogy

This document runs beside the trust analogy. The trust analogy explains authority, governance, custody, and fiduciary boundaries. The business analogy explains departments, operations, service delivery, and accountability.

The two analogies describe the same software system from different angles.

---

## 1. The company building

The `Nephew/` repository is the company building.

Inside the building are:

- public entrances;
- a reception desk;
- executive leadership;
- department management;
- workers and specialists;
- shared equipment;
- company records;
- communications systems;
- vendor relationships;
- security and audit systems.

The building is not intelligent by itself. Intelligence comes from the people, procedures, models, and systems operating inside it.

---

## 2. Company role map

| Business role | Software component | What it does |
|---|---|---|
| Customer or sponsor | User/requester | Provides the mission or asks for a service |
| Website, CLI, app, phone | Interface | Captures the request |
| Receptionist | `main.py` / intake controller | Identifies, records, validates, and routes requests |
| Corporate identity office | `identity/` | Preserves name, personality, voice, mission, and presentation |
| Corporate charter and policy office | `governance/` | Holds rules, permissions, safety policy, standards, and values |
| Board of directors | `directors/` | Converts missions into strategic plans |
| Operations managers | `managers/` | Creates work orders, assigns workers, controls access, and verifies completion |
| Employees and contractors | `workers/` | Perform bounded tasks |
| Consultants and analysts | `brains/` | Provide reasoning and specialized analysis |
| Records department | `memory/` | Stores operating history and structured state |
| Corporate library | `knowledge/` | Stores authoritative documents and reference material |
| Equipment room | `tools/` | Holds deterministic action capabilities |
| Training department | `skills/` | Holds repeatable procedures and job methods |
| Standard forms office | `prompts/` | Holds templates and structured instructions |
| IT configuration office | `config/` | Holds adjustable system configuration |
| Security office | `security/` | Controls credentials, permissions, approvals, and policy enforcement |
| Communications department | MCP host/client subsystem | Maintains standardized provider connections |
| Vendor service desk | MCP server | Offers approved capabilities |
| Vendor back office | Provider API/database/CLI | Performs vendor-specific work |
| Accounting and compliance | Audit, tracing, receipts | Records decisions, actions, costs, and outcomes |

---

## 3. The restaurant version

The restaurant analogy is especially useful for understanding directors, managers, and workers.

### Guest

The guest states the desired outcome:

> I want the fish entrée, no dairy, with fries, served together.

That is the mission.

### Front-of-house intake

The server or ordering interface records the request and sends it into the operating system.

In Nephew, this is the interface plus reception.

### Executive chef or menu authority

The executive chef defines the menu, quality standards, recipes, and operating philosophy. For a complex custom order, the directing role determines what the finished result should be.

This resembles directors plus governance.

### Expediter

The expo stands at the window and coordinates stations.

The expo does not personally fry every item or cook every fish. The expo:

- reads the ticket;
- sequences the work;
- calls the correct stations;
- checks timing;
- prevents collisions;
- inspects the finished plate;
- sends it to the guest.

This resembles management.

### Stations

Each station performs specialized work:

- grill;
- fry;
- pastry;
- garde manger;
- bar;
- plating.

These are workers.

### Pantry and equipment

Ingredients, knives, ovens, mixers, recipes, and inventory are shared company assets. Workers use them under operating rules; they do not take ownership of them.

These correspond to brains, knowledge, memory, tools, skills, and credentials.

### Vendor ordering

A station may report that ingredients are running low. It does not necessarily call every vendor directly. Management or purchasing checks inventory, budget, approved suppliers, and order authority before using the communications system.

This corresponds to management routing an approved request through an MCP client to a vendor MCP server.

---

## 4. The photo studio version

A photo studio makes asset custody easy to understand.

- Directors decide the campaign and visual objective.
- Managers schedule the shoot, assign personnel, approve locations, and check out equipment.
- Workers include photographers, lighting technicians, stylists, editors, and assistants.
- Brains are creative advisers, image models, and planning models.
- Tools are cameras, lenses, lights, editing software, and storage systems.
- Knowledge includes brand guidelines, shot lists, references, and client briefs.
- Memory includes prior shoots, edit history, approvals, and client preferences.
- Credentials include studio access, software licenses, cloud tokens, and account permissions.

A worker requests a camera through management. The manager checks it out, records custody, limits its use to the job, and checks it back in afterward.

That is the same pattern as temporary scoped access to a tool, credential, model, or server capability.

---

## 5. The software company version

Example mission:

> Update the GitHub repository, run the tests, summarize the changes, and open a draft pull request.

### Reception

Creates request `REQ-1042` and preserves the exact mission.

### Director

Produces the plan:

1. inspect repository state;
2. identify intended changes;
3. modify files;
4. run tests;
5. review the diff;
6. commit on a feature branch;
7. push;
8. open a draft pull request;
9. return links and validation results.

### Manager

Creates controlled work orders:

- repository analyst;
- code worker;
- test worker;
- release worker.

The manager grants each worker only the needed resources.

### Workers

- repository analyst reads repository state;
- code worker changes approved files;
- test worker runs validation;
- release worker uses GitHub capabilities.

### MCP communications

For GitHub operations, the host uses the client instance connected to the GitHub MCP server. That server may itself call GitHub APIs.

### Accounting and compliance

The audit system records:

- request ID;
- plan;
- approvals;
- files changed;
- commands run;
- test results;
- commit SHA;
- pull request;
- failures and retries.

---

## 6. What should remain centralized

A company becomes chaotic when every employee independently stores credentials, negotiates with vendors, invents policies, and creates untracked purchases.

Nephew should centralize:

- governance;
- identity;
- secrets;
- permissions;
- client lifecycle;
- vendor/server registry;
- audit logging;
- approval decisions;
- final response assembly.

Workers should remain specialized and replaceable.

---

## 7. What should remain distributed

The company should allow specialized departments to evolve independently.

Examples:

- coding workers can improve without rewriting finance workers;
- a GitHub server can be replaced without changing the WordPress server;
- a reasoning model can be swapped without replacing Nephew's identity;
- a CLI interface can coexist with a browser GUI and voice interface;
- managers can assign different workers according to task type.

This produces modular growth without losing organizational coherence.

---

## 8. Compact business pipeline

```text
CUSTOMER / SPONSOR
        │
        ▼
WEBSITE / CLI / GUI / VOICE / API
        │
        ▼
RECEPTION DESK
        │
        ▼
BOARD / DIRECTORS
consult charter, policies, identity, skills
        │
        ▼
OPERATIONS MANAGEMENT
create tickets, allocate assets, enforce approvals
        │
        ▼
SPECIALIST WORKERS
        │
        ├── use brains
        ├── consult memory
        ├── retrieve knowledge
        ├── operate tools
        └── request vendor capabilities
                    │
                    ▼
        COMMUNICATIONS DEPARTMENT
       host-managed MCP client instance
                    │
                    ▼
             VENDOR MCP SERVER
                    │
                    ▼
       VENDOR API / DATABASE / SYSTEM
                    │
                    ▼
          RESULT / RECEIPT / EVIDENCE
                    │
                    ▼
WORKER → MANAGER → DIRECTOR → RECEPTION → CUSTOMER
```

The business analogy emphasizes operational control. The trust analogy emphasizes authority and custody. Together they form the mental blueprint for Nephew.
