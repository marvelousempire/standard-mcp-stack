# Stewardship Formula

The Architectural Knowledge Steward uses a deterministic operating formula to convert conversation into durable architecture.

## The formula

```text
RAW EXPRESSION
  → CAPTURE
  → ATOMIZE
  → CLASSIFY
  → NORMALIZE
  → RELATE
  → CHECK AUTHORITY
  → PLACE
  → PLAN
  → IMPLEMENT
  → VERIFY
  → RECORD EVIDENCE
  → REPORT
  → MAINTAIN
```

A compact expression is:

```text
Durable Knowledge =
  Verified(
    Evidence(
      Implemented(
        Authorized(
          Placed(
            Related(
              Normalized(
                Classified(
                  Atomic(Captured Thought)
                )
              )
            )
          )
        )
      )
    )
  )
```

## Stage 1 — Capture

Preserve the original expression before editing it.

Required outputs:

- speaker or source
- timestamp or source reference
- captured wording
- session or document context

Gate: **Can the original expression be reconstructed?**

## Stage 2 — Atomize

Separate compound speech into singular propositions. A feature, purpose, constraint, and implementation request should not be hidden inside one record.

Gate: **Does each record express one primary proposition?**

## Stage 3 — Classify

Assign the canonical record type: idea, intent, purpose, feature, requirement, rule, constraint, analogy, decision, assumption, question, risk, dependency, task, or evidence.

Gate: **Is the record type more precise than a generic note?**

## Stage 4 — Normalize

Rewrite for clarity while preserving the original meaning. Keep the source wording beside the normalized statement.

Gate: **Would the requester recognize the normalized statement as their own intent?**

## Stage 5 — Relate

Search existing records and artifacts. Add parents, related records, dependencies, conflicts, duplicates, and supersession links.

Gate: **Has the steward checked whether this already exists or conflicts with something?**

## Stage 6 — Check authority

Determine who requested the record, whether implementation is authorized, what approvals are needed, and the allowed scope.

Gate: **Is the difference between a suggestion and an authorized change explicit?**

## Stage 7 — Place

Choose the canonical repository, artifact type, path, and reason. Prefer extending coherent canonical artifacts over multiplying files.

Gate: **Can the placement be defended in one sentence?**

## Stage 8 — Plan

Convert approved architecture into work orders. Define affected paths, dependencies, validation, migration, and rollback.

Gate: **Can a worker execute the task without inventing missing authority or requirements?**

## Stage 9 — Implement

Create or update the approved artifacts. Maintain separation among governance, architecture, implementation, testing, and evidence.

Gate: **Does the implementation remain within the approved work order?**

## Stage 10 — Verify

Validate schema, links, consistency, tests, screenshots, diagrams, terminology, and behavior.

Gate: **Is there objective evidence that the artifact says or does what it claims?**

## Stage 11 — Record evidence

Attach commits, pull requests, tests, screenshots, diagrams, logs, receipts, or documents.

Gate: **Can another person independently inspect the result?**

## Stage 12 — Report

Return a clear receipt to the requester: what was heard, what was recorded, what changed, where it lives, what remains open, and what assumptions were made.

Gate: **Can the requester correct the steward without rereading the whole project?**

## Stage 13 — Maintain

Detect drift among intent, documentation, schemas, implementation, screenshots, and deployed behavior. Open explicit work rather than allowing silent rot.

Gate: **Are stale or contradictory artifacts visible as tracked exceptions?**

## Validation scorecard

A record is ready for durable placement only when all applicable checks pass:

| Check | Required question |
|---|---|
| Atomicity | Is there one primary proposition? |
| Provenance | Can the source be reconstructed? |
| Intent fidelity | Was the speaker's meaning preserved? |
| Classification | Is the record type correct? |
| Duplicate check | Was existing architecture searched? |
| Conflict check | Were contradictions surfaced? |
| Authority | Is approval and scope explicit? |
| Placement | Is the canonical path justified? |
| Reversibility | Is rollback or supersession possible? |
| Evidence | Can the outcome be independently inspected? |
| Maintenance | Is future drift detectable? |

## Failure behavior

When a gate fails, the steward must not quietly guess. It shall do one of the following:

- preserve the record as `captured` or `proposed`;
- mark the uncertainty;
- create a decision question;
- request authorization when necessary;
- create a work order for missing validation;
- link a conflict for resolution.

The formula favors an honest incomplete record over a polished false certainty.
