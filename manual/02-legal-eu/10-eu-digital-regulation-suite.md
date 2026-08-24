# Ch. 10 — The EU Digital Regulation Suite

*Audience: lawyers mapping the full EU obligation set beyond the AI Act (Ch. 8) and GDPR (Ch. 9).
13 instruments that rarely mention "artificial intelligence" in their scope clauses but all reach AI
systems anyway — an AI-as-a-service offering is simultaneously a data-processing service (Data Act), a
supply-chain dependency (NIS2), an ICT third-party service (DORA, financial customers), a product with
digital elements (CRA, when embedded), and a product for strict-liability purposes (revised PLD).*

## Suite map (penalties as stated in source, verify currency)

| Instrument | Regulates | Key dates | Max penalty |
|---|---|---|---|
| DSA (Reg. 2022/2065) | Online intermediaries, platforms, VLOPs/VLOSEs | Aug 2023 (VLOPs) / Feb 2024 (general) | 6% worldwide turnover |
| DMA (Reg. 2022/1925) | Designated gatekeepers | Gatekeeper obligations Mar 2024 | 10% (20% repeat) |
| NIS2 (Dir. 2022/2555) | Cybersecurity, 18 sectors | Transposition Oct 2024 | €10M or 2% (essential entities) |
| NIS2 Implementing Reg. (2024/2690) | Digital service provider technical controls | Oct 2024 | Per NIS2 |
| DORA (Reg. 2022/2554) | Financial-sector ICT resilience & vendors | Jan 2025 | 1% avg. daily worldwide turnover (critical ICT providers) |
| Data Act (Reg. 2023/2854) | Connected-product data, switching, cloud/AI portability | Sep 2025 | Member-state penalties |
| Data Governance Act (Reg. 2022/868) | Public-data reuse, intermediaries, altruism | Sep 2023 | Member-state penalties |
| ePrivacy Directive (2002/58/EC) | Cookies, e-marketing, comms confidentiality | 2002, amended | Member-state; GDPR tiers on overlap |
| Cyber Resilience Act (Reg. 2024/2847) | Products with digital elements | Reporting Sep 2026; main obligations Dec 2027 | €15M or 2.5% |
| Revised PLD (Dir. 2024/2853) + AILD (pending) | Product liability for software/AI | PLD in force Dec 2024; transposition Dec 2026 | Civil damages |
| eIDAS 2.0 (Reg. 2024/1183) | EU Digital Identity Wallet, trust services | May 2024; wallets by 2026 | National penalties |
| Cybersecurity Act (Reg. 2019/881) | ENISA, EU security certification | Jun 2019 | Certification/market-access consequences |
| EHDS (Reg. 2025/327) | Health data primary/secondary use | Mar 2025; phased to 2029 | National, GDPR/AI-Act aligned |
| GPAI Code of Practice | AI Act Art. 51-55 operationalization | Published 2025 | Via AI Act: €15M or 3% |

**Practitioner note:** run conflicts/overlaps deliberately, not instrument-by-instrument. A single AI
incident can trigger NIS2 (24hr), DORA (financial entities), CRA (72hr for severe incidents in
products), AI Act serious-incident reporting, and GDPR breach notification (72hr) simultaneously, each
to a different authority on a different clock — build **one incident-classification decision tree** with
every applicable regime pre-mapped (see Ch. 37).

## Platform and market regulation

**DSA:** notice-and-action, statements of reasons, internal complaints; for VLOPs/VLOSEs (45M+ monthly
EU users) — annual systemic-risk assessments (illegal content, fundamental rights, elections,
gender-based violence, public health, minors), independent audits, researcher data access, crisis
response, recommender-system transparency incl. a non-profiling option, ad-profiling restrictions on
sensitive data and minors. **Stack:** L2 (recommender models are now externally auditable), L4
(real-time monitoring for illegal content), L5 (annual risk assessments = the most demanding
transparency exercise outside financial services). If your generative-AI feature ships into a VLOP/
VLOSE surface, it enters *their* systemic risk assessment — build Annex-IV-grade model documentation
so their auditors can consume it.

**DMA:** designated gatekeepers must not combine personal data across services without explicit consent,
must permit business-user competing offers, provide messaging interoperability and effective
portability. **Stack:** L3 — AI feature delivery depending on cross-service data combination requires
architectural separation enforced at the boundary, not just a consent screen.

## Cybersecurity and operational resilience

**NIS2:** essential/important entities across 18 sectors (energy, transport, banking, healthcare, digital
infra, etc.). Risk-management measures (incident handling, business continuity, **supply-chain
security** covering direct suppliers/service providers, crypto policy, MFA); reporting at **24hr
(early warning) / 72hr (notification) / 1 month (final report)**; **management-body personal liability**
for non-compliance. AI-consequence: supply-chain security obligations now cover AI providers serving
essential/important entities — vendor inventories must include AI components/inference services, which
pushes NIS2 requirements contractually onto AI providers regardless of whether they're independently
in scope. **Common failure pattern:** an AI inference service categorized by procurement as "software
licensing" rather than an ICT service never enters the vendor inventory — by hour 20 of a 24hr clock
the entity discovers no contractual notification right and no pre-classified incident category. Map AI
dependencies into the register *before* the incident.

**DORA:** financial entities + ICT third-party providers. ICT risk-management framework (board-approved),
major-incident classification/reporting, operational resilience testing (threat-led penetration testing
every 3yrs for significant entities — must include adversarial ML), **prescriptive contractual
provisions** with ICT providers (service descriptions, locations, security/SLAs, **exit strategies**,
audit rights, material-change notification), concentration-risk monitoring, critical-provider oversight
(1%/day penalty). **Common failure pattern:** exit-strategy clauses signed but not *engineered* — model
embeddings/fine-tunes/inference formats are proprietary, so the financial entity can't actually migrate
within the promised window; supervisors read exit strategies against technical reality.

**Cyber Resilience Act:** products with digital elements. Essential cybersecurity requirements (no known
exploitable vulnerabilities at release, secure defaults, vulnerability handling, updates, encryption),
cybersecurity risk assessment across the lifecycle, notified-body assessment for critical products,
**24hr** active-exploited-vulnerability reporting to ENISA, **72hr** severe-incident reporting, 14-day
final reports, min. 5-year default security-update lifecycle. AI models embedded in products must
satisfy essential requirements (adversarial robustness, prompt-injection defense are now regulatory
expectations, not just good practice). **Practitioner note:** treat CRA + AI Act documentation as one
combined build — a combined Annex-IV-plus-CRA technical file avoids maintaining two divergent accounts
of the same system.

**Cybersecurity Act / ENISA:** voluntary EU certification framework (EUCC scheme adopted 2024; EUCS
cloud scheme delayed on sovereignty disagreement). ENISA's 2024 AI Threat Landscape report and 2025 ML
Security Guidance are becoming reference points in NIS2/DORA supervisory dialogue.

## Data access, sharing, and communications privacy

**Data Act:** connected-product data-access rights for users; **switching obligations for data
processing services (incl. AI inference)** — max 30-day contractual transition, switching charges on a
mandated glide path to elimination after 2027, equivalent-functionality requirement. For customers this
converts vendor lock-in from a commercial complaint into a legal claim; for providers, design the export
path (weights, fine-tunes, embeddings, logs, formats) *before* a customer invokes it.

**Data Governance Act:** facilitates public-sector data reuse (secure environments, anonymization),
regulates data-intermediation services and data altruism (altruism rulebook still pending) — a lawful
sourcing channel for AI training data with documented provenance simplifying the downstream Art. 10
(AI Act) analysis.

**ePrivacy Directive:** Art. 5(3) consent for non-essential cookies/tracking; opt-in for e-marketing.
Its AI significance is *upstream lawfulness* — behavioral data harvested through non-compliant cookie
deployments contaminates every model trained on it, and because the cascading-failure principle runs
upward, the defect surfaces as a model-lawfulness problem that can't be fixed at the model layer. Tag
behavioral training data with its consent provenance at ingestion, or treat it as unusable.

**EHDS:** health data primary use (cross-border care, MyHealth@EU) and **secondary use** (research, AI
training, public health) via national health data access bodies, subject to permitted purposes/secure
processing/no re-identification. A lawful-basis pathway for healthcare AI training within specified
constraints — but the authorization terms travel with the data and bind the model program; record them
in dataset lineage.

## Liability and digital identity

**Revised Product Liability Directive:** explicitly extends product liability to **software including
AI**; disclosure-of-evidence + rebuttable presumptions of defect/causation ease the plaintiff's burden;
new compensable-damage categories include data corruption and psychological harm. **This is already in
force** — treat it as present-tense strict-liability exposure regardless of the pending AILD's status.
**Practitioner note:** courts can order production of technical documentation under the disclosure
mechanism — write the Annex IV file assuming it will one day be read aloud in litigation.

**AI Liability Directive (pending):** would add rebuttable causal presumptions for AI-related fault
claims; removed from the Commission's 2025 priority list, revival uncertain.

**eIDAS 2.0:** European Digital Identity Wallet (member states must provide by 2026); relying parties
using it for KYC/identity must register and stay within registered purposes — a privacy-minimizing
alternative to bulk PII collection.

## Operationalizing the AI Act's GPAI regime

**GPAI Code of Practice:** the operational playbook for the Art. 51-55 obligations already in force
(since Aug 2, 2025). Adherence = presumption of compliance; the alternative (demonstrating equivalent
compliance independently) is more expensive and less certain. For downstream deployers, the Code
defines what documentation to demand from a model vendor in procurement.

## Key takeaway

The suite is one regulatory system wearing thirteen names, converging on the same demands the Stack
already organizes: lawful/documented sourcing (Data Act, DGA, ePrivacy, EHDS → L1); secure, evaluated
models (CRA, Code of Practice → L2); governed integration/vendor chains (DMA, NIS2, DORA → L3);
monitored operation with fast incident reporting (DSA, NIS2, CRA, DORA → L4); evidence surviving audit,
supervision, litigation (DSA audits, DORA docs, PLD disclosure, certification → L5). Build the Stack
once; map each instrument's obligations onto it.
