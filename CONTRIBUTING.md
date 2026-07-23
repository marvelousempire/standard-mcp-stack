# Contributing to Standard MCP Stack

## Purpose

Contributions should strengthen one coherent architecture rather than create parallel terminology or competing mental models.

## Before contributing

Read:

1. `docs/architecture-principles.md`
2. `docs/document-standard.md`
3. `docs/glossary.md`
4. `matrices/rosetta-stone.md`
5. `docs/trust-analogy.md`

## Contribution rules

- Preserve the trust architecture as the primary teaching model.
- Preserve the business operating model as the parallel explanatory model.
- Map new concepts into the Rosetta Stone.
- Add truly new vocabulary to the glossary.
- State where the concept belongs in the numbered architecture layers.
- Separate technical capability from policy-backed authority.
- Do not imply that an LLM performs authentication, authorization, or deterministic policy enforcement.
- Do not treat MCP as synonymous with an API, transport, credential, tool, or server implementation.
- Do not duplicate canonical definitions across several documents.
- Link to the canonical source instead.

## Required document sections

Substantive documents should include:

- Purpose
- Responsibilities
- Non-responsibilities
- Inputs
- Outputs
- Authority
- Dependencies
- Trust analogy
- Business analogy
- MCP relationship
- Implementation notes
- Security and audit
- Failure modes
- Common misconceptions
- Key ideas
- Questions to ask
- Future roadmap

## Pull request checklist

- [ ] Vocabulary agrees with the glossary.
- [ ] Trust, business, MCP, AI, and code roles align.
- [ ] Architecture layer is identified.
- [ ] Authority source and limits are explicit.
- [ ] Audit evidence is identified.
- [ ] Security claims are enforced by software, not model behavior.
- [ ] Relevant diagrams and matrices are updated.
- [ ] Examples distinguish client, server, request, credential, transport, and API.
- [ ] Links resolve to canonical documents.

## Design review questions

- Does this addition introduce a new responsibility or merely a new name?
- Who authorizes it?
- What can it access?
- What evidence does it produce?
- Which failure boundary contains it?
- Can it be replaced without changing Nephew's identity?
