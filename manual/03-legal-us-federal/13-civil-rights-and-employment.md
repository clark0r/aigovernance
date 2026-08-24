# Civil Rights and Employment Law Applied to AI

*Audience: lawyers on AI in employment, housing, screening, and customer-facing digital services; HR
leaders procuring hiring/workforce tools. EEOC's ADA Title I hiring guidance is a regulator entry in
[Sector-Specific Federal Regulators on AI](15-sector-specific-federal-regulators.md); state AI hiring
statutes (NYC LL144, Illinois) in
[State AI Statutes](../04-legal-us-state/18-state-ai-statutes.md).*

## The doctrinal frame — old statutes, full force

None of these statutes mention machine learning, and none needs to — they prohibit discriminatory
*outcomes* regardless of mechanism. Three doctrines do the work:

- **Disparate treatment** — intentional discrimination; for AI, arises where a protected characteristic
  or a *known proxy* is used as a feature/targeting criterion. "The vendor built it" is not a defense.
- **Disparate impact** — a facially neutral practice falling more harshly on a protected class, not
  justified by business necessity where a **less discriminatory alternative (LDA)** exists. This is the
  primary theory for AI selection tools: plaintiff shows a statistical disparity → burden shifts to
  defendant to show job-relatedness/business necessity → plaintiff can still win by showing an LDA the
  defendant refused to adopt. Model selection *is* this fact pattern.
- **Reasonable accommodation** — ADA/Title VII require accommodating individuals whose disabilities or
  practices interact badly with a standardized assessment; independent of any statistical disparity.

The operational bridge: the **Uniform Guidelines on Employee Selection Procedures** (29 CFR 1607) supply
the adverse-impact framework, including the **four-fifths rule** and validation-study requirements.

**Key takeaway:** the organizations that lose these cases are rarely the ones with the most biased
models — they're the ones with no contemporaneous record: no adverse-impact analysis, no validation
study, no documented LDA search, no accommodation channel.

## Statutes at a glance

| Statute | Protected basis | Threshold | AI exposure |
|---|---|---|---|
| Title VII | Race/color/religion/sex/national origin | 15+ employees | Hiring/promotion/termination tools; disparate impact |
| ADEA | Age 40+ | 20+ employees | Age-correlated features; ad targeting; recruitment funnels |
| GINA | Genetic information | Employers (Title II); health plans (Title I) | Inferred genetic info; family history; phenotype analysis |
| Section 503/VEVRAA (OFCCP) | Disability; veterans | Federal contractors | AI selection tools in contractor personnel processes |
| Fair Housing Act | Race/color/national origin/religion/sex/familial status/disability | Housing transactions | Tenant screening, underwriting, advertising, valuation, eviction prediction |
| ADA Title III | Disability | Public accommodations | Chatbots, voice interfaces, AI-content accessibility |
| NLRA | Protected concerted activity | Most private employers | AI workplace surveillance/management tools |

## Title VII — the anchor statute

EEOC's 2024-2028 Strategic Enforcement Plan explicitly prioritizes algorithmic discrimination. **EEOC v.
iTutorGroup (2023, $365K)** — first resolved EEOC AI discrimination case, automated rejection of older
applicants. Requirements: adverse-impact analysis (four-fifths rule) at deployment and every material
model update; validation study or documented LDA search; records sufficient to support subgroup
selection-rate analysis. **Common failure pattern:** relying on a vendor's "EEOC compliant" assurance
without obtaining the underlying statistics — contract for delivery of adverse-impact analyses, audit
rights, and demographic-segmented selection data as procurement conditions, not post-charge requests.

## ADEA — the overlooked subgroup

Age-correlated *features* (years of experience, graduation year, tech-familiarity) can produce disparate
impact even where age is never a direct input. 2019 Facebook ad-targeting settlement established that
age-based ad targeting in employment can violate ADEA. **Audit feature lists for temporal proxies**
(graduation year, tenure, legacy-tool familiarity); willful violations carry liquidated damages, making
feature-selection reasoning directly relevant to damages exposure.

## GINA — the inference trap

A model doesn't need a genome to process "genetic information" — it needs only inputs from which
genetic predisposition can be derived (family medical history fields, health questionnaire free text,
phenotype-inferring images). **The collection prohibition reaches acquisition, not just use** — GINA can
be violated at the data-ingestion stage before any model is even trained. Add a GINA screen to the data-
acquisition gate for any workforce/benefits AI.

## OFCCP / federal contractors post-EO 11246

EO 11246 (race/sex affirmative action) was **revoked January 2025**; Section 503 (disability, 7%
utilization goal) and VEVRAA (veterans) remain operative and require AI selection-tool assessment as
part of the affirmative action plan. Title VII/ADEA/GINA/ADA continue independently. Debarment (loss of
federal contracting eligibility) is the operative sanction.

## Fair Housing Act

Covers AI in tenant screening, mortgage underwriting, valuation, advertising, eviction prediction under
both disparate-treatment and disparate-impact theories, alongside FCRA (adverse action) and ECOA
(underwriting) — a single housing AI system commonly answers to three federal regimes at once.
**HUD 2024 guidance + SafeRent settlement ($2.275M, 2023)** established federal tenant-screening
enforcement; the **Facebook Settlement (2022)** governs housing-ad algorithmic targeting. **Familial
status** is the protected class housing AI teams most often forget — screening features penalizing
household size/occupancy/school-proximity search behavior can encode it directly. Civil penalties up to
$25,000 (first)/$65,000 (repeat).

## ADA Title III — customer-facing accessibility

Reaches AI chatbots, voice interfaces, recommendation engines, generative content (alt text/captions).
WCAG 2.1 AA is the de facto benchmark pending DOJ's 2024 ANPRM on codified digital-accessibility
standards. Generative surfaces are a **continuous** accessibility risk (every output can regress
accessibility) — add automated alt-text/caption/assistive-tech-compatibility checks to the same
deployment gate that checks content policy, and provide a persistent accessible non-AI fallback channel.

## NLRA and algorithmic management

NLRB General Counsel Memo GC 23-02 (2022) applies Section 7 to AI workplace surveillance — employer use
of AI to monitor workers may unlawfully chill protected concerted activity even without any adverse
action against a specific employee. Sentiment-analysis/communications-monitoring tools are particularly
exposed (organizing conversations are exactly the anomalous cluster such tools are designed to surface).
Run the Section 7 analysis against the tool's actual *capability*, not its marketed purpose.

## State workforce surveillance statutes (survey)

NY Labor Law §52-c requires written notice of electronic monitoring at hire; CA AB 2188 restricts
employment decisions based on off-duty cannabis use (constraining what signals workforce AI may weigh);
several states are considering/enacting AI-worker-management notice + discipline limits + human-review
mandates. Maintain one national monitoring-disclosure standard set to the strictest applicable state.

## The employment/housing AI defense file (standing Layer 5 artifacts, per system)

- **System inventory entry** — purpose, decision produced, population affected, vendor/in-house,
  applicable statutes.
- **Adverse-impact analysis** — four-fifths rule by race/sex/age bands (+ familial status/disability in
  housing contexts), run at deployment and each material update.
- **Validation/business-necessity record.**
- **Less-discriminatory-alternative memo** — the single artifact most often missing and most often
  dispositive.
- **Proxy-feature review** — age proxies, GINA acquisition, protected-class correlates (ZIP code, name,
  household composition).
- **Accommodation-channel evidence.**
- **Monitoring disclosures** (workforce AI) + Section 7 capability review.
- **Vendor file** — contractual rights to statistics/audits, OFCCP-ready selection-rate data.

**Common failure pattern:** one compliance file per *statute*, none per *system* — when the EEOC charge,
HUD complaint, and OFCCP audit each arrive asking about the same model, three teams reconstruct three
inconsistent accounts. Maintain one defense file per AI system, mapped to every applicable statute.

## Key takeaway

Disparate-impact doctrine turns model selection into a legal procedure: measure the disparity, justify
necessity, prove you looked for something better — do those three things, in writing, before
deployment, for every protected class, and the oldest laws in this manual become manageable engineering
requirements rather than litigation lotteries.
