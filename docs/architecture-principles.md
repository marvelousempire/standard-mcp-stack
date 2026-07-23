# Architecture Principles

## Purpose

This document defines the non-negotiable principles of the Standard MCP Stack. These principles apply across governance, host design, planning, orchestration, execution, security, memory, tools, skills, and MCP integrations.

## Core principles

1. **Authority flows downward.** Governance defines authority, directors interpret it, managers delegate it, and workers receive only the authority required for a task.
2. **Evidence flows upward.** Workers return results and receipts to managers; managers return verified outcomes to directors; directors return a coherent response to reception and the requester.
3. **Governance does not execute work.** Governance defines identity, mission, rules, permissions, and limits. It does not run tools or modify systems directly.
4. **Directors plan; managers coordinate; workers execute.** These roles must remain distinguishable in code and behavior.
5. **Workers do not bypass management.** Workers request assets, credentials, tools, and external access through management-controlled channels.
6. **Identity is persistent; brains are replaceable.** Nephew remains Nephew even when models, providers, or inference engines change.
7. **Credentials are controlled assets.** They are never treated as worker-owned data and must remain scoped, revocable, and auditable.
8. **Every external action is reconstructable.** Requests, approvals, execution, outputs, errors, and receipts should be traceable.
9. **MCP is a protocol boundary, not an authority source.** A server may advertise a capability, but the host decides whether it may be used.
10. **Capability discovery is not permission.** Knowing a tool exists is separate from having authority to invoke it.
11. **Context is minimized by default.** Each worker, model, and server receives only the context required for the current task.
12. **Assets are shared services, not worker possessions.** Brains, memory, knowledge, tools, and skills are controlled resources.
13. **Deterministic operations should remain deterministic.** Use ordinary code for routing, validation, arithmetic, state transitions, and policy checks whenever possible.
14. **Models advise and reason; software enforces.** Language models may recommend actions, but code must enforce permissions and invariants.
15. **Boundaries must be visible.** Every component should declare its inputs, outputs, authority, dependencies, and audit obligations.
16. **Failure should be contained.** A failing server, tool, worker, or brain must not collapse unrelated parts of the host.
17. **The host owns the user relationship.** Servers do not independently control the conversation, identity, approvals, or cross-server context.
18. **One logical client session connects to one server.** A host may manage many client sessions, but each session has a clear server boundary.
19. **Local and remote services are governed consistently.** A local file server can be as sensitive as a remote financial API.
20. **The mental model and code model must agree.** Trust, business, MCP, AI, and Python descriptions should map to the same responsibilities.

## Trust interpretation

The trust instrument establishes purpose and authority. Directors interpret the instrument. Managing trustees issue bounded work orders. Contractors perform scoped work. Trust assets remain in custody. Every material transaction produces records.

## Business interpretation

The company charter and policies define the enterprise. Directors set plans. Managers assign work and control resources. Employees and contractors execute. Finance, IT, legal, data, and equipment remain governed shared services.

## Implementation consequences

Every major package or document should state:

- purpose
- responsibilities
- inputs
- outputs
- authority
- dependencies
- trust analogy
- business analogy
- implementation notes
- audit evidence
- common misconceptions

## Questions to ask

- Who granted this component authority?
- What exact input may it receive?
- What assets may it use?
- What evidence must it return?
- Can its behavior be reconstructed later?
- What happens if it fails or is replaced?
