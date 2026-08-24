# AI Governance Knowledge Base — Index

Structured reference notes on AI governance, law, and compliance. This README is an **index only** —
each row below tells you which file to open for a given topic, so a retrieval pass can jump straight to
the right file instead of loading this whole knowledge base into context. Coverage reflects
legal/regulatory developments through **August 2026**; verify current statutory text before relying on
any obligation, threshold, or penalty figure.

## The AI Governance Stack (used as a tag throughout the index below)

Five layers every file maps its subject onto — full spec in
[`reference/stack-quick-reference.md`](reference/stack-quick-reference.md):

| Layer | Name | Question |
|---|---|---|
| L1 | Data Governance | Is the data safe to learn from? |
| L2 | Model Governance | Is the model sound, fair, non-biased? |
| L3 | System Integration | Is it wired into the business safely? |
| L4 | Control & Monitoring | Are we watching it in production? |
| L5 | Audit & Evidence | Can we prove all of the above? |

## File index

| File | Domain / jurisdiction | Keywords |
|---|---|---|
| [`reference/stack-quick-reference.md`](reference/stack-quick-reference.md) | Cross-cutting framework | 5-layer Stack, DG-1…AE-5 requirement IDs, ownership model, maturity model, credit-decision walkthrough |
| [`reference/penalty-comparison.md`](reference/penalty-comparison.md) | Cross-cutting, all jurisdictions | penalty tables, fine thresholds, private right of action, cure periods |
| [`reference/glossary.md`](reference/glossary.md) | Cross-cutting | acronyms, defined terms, statutory instrument list by jurisdiction |
| [`00-foundation/01-discipline-of-ai-governance.md`](00-foundation/01-discipline-of-ai-governance.md) | Foundational | AI definitions, OECD/EU/NIST definitions, risk classification, failure propagation, business case intro, ROI |
| [`00-foundation/02-ai-governance-stack.md`](00-foundation/02-ai-governance-stack.md) | Foundational | Stack rationale, layer verification criteria, failure modes, maturity transitions |
| [`00-foundation/03-ethics-and-professional-responsibility.md`](00-foundation/03-ethics-and-professional-responsibility.md) | Foundational | ethics frameworks, consequentialism, deontology, ACM Code of Ethics, NIST AI RMF, ISO 42001, governance culture |
| [`01-executives/04-business-case-and-roi.md`](01-executives/04-business-case-and-roi.md) | Executive/org | ROI model, compliance cliff, cost of inaction, budget justification |
| [`01-executives/05-building-the-governance-function.md`](01-executives/05-building-the-governance-function.md) | Executive/org | Chief AI Officer, committee design, org structure, seven core policies, risk classification |
| [`01-executives/06-governance-roadmap.md`](01-executives/06-governance-roadmap.md) | Executive/org | 12-month build plan, three-phase roadmap, budget/staffing rules, incident response readiness |
| [`01-executives/07-evolving-landscape-and-board-prep.md`](01-executives/07-evolving-landscape-and-board-prep.md) | Executive/org | board questions, international convergence, ISO 42001, AI safety institutes, frontier model governance |
| [`02-legal-eu/08-eu-ai-act.md`](02-legal-eu/08-eu-ai-act.md) | EU | EU AI Act, Regulation 2024/1689, risk pyramid, Art. 5 prohibited practices, GPAI, Annex III, Annex IV, conformity assessment |
| [`02-legal-eu/09-gdpr.md`](02-legal-eu/09-gdpr.md) | EU | GDPR, Art. 22 automated decision-making, DPIA, lawful basis, Schrems II, cross-border transfer, data subject rights |
| [`02-legal-eu/10-eu-digital-regulation-suite.md`](02-legal-eu/10-eu-digital-regulation-suite.md) | EU | DSA, DMA, NIS2, DORA, Data Act, Cyber Resilience Act, Product Liability Directive, EHDS |
| [`03-legal-us-federal/11-us-federal-privacy-consumer-protection.md`](03-legal-us-federal/11-us-federal-privacy-consumer-protection.md) | US federal | FTC Act §5, HIPAA, GLBA, FERPA, COPPA, FCRA, ECOA, TCPA, CFAA, Privacy Act 1974, FISMA |
| [`03-legal-us-federal/12-us-communications-intermediary-surveillance.md`](03-legal-us-federal/12-us-communications-intermediary-surveillance.md) | US federal | VPPA, §230 CDA, ECPA, Wiretap Act, CLOUD Act, EU-US Data Privacy Framework, FISA §702, CAN-SPAM, DPPA |
| [`03-legal-us-federal/13-civil-rights-and-employment.md`](03-legal-us-federal/13-civil-rights-and-employment.md) | US federal | Title VII, ADEA, GINA, disparate impact, Fair Housing Act, ADA Title III, NLRA, hiring algorithms |
| [`03-legal-us-federal/14-critical-infrastructure-cybersecurity.md`](03-legal-us-federal/14-critical-infrastructure-cybersecurity.md) | US federal | CIRCIA, NERC CIP, TSA directives, NRC, FAA DO-178C, FERC Order 901, DOD Responsible AI, OT security |
| [`03-legal-us-federal/15-sector-specific-federal-regulators.md`](03-legal-us-federal/15-sector-specific-federal-regulators.md) | US federal | FDA SaMD, SR 11-7 model risk management, CFPB circulars, EEOC ADA guidance, ACA §1557, NAIC, SEC AI-washing |
| [`04-legal-us-state/16-comprehensive-state-privacy-laws.md`](04-legal-us-state/16-comprehensive-state-privacy-laws.md) | US state | CCPA/CPRA, VCDPA, CPA, all 20 state comprehensive privacy laws, ADMT, profiling opt-outs, penalties/cure periods |
| [`04-legal-us-state/17-state-biometric-cyber-breach.md`](04-legal-us-state/17-state-biometric-cyber-breach.md) | US state | BIPA, CUBI, MHMDA, NY SHIELD Act, NY DFS Part 500, Mass. 201 CMR 17, breach notification, biometric consent |
| [`04-legal-us-state/18-state-ai-statutes.md`](04-legal-us-state/18-state-ai-statutes.md) | US state | Colorado AI Act, Texas TRAIGA, California AB 2013/SB 942/SB 53, NYC Local Law 144, Illinois HB 3773, ELVIS Act, Utah AI Policy Act |
| [`05-legal-international/19-uk-and-americas.md`](05-legal-international/19-uk-and-americas.md) | UK, Canada, Latin America | UK GDPR, Online Safety Act, Quebec Law 25, PIPEDA, LGPD, Chile Law 21.719, Colombia, Peru, Uruguay, Panama, Ecuador |
| [`05-legal-international/20-asia-pacific.md`](05-legal-international/20-asia-pacific.md) | Asia-Pacific | China PIPL/DSL/CSL, Generative AI Measures, Japan APPI, South Korea PIPA/AI Basic Act, Singapore PDPA/AI Verify, India DPDP Act |

## Reading paths by role

- **Executives:** `00-foundation/01-discipline-of-ai-governance.md` → `01-executives/*`
- **Lawyers/counsel:** `00-foundation/01-02` → `02-legal-eu/*` → `03-legal-us-federal/*` → `04-legal-us-state/*` → `05-legal-international/*`
- **Engineers/data scientists:** `00-foundation/02-ai-governance-stack.md`
- **Security professionals:** `00-foundation/02-ai-governance-stack.md` → `03-legal-us-federal/14-critical-infrastructure-cybersecurity.md`
- **Compliance/audit:** `00-foundation/*` → `01-executives/06-governance-roadmap.md` → domain-specific legal files

## Coverage gaps

Within Asia-Pacific ([`20-asia-pacific.md`](05-legal-international/20-asia-pacific.md)), only China,
Japan, South Korea, Singapore, and India have full narrative treatment — Australia, New Zealand,
Vietnam, Indonesia, Thailand, the Philippines, Malaysia, Hong Kong, and Taiwan are summary-table only.
Not yet covered anywhere in this knowledge base: privacy engineering, technical implementation, security
frameworks, compliance program build-out, and domain-specific playbooks (healthcare, finance,
government, generative AI, agents).
