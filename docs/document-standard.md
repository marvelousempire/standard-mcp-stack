# Document Standard

## Purpose

Every substantive chapter in this repository should use a consistent structure so readers can compare components without relearning the page format.

## Required chapter structure

1. **Purpose** — why the component exists.
2. **Responsibilities** — what it must do.
3. **Non-responsibilities** — what it must not do.
4. **Inputs** — information, authority, or assets it may receive.
5. **Outputs** — plans, work orders, results, evidence, or state changes it returns.
6. **Authority** — who grants authority and how narrowly it is scoped.
7. **Dependencies** — services, policies, data, models, or tools it relies upon.
8. **Trust analogy** — the matching trust role or process.
9. **Business analogy** — the matching company or operating role.
10. **MCP relationship** — whether it is part of the host, client, server, or underlying system.
11. **Python implementation** — likely packages, classes, functions, and configuration.
12. **Security and audit** — permission checks, approvals, logs, and receipts.
13. **Failure modes** — foreseeable errors and containment requirements.
14. **Common misconceptions** — likely category mistakes.
15. **Key ideas** — short chapter summary.
16. **Questions to ask** — design review prompts.
17. **Future roadmap** — planned implementation maturity.

## Terminology rules

- Use **host**, **client**, and **server** according to the canonical glossary.
- Do not use **API**, **MCP**, **transport**, and **credential** as synonyms.
- Use **director**, **manager**, and **worker** for responsibilities, not merely for separate language models.
- Use **brain** for a model endpoint or inference adapter.
- Use **memory** for retained operational state and **knowledge** for source material.
- Use **tool** for an action interface and **resource** for retrievable context.
- Use **authority** for permission originating in governance; use **capability** for something a component can technically do.

## Chapter ending template

```markdown
## Key ideas

- ...

## Common misconceptions

- ...

## Questions to ask

- ...

## Future roadmap

- ...
```

## Review checklist

Before merging a document, verify:

- terminology agrees with `docs/glossary.md`
- the trust and business analogies map to the same technical responsibility
- authority and audit requirements are explicit
- examples do not imply that an LLM enforces security
- links point to canonical documents rather than duplicate definitions
