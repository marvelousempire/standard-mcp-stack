# Repository Integration Standard

This document defines how a repository adopts the Architectural Knowledge Steward skill.

## Required repository footprint

```text
.brain/
  nephew.md
  identity.md
  operating-rules.md

architecture/
  principles.md
  layers.md
  decisions/

knowledge/
  records/
  registries/

schemas/
  idea-record.schema.json

evidence/
  screenshots/
  diagrams/
  receipts/

skills/
  architectural-knowledge-steward/

README.md
ROADMAP.md
```

A repository may adapt the names, but it must preserve the responsibilities.

## `.brain/` purpose

The `.brain/` directory is the repository-facing executive profile. It does not contain model weights. It tells any compatible AI host how the repository should be understood and governed.

- `nephew.md` defines the Head of Household role.
- `identity.md` defines repository identity, mission, audience, tone, and boundaries.
- `operating-rules.md` defines local constraints, approval rules, and evidence requirements.

## Records registry

Atomic records should be stored in a searchable registry, initially as JSON or YAML files and later optionally in a database.

Recommended pattern:

```text
knowledge/records/2026/
  AKS-2026-0001.json
  AKS-2026-0002.json
```

Each record must validate against the canonical schema.

## Decision records

Use an architectural decision record when a choice has meaningful alternatives, consequences, or migration impact.

```text
architecture/decisions/
  ADR-0001-use-one-client-session-per-server.md
```

Each decision should include context, options, decision, consequences, authority, evidence, and supersession rules.

## Issue and work-order integration

Approved but incomplete implementation should become a bounded issue or work order. The issue must link back to the atomic record and define:

- authorized outcome;
- included and excluded scope;
- affected paths;
- dependencies;
- validation;
- evidence required;
- rollback or supersession approach.

## README integration

The README should expose:

1. Identity and mission
2. Architecture overview
3. Trust and business mental model when applicable
4. Quick start
5. Visual tour for GUI projects
6. Documentation map
7. Current status
8. Live preview or deployment information
9. Governance and contribution links

## Makefile integration

A repository may provide a standard operator panel:

```makefile
help:
	@echo "validate-records  Validate architectural records"
	@echo "docs              Build documentation"
	@echo "screenshots       Capture GUI evidence"
	@echo "preview           Start local preview"
	@echo "test              Run project tests"

validate-records:
	python scripts/validate_records.py

screenshots:
	npm run screenshots

preview:
	npm run dev
```

The Makefile launches workflows. It does not become the repository's intelligence or governance layer.

## Steward operating cycle

For every substantive interaction:

1. Capture the request.
2. Extract atomic records.
3. Compare against existing records and architecture.
4. Present or record conflicts and assumptions.
5. Determine authorization.
6. Update canonical artifacts.
7. Create work orders for remaining implementation.
8. Validate code, schemas, docs, diagrams, and screenshots.
9. Record evidence.
10. Return a receipt to the requester.

## Receipt format

```markdown
## Stewardship Receipt

### Heard
- Atomic intent or idea

### Recorded
- Record IDs and canonical locations

### Changed
- Files, schemas, diagrams, issues, or code

### Evidence
- Commit, tests, screenshots, or links

### Open
- Pending decisions, missing authority, risks, or follow-up work

### Assumptions
- Any interpretation that was necessary
```

## Portability

The skill must remain model-independent. The repository may swap Qwen, Llama, DeepSeek, GLM, a hosted model, or another reasoning system without rewriting its identity, governance, records, or schema.

Nephew is the stable Head of Household identity. Models are replaceable advisers or brains operating within that governed environment.
