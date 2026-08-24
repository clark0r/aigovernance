# The GDPR

*Audience: lawyers/counsel needing the authoritative legal reference on GDPR as applied to AI.
Regulation (EU) 2016/679.*

## At a glance

| | |
|---|---|
| **Jurisdiction** | EU (extraterritorial, Art. 3) |
| **Effective** | May 25, 2018 |
| **Regulator** | National DPAs; EDPB; EDPS (Union institutions) |
| **Scope** | Controllers/processors in the EU, or outside the EU offering goods/services to, or monitoring behavior of, EU data subjects |

**Applicability to AI:** the GDPR is technology-neutral, so it governs AI architectures/training methods
that didn't exist when written. Because the definition of personal data expressly includes
**inferences**, AI training data *and* the inferences a model draws about people are both squarely in
scope. Interaction with the EU AI Act is the central EU compliance complexity — see
[The EU AI Act](08-eu-ai-act.md).

## The seven Article 5(1) principles (Tier 2 penalties attach directly to violation)

- **Lawfulness, fairness, transparency** — a valid legal basis, no deception/exploitation of information
  asymmetries, adequate disclosure of who/what/why/basis/with-whom/rights.
- **Purpose limitation** — data collected for specified purposes can't be repurposed to incompatible
  ends without new consent or a documented compatibility assessment (fraud detection → AML detection is
  plausibly compatible; marketing data → hiring decisions is not).
- **Data minimization** — only what's necessary for the stated purpose. Genuinely hard for AI: feature
  importance is often unknown at collection time, minimization can conflict with fairness testing that
  needs demographic attributes. Requires principled feature selection + documented retention
  justifications.
- **Accuracy** — including a *staleness* duty: a model still using 2020 data in 2024 for consequential
  decisions may process information that no longer reflects reality.
- **Storage limitation** — collides with ML's habit of retaining all training data indefinitely; forces
  explicit, periodically-reassessed retention decisions.
- **Integrity and confidentiality** — standard infosec + governance constraining *authorized* users
  (scoped, logged, purpose-limited access).
- **Accountability** — converts process claims into *evidence* obligations. Regulators treat missing
  documentation as a violation in itself, not merely weak evidence — this is the GDPR's Layer 5 engine.

## Lawful bases (Article 6) and special categories (Article 9)

Six bases; must be chosen and documented **before** processing begins (switching post hoc is an
enforcement red flag): consent (specific, informed, freely-given, as-easy-to-withdraw-as-to-give — the
"processing to improve our services" trap fails specificity for AI training); contract (necessity-
limited — see the Meta enforcement below); legal obligation; vital interests; public task; **legitimate
interests** (the AI-training workhorse — requires a documented, contemporaneous three-part test:
legitimate interest, necessity, balancing; DPAs have opened inquiries precisely where the balancing test
didn't exist in writing; cannot support Art. 22 solely-automated decisions or substitute for an Art. 9
condition).

**Special categories (Art. 9):** race/ethnicity, political opinion, religion, trade union membership,
genetic/biometric data, health data, sex life/orientation — require **both** an Art. 6 basis and a
separate Art. 9(2) condition (usually explicit consent). **AI trap:** inference — a model predicting
creditworthiness may incidentally learn to infer health conditions with high accuracy; biometric/
emotion-adjacent systems generate special-category data by design. Any system that ingests *or infers*
Art. 9 data needs the dual-condition analysis, documented, before development proceeds.

## Data subject rights and their AI complications

| Right | Provision | AI complication |
|---|---|---|
| Access | Art. 15 | Must explain what algorithms do with data, not just what data is held — generic model descriptions fail the standard |
| Rectification | Art. 16 | Corrected inputs may invalidate prior model-driven decisions |
| Erasure | Art. 17 | Does deletion reach training corpora and model influence? Retraining required? |
| Restriction | Art. 18 | Suppress an individual from profiling/model pipelines without deleting |
| Portability | Art. 20 | Scope of derived/inferred data |
| Objection | Art. 21 | Halting model-driven profiling for one objector while the model serves everyone else |
| Not to be subject to solely automated decisions | Art. 22 | See below |
| Transparency | Art. 13-14 | Disclosing AI involvement in actionable language |

Enforcement verifies rights mechanisms by *exercising* them; a response omitting profiling logic,
inferred attributes, or training-data holdings is incomplete and is treated as an enforcement finding,
not a customer-service issue.

## Controllers, processors, and the accountability infrastructure

Controller determines purposes/means; processor acts on controller's documented instructions. AI supply
chains strain the model — a vendor training on customer data for its own model improvement is *not*
acting as a processor for that activity; joint controllership can arise. Art. 28 DPAs must impose
processor obligations + subprocessor controls + audit rights. Four load-bearing components: **RoPA**
(Art. 30 — DPAs request it in early-stage inquiries; AI training/inference activity must be in it);
**DPO** designation where Art. 37 requires; **breach notification** (Art. 33, 72hrs to the authority;
Art. 34, without undue delay to data subjects where high risk — AI systems belong in the breach playbook
because model inversion/membership inference/training-data exposure are personal-data breaches when they
succeed); **transfer mechanisms** (Ch. V, see below).

## Article 22 — automated decision-making (the central AI provision)

Right not to be subject to a decision **based solely on automated processing** (including profiling)
that produces legal or similarly significant effects.

- **"Solely automated" test:** turns on whether human involvement is *meaningful*. Rubber-stamping an
  algorithmic recommendation doesn't remove a decision from scope — a reviewer who rarely overrides, is
  trained to defer, or lacks authority to decide differently doesn't count. No fixed override percentage
  is specified; build defensible oversight and *document that it operates in fact*. Tests mirror the EU
  AI Act's Art. 14 conditions (see [The EU AI Act](08-eu-ai-act.md)) — harmonizing the two is a
  recurring compliance task for any org building one program to both.
- **Exceptions (Art. 22(2)):** necessary for contract performance (does heavy lifting for automated
  credit scoring/resume screening/underwriting); authorized by Union/member-state law with safeguards;
  explicit consent. Special-category data faces stricter Art. 9 conditions even within an exception, and
  **legitimate interest is never available** as the Art. 22 basis.
- **Explanation/contestation (Recital 71, Art. 13-15):** guarantees explanation and contest, not a
  favorable outcome. The hard problem is technical — a deep network's proxy patterns (names, zip codes)
  may drive outcomes the org can't fully interpret. Enforcement condemns "explanation theater": naming
  one decisive factor when dozens of unmentioned variables collectively mattered more misleads the
  individual who acts on it.

**Practical architectures:** genuinely human decisions informed by AI scoring (avoids Art. 22 entirely),
or fully automated decisions built on models explainable enough to support meaningful contest. The
hybrid dominates in practice — **compliance is decided by evidence about how decisions actually get
made**: override rates, reviewer caseloads, training records, explanation samples are what a DPA tests.

## The DPIA duty (Article 35)

Required before processing likely to result in high risk: (1) systematic/extensive automated evaluation
(incl. profiling) producing significant effects; (2) large-scale special-category processing; (3)
large-scale systematic public-area monitoring. Most consequential commercial AI applications trigger it.
Art. 36 requires prior consultation with the supervisory authority where residual risk can't be
adequately mitigated.

A legally sufficient DPIA reaches: data dimension (sources, volume, sensitivity, retention); model
dimension (architecture, training, validation, update mechanics); decision dimension (what decisions,
what oversight, what disclosure/contestation); governance dimension (ownership, audit trails). AI-
specific risks to include: discrimination, re-identification, sensitive-attribute inference, model
extraction, membership inference, accuracy degradation over time. DPAs reject assessments that declare
risk "acceptable" without analysis or propose mitigations without owners/parameters — must precede
processing, stay a living document, and be among the first artifacts requested in any AI inquiry.

## Cross-border transfers and the Schrems framework (Art. 44-50)

Adequacy decisions, SCCs, BCRs, or narrow derogations. **Schrems I (2015)** invalidated Safe Harbor
(bulk surveillance without proportionality); **Schrems II (2020)** invalidated Privacy Shield (FISA §702
lacked individualized judicial authorization/notice/redress for EU data subjects) and required a
**transfer impact assessment** even for SCCs: identify destination-jurisdiction government-access laws,
determine whether they'd prevent honoring SCC commitments, assess supplementary measures (principally
exporter-held-key encryption). Honest US-cloud assessments have repeatedly concluded FISA-authorized
access can't be fully mitigated for data the provider can read — driving real architecture (EU-hosted
infra, exporter-held keys, restructured business models). The **EU-US Data Privacy Framework** (2023)
restored an adequacy pathway; treat it as functioning but contested (a further legal challenge is
anticipated; the underlying FISA architecture that prompted Schrems II remains in place — see
[US Communications, Intermediary, and Surveillance Law](../03-legal-us-federal/12-us-communications-intermediary-surveillance.md)).
AI training pipelines feel this acutely because centralizing training data resists exporter-held-key
encryption designs.

## Penalties and AI-specific enforcement

Two tiers: €10M/2% (infrastructure violations) and **€20M/4%** (processing principles, rights, transfer
rules) global turnover. Meta's €1.2B transfer fine (2023) is the largest to date.

| Case | Doctrinal holding |
|---|---|
| **Clearview AI** (>€90M cumulative across DPAs + processing bans) | Public availability ≠ a right to process; no direct commercial relationship ≠ exemption; scale facial recognition warrants heightened pre-deployment scrutiny |
| **Meta behavioral advertising** (cumulative >€1B) | Contract-basis processing is limited to what's *actually necessary* for the contracted service — behavioral profiling for ad revenue failed necessity; consent buried in ToS ≠ valid consent |
| **Amazon** (€746M, Luxembourg DPA) | Defines the documentation bar: training-data provenance, documented purposes per processing activity, lifecycle tracking, functioning erasure/access mechanics |
| **Austrian unemployment-service ADM case** | Assignment to an investigation queue is a decision with legal/similarly-significant effects even without determining the ultimate outcome; public-sector deployment doesn't soften Art. 22 safeguards |
| **Italian Garante — ChatGPT** (2023 block, settled €15M 2024) **and Replika** (€5M, 2025) | Generative AI providers face the full GDPR stack: training-data lawful basis, user transparency, age protection, rights mechanics |

**EDPB Opinion 28/2024** established the European position on: whether AI models "contain" personal
data at inference; the legitimate-interest analysis for training on publicly available data; downstream
consequences for deployers of upstream unlawful training. **Practitioner note:** maintain this analysis
as a documented artifact alongside the DPIA — its absence is itself a compliance signal DPAs now
explicitly request.

**Common failure pattern:** reading the enforcement record as a big-tech-only problem. The actual
pattern across cases is the absence of contemporaneous artifacts — no lawful-basis analysis, no
balancing test, no DPIA, no rights mechanics reaching the model pipeline.

## Key takeaway

The GDPR governs every phase of the AI lifecycle touching personal data, and AI enforcement is mature,
not emerging. What changes is evidentiary expectation, and the direction is uniform: contemporaneous,
specific, maintained. Build the artifacts as the system is built — reconstructing them under inquiry is
worth little.
