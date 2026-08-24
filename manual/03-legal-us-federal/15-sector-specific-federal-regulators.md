# Sector-Specific Federal Regulators on AI

*Audience: healthcare, banking, consumer finance, insurance, securities, and employment-facing
organizations. Detailed operational playbooks for healthcare and financial services are not yet in
this knowledge base.*

## The unifying pattern: regulation by interpretation

None of these frameworks required new legislation — each regulator read its *existing* statute,
concluded AI-driven conduct was already inside it, and published guidance/circulars/bulletins/rules
saying so. Three consequences:
1. **No AI exemption, no grace period** — guidance clarifies obligations, it doesn't create them.
   Enforcement reaches conduct that preceded the guidance.
2. **The examiner is the interface** — most regimes operate through supervision (FDA premarket review,
   Fed/OCC exam, market-conduct exam, SEC/FINRA exam, OCR compliance review). The practical question is
   "what will the examiner ask for," making **Layer 5 evidence the operative compliance product**.
3. **Explainability + documentation are the common denominator** — every regulator here independently
   demands: (a) the org can explain what its model actually did, and (b) it holds documentation proving
   the explanation is real. A model that can't support specific, accurate explanations isn't deployable
   in any sector this chapter covers.

## Sectoral frameworks at a glance

| Sector | Instrument | Regulator | Core AI demand |
|---|---|---|---|
| Medical devices | FDA AI/ML SaMD framework + PCCP guidance (2024) | FDA CDRH | Premarket pathway, QSR, PCCP for adaptive models, post-market surveillance |
| Banking | SR 11-7 (2011) + SR 21-8 (third-party) | Fed/OCC/FDIC | Model inventory, independent validation, conceptual soundness |
| Consumer finance | CFPB Circulars 2022-03, 2023-03 | CFPB | Specific-reasons adverse action regardless of model complexity |
| Employment | EEOC ADA Title I guidance (2022) | EEOC | Disability screen-out + accommodation in AI assessment |
| Healthcare civil rights | ACA §1557 final rule (2024, AI provisions eff. May 2025) | HHS OCR | ID + mitigate discrimination risk in patient-care decision-support tools |
| Insurance | NAIC Model Bulletin (2023) | State insurance commissioners | Written AI program, fairness/bias/accuracy testing |
| Securities | SEC predictive-analytics posture (2023 proposal, pending; enforcing now via existing authority) | SEC/FINRA | Conflict-of-interest disclosure, "AI-washing" liability |

## FDA — AI/ML Software as a Medical Device

Existing device framework (510(k)/De Novo/PMA) applies to AI/ML devices; **intended use, not marketing
label, determines device status** (a "wellness" tool making diagnostic claims is an unapproved device
regardless of the regulatory strategy memo). The **2024 Predetermined Change Control Plan (PCCP)**
guidance lets manufacturers pre-specify permitted post-market algorithm modifications, avoiding a new
submission per update — draft it by *validated method and bounded envelope* (what will change, how
validated, what triggers rollback), not by aspiration. QSR (21 CFR 820) design controls, ISO 14971 risk
management, IEC 62304 software lifecycle, cybersecurity (SBOM under FDORA §524B). Stack: L1 clinical
training-data representativeness/subgroup performance; L2 PCCP-bounded algorithm docs; L3 EHR/workflow
integration reviewed as part of intended use; L4 real-world post-market monitoring; L5 Design History
File (the most extensive Layer 5 requirement in US healthcare AI). Penalties: civil, seizure, injunction,
criminal under FD&C Act; market removal is the sanction that matters for a device business.

## Federal Reserve SR 11-7 — banking model risk management

The most mature AI-relevant governance regime in this manual (2011, 15 years of supervisory practice).
Applies to any "model" (quantitative method/system/approach applying statistical/economic/financial/
mathematical theory to process input into estimates) — this definition captures generative AI tools,
vendor scoring services, and spreadsheet-era quantitative methods most orgs don't think to inventory.
Core obligations: model development documentation + conceptual soundness evaluation + ongoing
monitoring + outcomes analysis; **independent** validation (validators must have real authority to block
deployment); governance/policy/model inventory/internal audit; **SR 21-8** extends this to third-party
(vendor) models — the bank, not the vendor, is responsible for validating a model it can't see, so
negotiate documentation/testing-support/performance-reporting/exit rights *before* signature. Escalation
ladder: matter-requiring-attention → supervisory letter → formal enforcement → civil money penalties →
capital surcharges → management remediation.

## CFPB Circulars 2022-03 and 2023-03 — adverse action and AI

Complex models don't excuse the ECOA/Reg. B specific-reasons requirement (Circular 2022-03); generic
30-item reason checklists that don't meaningfully convey what mattered also fail (Circular 2023-03). The
explanation-fidelity standard has propagated into FCRA screening positions and the 2024 multi-agency
EEOC AI Joint Statement. **Test the explanation pipeline as rigorously as the model itself** — validation
should include fidelity testing of the explanation method against actual model behavior, sampled at the
individual-decision level, since an explanation method producing plausible-but-unfaithful reasons
misstates every notice at scale on a per-day penalty clock (up to $1,362,567/day).

## EEOC — ADA Title I and AI hiring tools

**EEOC v. iTutorGroup (2023)** established direct enforcement against algorithmic hiring discrimination
(age, in that case). ADA-specific theory: a screen-out based on a characteristic correlated with
disability is actionable **without needing a statistical disparity** — a single applicant screened out
by a tool measuring a disability-correlated characteristic, or denied an accommodation in an AI
assessment, states a claim. Interrogate what the tool *actually measures* (gamified assessments,
video-interview analysis, timed cognitive exercises frequently measure reaction time/speech patterns/
eye movement/affect — all disability-correlated) — for each, either demonstrate job-relatedness/business
necessity or remove it, and build a tested accommodation path that doesn't penalize the applicant who
uses it.

## ACA Section 1557 — healthcare nondiscrimination

The **2024 final rule (45 CFR §92.210, AI provisions effective May 1, 2025)** requires covered entities
(healthcare providers, Medicare/Medicaid recipients) to make "reasonable efforts" to identify **patient-
care decision-support tools** using inputs measuring/correlating with race/color/national origin/sex/
age/disability, and to mitigate discrimination risk. The obligation runs to the **entity using the tool,
not only its developer** — clinical risk scores, triage algorithms, EHR-embedded decision support are
all covered whether or not FDA-regulated. "Reasonable efforts" is a process standard starting with an
inventory most covered entities don't have — build the census of every decision-support tool, screen
input variables against protected characteristics, document the mitigation decision per flagged tool,
date-stamp everything.

## NAIC Model Bulletin — insurer AI systems

State-coordinated (not federal) but functions as the national insurance baseline the way SR 11-7 does
for banking. As of 2026, adopted/implemented in more than half of US states. Interprets *existing*
unfair-trade-practices authority — doesn't create new substantive standards, meaning AI-driven unfair
discrimination in underwriting/rating/claims was already sanctionable before adoption. Requires: a
**written AI program** (governance, risk mgmt), fairness/bias/accuracy testing, third-party AI vendor
due diligence. Write the program to be examined, not admired — if it promises annual bias testing of
rating models, dated test results covering production models must actually exist. Maintain one national
program at the bulletin's full standard rather than tracking state-by-state adoption.

## SEC — predictive data analytics and disclosure

The 2023 proposed rule on predictive data analytics conflicts of interest remains pending in revised
form, but **existing fiduciary/disclosure/anti-fraud obligations apply now** — the 2024 SEC "AI-washing"
enforcement actions established this under existing authority (the securities-law mirror of the FTC's
§5 posture). Reconcile three documents before any exam: the marketing description of your AI, the Form
ADV disclosure, and the engineering reality of what the system optimizes. Where a recommendation
model's objective function includes firm revenue/order flow/product placement, treat it as a disclosable
conflict now.

## Cross-sector convergence — five demands, seven vocabularies

| Demand | FDA | SR 11-7 | CFPB | EEOC | §1557 | NAIC | SEC |
|---|---|---|---|---|---|---|---|
| Inventory of AI in scope | Device list, DHF | Model inventory | Credit models in use | Assessment tools in use | Decision-support tool census | Written AI program inventory | Analytics in investor interactions |
| Validation/fairness testing | Clinical validation, subgroup perf. | Independent validation | Explanation fidelity | Adverse-impact validation | Fairness testing as mitigation | Fairness/bias/accuracy testing | Conflicts/suitability analysis |
| Explainability at decision level | PCCP-bounded behavior | Outcomes analysis | Specific principal reasons | Screen-out/accommodation analysis | Input-variable identification | Documentation of AI-driven decisions | Disclosed basis of recommendations |
| Third-party AI governance | Supplier/SBOM controls | SR 21-8 due diligence | Vendor model accountability | Vendor tool validation | Procured-tool mitigation duty | Vendor due diligence | Vendor analytics oversight |
| Standing documentation | Inspection-ready QSR file | Examination artifacts | Adverse-action records | Selection-rate/accommodation records | Reasonable-efforts file | Examined written program | Filings/marketing consistency |

**Sequence by supervisory intensity** for orgs regulated by more than one framework — build to the most
demanding applicable regime first (FDA for anything near a device claim, SR 11-7 for anything a banking
examiner will see); the others are then satisfied largely by relabeling existing artifacts.

## Key takeaway

Five regulators independently reinvented Layers 1-5 because supervision of consequential automated
decisions requires nothing less — the strongest empirical validation of the Stack framework itself.
Build the five capabilities once as one program, map to each regulator's vocabulary.
