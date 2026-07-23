# Memory Model Standard

Memory is the system's governed continuity layer. It stores selected facts, events, decisions, preferences, and relationships. Memory is not the same as model weights and is not the same as the current context window.

## Trust lens

Memory is the trust's operating history, correspondence, resolutions, receipts, and matter files.

## Business lens

Memory is institutional knowledge: CRM records, case notes, project history, audit events, and prior decisions.

## Memory classes

| Class | Purpose | Typical technology |
|---|---|---|
| Working memory | Current task state | In-process objects, cache |
| Episodic memory | What happened and when | Event store, SQL |
| Semantic memory | Facts and concepts | Vector database, graph, SQL |
| Procedural memory | Reusable methods | Skills, workflows, prompts |
| Preference memory | Stable user/system preferences | Config database |
| Audit memory | Material actions and approvals | Append-only log |

## Write policy

A memory write should declare:

- subject
- fact or event
- source
- confidence
- sensitivity
- retention class
- authorizing rule
- timestamp

## Retrieval policy

Retrieval must preserve provenance. A worker should know whether an answer came from current context, stored memory, a knowledge source, or model weights.