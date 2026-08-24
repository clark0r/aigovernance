# Ch. 8 — The EU AI Act

*Audience: lawyers/counsel on any org that develops/deploys AI touching the EU market. Regulation (EU)
2024/1689.*

## At a glance

| | |
|---|---|
| **Jurisdiction** | EU (extraterritorial — providers placing on EU market, EU deployers, or use of outputs in the EU) |
| **Effective** | In force Aug 1, 2024; phased: prohibitions Feb 2, 2025; GPAI obligations Aug 2, 2025; Art. 50 transparency Aug 2, 2026; high-risk Annex III **deferred to Dec 2, 2027**; Annex I high-risk/product-safety deferred to **Aug 2, 2028** (Digital Omnibus) |
| **Regulator** | European AI Office (DG CNECT); national market surveillance authorities; EDPS (Union institutions); European AI Board |
| **Scope** | Providers, deployers, importers, distributors, product manufacturers — reaches any org whose AI outputs are used in the Union |

## Structure: the risk pyramid

| Tier | Treatment | Anchor | Examples |
|---|---|---|---|
| **Unacceptable risk** | Prohibited outright (Art. 5) | Art. 5 | Social scoring by public authorities; real-time remote biometric ID in public spaces (narrow LE exceptions); vulnerability exploitation; workplace/education emotion recognition |
| **High risk** | Comprehensive obligations + conformity assessment | Art. 6, Annexes I & III, Art. 8-15 | Recruitment, credit scoring, insurance underwriting, exam scoring, medical device AI, border control |
| **Limited risk** | Transparency obligations | Art. 50 | Chatbots, deepfake generators, emotion recognition outside prohibited contexts |
| **Minimal risk** | No AI Act obligations | — | Spam filters, game AI, inventory optimization |

**GPAI (general-purpose AI)** is a separate regime (Art. 51-55) layered on top, with enhanced duties
above the **systemic-risk threshold: ≥10^25 FLOP** training compute (Commission can also designate on
capability grounds regardless of compute).

## Legislative history (why the Act reads as it does)

Traces to the April 2020 Commission White Paper (initially soft-law); ChatGPT's Dec 2022 release exposed
the inadequacy of voluntary mechanisms, pivoting the April 2021 proposal to mandatory requirements. The
European Parliament's June 2023 amendments (expanding emotion-recognition prohibition, strengthening
biometric restrictions, mandating fundamental-rights impact assessments) reflected a cross-cutting
left/centrist/right coalition that prevented industry capture. Trilogue negotiations (June 2023-spring
2024) were most contested on: the high-risk definition, prohibited-practice scope, and foundation-model
obligations — the eventual GPAI compromise (transparency for all + enhanced above the systemic-risk
threshold) satisfied neither extreme fully. Adopted June 13, 2024. The GDPR's "Brussels Effect" precedent
(global compliance baseline because multinationals prefer one high standard) shaped the strategy
deliberately — early evidence (global vendors building to Annex IV, the GPAI Code of Practice functioning
as a de facto international standard) suggests it's working.

## Classification: Article 6 procedure

Annex III enumerates high-risk domains: biometric ID/emotion recognition; education/vocational training;
employment (recruitment, promotion, termination, task allocation); essential private/public services
(credit, insurance, benefits); law enforcement; migration/asylum/border control; justice/democratic
processes. Annex I captures AI as a safety component of already-regulated products (machinery, medical
devices, vehicles).

**Art. 6 exemption:** an Annex III system defaults to high-risk *unless* the org documents it doesn't
pose significant risk (narrow procedural task, improves a completed human activity, doesn't materially
influence outcomes) — the claim must be documented and defensible; a "narrow" task that cumulatively
shapes outcomes across a whole workforce (e.g., a resume filter removing "obviously unqualified"
candidates) doesn't automatically escape.

**Worked examples across tiers:**
- Facial recognition: real-time mass surveillance = **prohibited**; judicially-authorized targeted LE
  search for serious crime = exception; post-hoc footage analysis after a reported crime = **high-risk**;
  device unlock = limited-risk; game face-swap = minimal-risk.
- Employment: resume screening = high-risk; diversity analytics informing recruiting = high-risk;
  license-flagging tool with humans making all substantive decisions = limited-risk *only if documented*
  as non-material; job-description generator = minimal-risk.
- Credit/insurance: high-risk whether AI decides or merely supports (loan officers anchor on
  recommendations); fraud-triage that only flags for human investigation and makes no binding decision =
  limited-risk.

**Common failure pattern:** classifying by product label ("productivity tool," "decision-support
dashboard," "chatbot") rather than function and context. Regulators classify by what the system does to
people.

## Article 5 — prohibited practices (in force since Feb 2, 2025, no transition period)

| Category | Boundary |
|---|---|
| **Social scoring** | Prohibits *aggregation across unrelated life domains* into a unified score with cross-context consequences (China's model is the reference concern). Narrow single-domain assessment (credit models, recidivism scores) remains legal though possibly high-risk. Analytical test: aggregation of many narrow domain assessments into a unified score governing unrelated opportunities. |
| **Real-time remote biometric ID** | Targets mass surveillance in public spaces. Narrow LE exceptions: targeted search for specific suspects (serious crime), imminent serious threat prevention, CSAM investigation — require national-law authorization with strict safeguards (judicial authorization, cause standards, technical audits). Circumvention risk: pretextual "mass suspect" identification wearing a targeting label. |
| **Vulnerability exploitation / subliminal manipulation** | Systems exploiting age/disability/economic vulnerability, or subliminal techniques, to materially distort behavior causing significant harm. High threshold — ordinary preference-based advertising doesn't meet it. **No law-enforcement exception exists for this category.** |

**Common failure pattern:** no Art. 5 screen in design/marketing review. Recurring near-misses: emotion
recognition in HR products, engagement optimization targeting minors, any biometric categorization
capability. Maximum penalty tier (€35M/7%) and already-active enforcement.

## High-risk requirements mapped to the Stack (Art. 8-15)

| AI Act requirement | Provision | Stack layer |
|---|---|---|
| Data and data governance | Art. 10 | L1 |
| Risk management system | Art. 9 | L2 |
| Accuracy, robustness, cybersecurity | Art. 15 | L2 |
| Transparency/instructions to deployers | Art. 13 | L2-3 |
| Quality management system; supply-chain roles | Art. 17; 16-27 | L3 |
| Human oversight | Art. 14 | L4 |
| Post-market monitoring; serious-incident reporting | Art. 72-73 | L4 |
| Technical documentation; record-keeping; conformity assessment; registration | Art. 11-12, 43, Annex IV | L5 |

**L1 (Art. 10):** training/validation/test data must be relevant, representative, error-free, complete
"to the extent feasible," with documented bias examination and appropriate statistical properties.
Relevance = sourced from the actual deployment context (historical decisions carry historical bias);
representativeness may require deliberate oversampling of underrepresented groups.

**L2 (Art. 9 risk mgmt + Art. 15 accuracy/robustness/cybersecurity):** continuous risk management (FMEA-
style: biased outputs, adversarial inputs, deployment-context drift, human over-reliance), each risk
scored and mitigated technically/operationally/organizationally. Accuracy must be validated **per
demographic subgroup**, not just in aggregate.

**L3 (Art. 16-27):** provider carries core duties + Art. 17 QMS; importers/distributors verify
conformity; deployers use per instructions, assign human oversight, ensure input-data relevance, monitor,
report serious incidents. **Role-shifting rule:** a distributor/importer/deployer that rebrands,
substantially modifies, or repurposes a system into high-risk use *becomes the provider* and inherits
the full obligation set.

**L4 (Art. 14 human oversight + Art. 72-73 monitoring):** meaningful oversight has four operational
conditions: (1) humans understand the system well enough to critically evaluate it; (2) caseloads permit
substantive review (a loan officer reviewing 500 recs/day is a rubber stamp — advisory experience shows
high caseloads reliably collapse into automatic approval); (3) override authority is *real* (policies
making recommendations effectively binding, or demanding elaborate justification to deviate, defeat the
requirement — track override rates); (4) reviewers are trained on limitations/biases/edge cases. Art. 72
requires proportionate post-market monitoring; Art. 73 requires serious-incident reporting to market
surveillance authorities.

**L5 (Art. 11-12, 43):** Annex IV technical documentation must capture not just *what* was built but
*why* — architectures considered and rejected, performance trade-offs accepted, how fairness thresholds
were set. Art. 12 requires automatic logging sufficient to reconstruct system behavior, retained "well
beyond deployment" since harms/liability emerge on a delay. Conformity assessment: most Annex III
systems use **internal control** (provider self-assesses, issues EU declaration of conformity);
biometric systems + Annex I product-safety systems require **notified-body** assessment. CE marking
creates a legal presumption of conformity.

**Practitioner note:** build compliance to the Annex IV template even for systems not yet classified as
high-risk — it doubles as a cross-jurisdictional defense file (Product Liability Directive, GDPR
accountability, procurement due diligence).

## GPAI and systemic risk (Art. 51-55)

All GPAI providers: maintain technical documentation, supply downstream-provider information, implement
a copyright-compliance policy (respecting EU text-and-data-mining opt-outs — robots.txt, machine-readable
metadata), publish a training-data summary. Selective disclosure of only favorable benchmarks fails the
obligation.

**Systemic-risk models (≥10^25 FLOP presumption, or Commission capability-based designation):**
state-of-the-art evaluation including adversarial testing/red-teaming; systemic risk assessment/
mitigation covering misuse potential (CSAM, deepfake pornography, bio-weapon uplift, malware generation,
disinformation, fraud), cybersecurity vulnerabilities (model theft, weight manipulation, training-data
exposure), emergent-capability risks; serious-incident tracking/reporting to the EU AI Office; ongoing
(not just at-launch) monitoring for degradation and scaled misuse.

**GPAI Code of Practice (Commission, 2025):** adherence creates a *presumption of compliance*;
non-adherents must demonstrate equivalent compliance by other means (harder, more expensive).
**Practitioner note:** downstream deployers should demand the GPAI transparency artifacts (training-data
summary, documentation, downstream-provider info) in procurement — without them your own Annex III
compliance and Art. 10 data-governance analysis rest on an undocumented dependency.

## Enforcement and penalties

| Violation | Max penalty |
|---|---|
| Art. 5 prohibited practices | €35M or 7% global turnover |
| Most other obligations (high-risk, GPAI, transparency) | €15M or 3% |
| Incorrect/incomplete/misleading info to authorities | €7.5M or 1% |

Lower caps for SMEs/start-ups. Preserved member-state civil liability + the revised Product Liability
Directive (extends strict liability to software/AI with disclosure-of-evidence + rebuttable
presumptions — making the Annex IV file the principal defense asset; see Ch. 10). For orgs with
meaningful EU revenue, compliance cost is small against market-exclusion risk.

## Compliance timeline

| Date | Milestone |
|---|---|
| Aug 1, 2024 | Entry into force |
| Feb 2, 2025 | Art. 5 prohibitions apply; Art. 4 AI literacy begins |
| Aug 2, 2025 | GPAI obligations apply (Art. 51-55) |
| Aug 2, 2026 | Art. 50 transparency obligations in effect |
| **Dec 2, 2027** | Annex III high-risk obligations apply (deferred from Aug 2026 by Digital Omnibus) |
| Aug 2, 2028 | Annex I high-risk/product-safety obligations apply (deferred from Aug 2027) |

**Note on Art. 4 (AI literacy):** the Digital Omnibus (Reg. 2026/1744, in force Jul 27, 2026) replaced
Art. 4 — providers/deployers must take measures supporting staff AI literacy but are **not** required to
guarantee any individual's specific proficiency level.

**Common failure pattern:** anchoring compliance programs on the furthest deadline (Dec 2027) and
ignoring obligations already in force. Early enforcement findings concentrate on Art. 5 screening gaps
and missing Art. 50 disclosures on customer-facing chatbots/synthetic content — both fully applicable
now.

## Practical implementation sequence

1. Inventory + classify every system against Art. 5, Annex III, Art. 50 (documented memo per system).
2. Prioritize high-risk systems; assign a per-Stack-layer owner; 6-12 month project each.
3. Stand up Art. 10 data governance (provenance, representativeness, bias examination, QA, lifecycle
   docs).
4. Build Art. 9/15 validation (risk register, demographic disaggregation testing, adversarial
   evaluation, documented thresholds).
5. Design Art. 14 oversight into deployment *before* launch (explainability, caseloads, real override
   authority, training, override analytics).
6. Implement Art. 72/73 operations (monitoring, drift detection, incident classification, reporting
   pathways rehearsed pre-go-live).
7. Assemble the Annex IV file continuously; select the conformity route early.
8. Track harmonized standards (CEN-CENELEC) and AI Office guidance.

Sequence bottom-up: Layer 1 findings determine Layer 2 remediation; Layer 2 characteristics determine
Layer 3/4 compensating design; everything above generates the Layer 5 evidence that conformity
assessment consumes. Programs that start by drafting documentation produce shelf-ware.

## Key takeaway

The Act converts sound AI engineering governance into binding law with penalties reaching 7% of
worldwide turnover. Classification determines scope; the prohibitions and GPAI regime are *already*
enforceable; Dec 2, 2027 is the enterprise build horizon for the rest.
