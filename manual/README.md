# AI Governance Knowledge Base

Structured reference notes distilled from *The AI Governance Practitioner's Manual* (Noah M. Kenney,
Digital 520, 1st ed., 2026) — reorganized here as a navigable Markdown knowledge base rather than a
verbatim copy of the source text. Facts, definitions, obligation tables, and the organizing frameworks are
retained; narrative prose has been condensed and paraphrased. The source is a copyrighted commercial
work ("© 2026 Noah M. Kenney. All rights reserved."); this knowledge base is for internal/personal
reference use, not redistribution. Always verify current statutory text and regulatory guidance before
relying on any obligation, threshold, or penalty figure noted here — coverage reflects the source's
stated currency of **August 2026**.

## How this is organized

The source manual is organized **by audience** (a reading-path model), but this knowledge base is
organized **by subject area** for lookup, since that's more useful once the material is extracted from
its original chapter sequence. Cross-references to the original chapter numbers are kept in each file's
front line so you can trace back.

```
manual/
├── 00-foundation/          Part I — the discipline, the 5-layer Stack, ethics (Ch. 1-3)
├── 01-executives/          Part II — business case, org design, roadmap, board prep (Ch. 4-7)
├── 02-legal-eu/            EU AI Act, GDPR, EU digital regulation suite (Ch. 8-10)
├── 03-legal-us-federal/    US federal privacy, comms, civil rights, infrastructure, sector regulators (Ch. 11-15)
├── 04-legal-us-state/      US state privacy, biometric/cyber/breach, state AI statutes (Ch. 16-18)
├── 05-legal-international/ UK, Americas, Asia-Pacific (Ch. 19-20)
└── reference/               Cross-cutting quick-reference material
```

## The core organizing idea: the AI Governance Stack

Every chapter in the source maps its subject onto a single five-layer framework. See
[`reference/stack-quick-reference.md`](reference/stack-quick-reference.md) for the full spec. In brief:

| Layer | Name | Question | Default owner |
|---|---|---|---|
| 1 | Data Governance | Is the data safe to learn from? | Data teams |
| 2 | Model Governance | Is the model sound, fair, non-biased? | ML / data science |
| 3 | System Integration | Is it wired into the business safely? | Engineering |
| 4 | Control & Monitoring | Are we watching it in production? | SRE / risk operations |
| 5 | Audit & Evidence | Can we prove all of the above? | Compliance / legal |

**Cascading failure principle:** failures propagate *upward* through the layers and must be fixed at
their *source* layer — a Layer 1 (data) defect patched at Layer 3 (integration) is compensation, not
correction.

## Reference material

- [`reference/stack-quick-reference.md`](reference/stack-quick-reference.md) — full 5-layer spec, requirement IDs (DG-1…AE-5), maturity model
- [`reference/penalty-comparison.md`](reference/penalty-comparison.md) — consolidated penalty/threshold table across every regime covered
- [`reference/glossary.md`](reference/glossary.md) — recurring terms and acronyms

## Reading paths (condensed from source Ch. "Reading Paths by Role")

- **Executives / governance leaders:** `00-foundation/01…` → `01-executives/*`
- **Lawyers / counsel:** `00-foundation/01-02` → `02-legal-eu/*` → `03-legal-us-federal/*` → `04-legal-us-state/*`
- **Engineers / data scientists:** `00-foundation/02-ai-governance-stack.md` (Layers 1-3 in detail)
- **Security professionals:** `00-foundation/02-ai-governance-stack.md` (Layers 3-4) → `03-legal-us-federal/14-critical-infrastructure.md`
- **Compliance / audit:** `00-foundation/*` → `01-executives/06-governance-roadmap.md` → domain-specific legal files

## Source coverage

The source manual has 46 chapters across 9 parts plus 10 appendices; **this knowledge base currently
covers Chapters 1–20 (Parts I, II, and III through the Asia-Pacific section)**, which is the portion
supplied. Parts IV–IX (privacy engineering, technical implementation, security frameworks, compliance
program build-out, domain playbooks for healthcare/finance/government/GenAI/agents, and the reference
appendices) are not yet included — add them here as they become available.
