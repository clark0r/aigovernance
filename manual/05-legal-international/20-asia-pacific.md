# Asia-Pacific Regimes

*Audience: counsel/privacy officers for AI operations touching Asia-Pacific markets. This chapter has
full narrative depth for China, Japan, South Korea, Singapore, and India; the remaining nine
jurisdictions in the comparison table below (Australia, New Zealand, Vietnam, Indonesia, Thailand, the
Philippines, Malaysia, Hong Kong, Taiwan) are currently covered at summary-table level only — fuller
narrative treatment awaits additional source material, matching the coverage note in the top-level
README.*

## Orientation: three philosophies, one region

Asia-Pacific AI governance sorts into three postures rather than one convergent model:
1. **State-centric control** (China) — data/algorithm/content governance as extensions of state
   oversight; registration and security-review gates that have no Western analogue.
2. **Sectoral/soft-law** (Japan, Singapore, Hong Kong) — light-touch, guidance-led frameworks betting
   that voluntary frameworks plus targeted sectoral rules outperform horizontal legislation; several
   (Singapore's AI Verify) are becoming de facto regional/global reference points despite non-binding
   status.
2. **Hybrid comprehensive** (South Korea, India, and emerging Australia reform) — GDPR-adjacent
   comprehensive privacy law with a separate, newer AI-specific instrument layered on top.

The practical consequence: a single "APAC AI compliance program" doesn't exist the way a "GDPR-derivative
program" does for Latin America (see
[The United Kingdom and the Americas](19-uk-and-americas.md)) — build a jurisdiction-tagged control
matrix keyed to which of
the three postures applies, then localize.

## Regional comparison at a glance

| Jurisdiction | Principal privacy law | Regulator | Max penalty | AI-specific instrument |
|---|---|---|---|---|
| China | PIPL + DSL + CSL ("data trinity") | CAC | Up to 5% turnover or RMB 50M | Generative AI Measures; Deep Synthesis Provisions; Algorithmic Recommendation Provisions |
| Japan | APPI | PPC | Up to JPY 100M (corporate) | Soft-law AI Guidelines (METI/MIC); sectoral |
| South Korea | PIPA | PIPC | Up to 3% relevant revenue | **AI Basic Act** (eff. Jan 2026) |
| Singapore | PDPA | PDPC | Up to SGD 1M or 10% turnover | Model AI Governance Framework; Gen AI Framework; AI Verify (testing toolkit) |
| India | DPDP Act 2023 | Data Protection Board | Up to INR 250 crore (~USD 30M) | No dedicated AI statute; DPDP applies to AI processing |
| Australia | Privacy Act 1988 (reform ongoing) | OAIC | Up to greater of AUD 50M / 30% turnover / 3x benefit | No dedicated AI statute; voluntary AI Safety Standard |
| New Zealand | Privacy Act 2020 | Privacy Commissioner | NZD 10,000 (individual, low) | Algorithm Charter (voluntary, public sector) |
| Vietnam | PDPD (Decree 13/2023) | MPS | Up to 5% revenue (draft PDPL escalates) | Draft AI law in development |
| Indonesia | PDP Law (2022) | MOCI | Up to 2% annual revenue | Ministerial AI circular (non-binding) |
| Thailand | PDPA (2019) | PDPC (Thailand) | Up to THB 5M administrative + criminal | Draft AI Act in development |
| Philippines | Data Privacy Act (2012) | NPC | Up to PHP 5M + imprisonment | NPC AI advisory guidance |
| Malaysia | PDPA (amended 2024) | Dept. of Personal Data Protection | Up to MYR 1M + imprisonment | National AI Roadmap (non-binding) |
| Hong Kong | PDPO | PCPD | Fines + imprisonment (criminal model) | PCPD AI guidance (non-binding) |
| Taiwan | PDPA (Taiwan) | Ministry of Justice (sectoral) | Up to TWD 15M | Draft AI Basic Act in legislature |

## China — the "data trinity" plus algorithm-specific instruments

China regulates AI through three interlocking statutes rather than one comprehensive law, plus a growing
set of algorithm/content-specific rules layered on top — the most administratively distinctive regime in
this manual.

**The trinity:**
- **PIPL (Personal Information Protection Law, 2021)** — China's GDPR-equivalent: consent-centric,
  separate consent required for sensitive personal information and cross-border transfer, data-
  localization triggers for critical information infrastructure operators (CIIOs) and volume thresholds,
  extraterritorial reach for processing targeting Chinese individuals.
- **DSL (Data Security Law, 2021)** — classifies data by national-security/economic-significance tier
  ("important data," "core data"), imposing security-review and export-control obligations independent
  of whether the data is personal information at all — a training corpus of non-personal industrial data
  can trigger DSL obligations that PIPL never reaches.
- **CSL (Cybersecurity Law, 2017)** — network security baseline, CIIO designation, security-assessment
  obligations for network products/services (AI systems embedded in critical infrastructure inherit CSL
  exposure on top of PIPL/DSL).

**Cross-border transfer** requires one of: CAC security assessment (above-threshold or CIIO), standard
contract filing, or certification — thresholds tightened materially since 2022; assume any transfer of
AI training data or model outputs containing Chinese personal information out of China requires an active
transfer-mechanism determination, not a one-time historical assessment.

**Algorithm-specific instruments (the layer with no Western equivalent):**
- **Algorithmic Recommendation Provisions (2022)** — registration of recommendation algorithms with CAC,
  user opt-out from algorithmic recommendation, prohibition on using algorithms to manipulate
  pricing/exploit vulnerable users, mandatory disclosure of algorithm logic to regulators (not
  necessarily to users).
- **Deep Synthesis Provisions (2023)** — labeling/watermarking requirements for AI-generated/synthetic
  content (deepfakes, voice cloning, generated images/video), real-name verification of users of deep-
  synthesis services, prohibition on using deep synthesis for disinformation.
- **Generative AI Measures (2023)** — the operative generative-AI framework: **algorithm filing with
  CAC** before public generative AI service launch, security assessment for services with "public opinion
  properties" or "social mobilization capacity," training-data lawfulness obligations (no IP
  infringement, data quality/accuracy), content labeling, and a requirement that generated content
  reflect "socialist core values" — a content-governance obligation with no analogue in any other
  jurisdiction in this manual.

**Practitioner note:** the filing/registration requirements are the operative compliance gate — a
generative AI service is not legally launchable in China without CAC algorithm filing, unlike Western
regimes where non-compliance is a post-launch enforcement risk. Treat filing as a **pre-launch blocking
dependency**, not a parallel workstream. **Common failure pattern:** treating China as "PIPL compliance"
alone and missing that DSL/CSL/algorithm-specific filings are independent, cumulative obligations that
attach to different aspects of the same AI system.

## Japan — soft-law leadership on a comprehensive-privacy base

**APPI (Act on Protection of Personal Information)**, most recently amended 2022, is Japan's GDPR-
adjacent comprehensive privacy law: consent for sensitive information, breach notification to the PPC and
affected individuals, cross-border transfer restrictions (adequacy-style "equivalent level" test),
individual rights (access/correction/deletion/use-suspension). Enforcement historically softer than
Western peers, but the PPC has been increasing order frequency and corporate-fine amounts.

**AI governance is deliberately soft law.** Japan has consciously chosen *not* to legislate horizontally,
betting that flexible, non-binding guidance (METI/MIC **AI Guidelines for Business, 2024**) outpaces
statute in a fast-moving field, backed by sector-specific hard law where AI touches an already-regulated
activity (financial services, healthcare, autonomous vehicles). The guidelines organize obligations
around familiar principles (human oversight, transparency, fairness, safety, accountability, innovation-
promotion) but carry no direct penalty — their force comes from reputational/procurement pressure and
their role as the reference point regulators cite when applying existing sectoral law to an AI-driven
harm.

**Practitioner note:** "no AI statute" does not mean "no AI exposure" — APPI applies fully to AI systems
processing personal information, and sectoral regulators (FSA for finance, PMDA for medical devices)
apply AI-specific supervisory expectations through existing licensing/examination channels exactly as
the US sectoral regulators do (see
[Sector-Specific Federal Regulators on AI](../03-legal-us-federal/15-sector-specific-federal-regulators.md)).
Build to the AI Guidelines' principles as the baseline; treat
sectoral licensure as the binding layer.

## South Korea — comprehensive privacy plus a dedicated AI statute

**PIPA (Personal Information Protection Act)**, most recently strengthened by a major 2023 amendment
(mandatory breach notification within 72 hours, expanded extraterritorial reach, higher penalty ceiling
of up to 3% of relevant revenue — among the highest in the region), is the most GDPR-convergent
comprehensive privacy law in Asia after Japan's APPI, with PIPC as an increasingly active independent
regulator.

**AI Basic Act (Framework Act on AI, effective January 2026)** — South Korea becomes one of the first
Asia-Pacific jurisdictions with dedicated horizontal AI legislation, structurally closer to the EU AI Act
than to Japan's soft-law model: risk-tiered obligations, a designated category of **"high-impact AI"**
(systems significantly affecting life/safety/fundamental rights — health, energy, transportation,
public services in enumerated sectors) carrying explainability/human-oversight/risk-management
obligations, transparency obligations for generative AI (AI-generated content disclosure), and a
national AI safety institute function. **Common failure pattern:** assuming Korea follows Japan's soft-
law regional pattern given geographic/cultural proximity — the AI Basic Act is binding statute with
penalties, not guidance, and orgs building only to APPI-equivalent PIPA compliance will be under-built
for the Act's high-impact-AI obligations once effective.

## Singapore — non-binding frameworks functioning as de facto standards

**PDPA (Personal Data Protection Act)**, administered by PDPC, is Singapore's comprehensive privacy
baseline: consent-based collection, notification obligations, a Do Not Call registry, and since 2020,
mandatory breach notification for breaches likely to result in significant harm. Penalties scaled
significantly upward in 2022 (up to SGD 1M or 10% of annual turnover in Singapore, whichever is higher).

**Singapore's distinctive contribution is its AI governance frameworks, deliberately non-binding but
highly influential:**
- **Model AI Governance Framework** (first issued 2019, updated) — the region's earliest comprehensive
  AI governance framework, organized around internal governance structures, human-in-the-loop risk
  calibration, operations management, and stakeholder communication; widely referenced/adopted by
  multinational orgs as a practical baseline even outside Singapore.
- **Generative AI Model Governance Framework** (2024) — extends the original framework to generative-AI-
  specific risks: hallucination, IP/copyright in training data, content provenance, misuse potential —
  organized around nine dimensions (accountability, data, trusted development/deployment, incident
  reporting, testing/assurance, security, content provenance, safety/alignment R&D, AI-for-public-good).
- **AI Verify** — an open-source AI governance testing framework and software toolkit (developed with
  IMDA) enabling technical validation of AI systems against internationally recognized principles
  (fairness, explainability, robustness, etc.) — increasingly used by orgs across the region as an
  actual technical testing tool, not merely a policy reference.

**Practitioner note:** none of Singapore's AI frameworks carry legal force, but they are the most
frequently cited *technical* reference point in the region (unlike Japan's more principle-level
guidance) — where a system needs to demonstrate fairness/explainability testing for any regulator in the
region, AI Verify results are increasingly accepted evidence. Building to AI Verify is a portable
investment across the entire APAC footprint, not a Singapore-only compliance cost.

## India — DPDP Act 2023 as the sole current instrument

**DPDP Act (Digital Personal Data Protection Act, 2023)**, India's first comprehensive data-protection
statute (rules under active finalization as of 2026), applies a consent-and-notice model with
"Significant Data Fiduciary" (SDF) designation for high-volume/high-risk processors — SDFs face
additional obligations: DPO appointment, independent data-protection-impact assessment (equivalent),
periodic audit. Penalties are the highest ceiling of any Asia-Pacific comprehensive privacy law (**up to
INR 250 crore, roughly USD 30M**, per instance of non-compliance, dwarfing PIPA/APPI/PDPA ceilings).
Cross-border transfer defaults to permitted **except** to a government-notified restricted list
(blocklist model — the inverse of PIPL's default-restricted approach), a materially lighter transfer
regime than China's.

**No dedicated AI statute exists or is imminent** — the DPDP Act is the operative instrument for any AI
system processing personal data of Indian residents, applying its consent/notice/SDF/cross-border rules
without AI-specific modification. Government policy (NITI Aayog's AI strategy documents) signals a
principles-based, innovation-first posture similar to Japan's, but with no binding AI framework yet
published. **Practitioner note:** because the SDF designation and its audit/DPO/DPIA-equivalent
obligations trigger on volume/risk criteria still being finalized in the rules, track the rules'
finalization actively — an org's SDF status (and therefore its obligation set) may change with the rules'
final text in a way its current program isn't built for.

## The nine jurisdictions covered at summary-table level only

For **Australia, New Zealand, Vietnam, Indonesia, Thailand, the Philippines, Malaysia, Hong Kong, and
Taiwan**, this knowledge base currently holds only the regulator/penalty/instrument data in the
comparison table above — no full narrative treatment. Two items worth flagging even at summary level:

- **Australia** is mid-reform: the Privacy Act 1988 is undergoing its most significant overhaul in
  decades (tranche-based amendments through 2024-2026), including a statutory tort for serious privacy
  invasion and increased penalties (up to the greater of AUD 50M / 30% of adjusted turnover / 3x benefit
  obtained) — materially higher than the pre-reform ceiling. No dedicated AI statute exists; a voluntary
  AI Safety Standard provides guardrails guidance. Treat Australia as a jurisdiction in active flux
  requiring a current-state check before relying on this table.
- **Vietnam and Thailand** both have draft AI-specific legislation in development (not yet enacted) —
  track for enactment dates before assuming their current comprehensive-privacy-only posture persists.

Do not extend the depth of treatment given to China/Japan/Korea/Singapore/India to these nine
jurisdictions from inference — confirm against primary sources or updated manual content before relying
on anything beyond the table above.

## Cross-region synthesis

Three practical building blocks cover the region without fifteen bespoke programs:
1. **A comprehensive-privacy core** (PIPL, APPI, PIPA, PDPA, DPDP, Privacy Act 1988, PDPO, etc.) — one
   consent/notice/rights/breach-notification program, jurisdiction-tagged for the deltas (China's
   consent-separation-per-purpose rules and India's SDF tier are the two largest deltas from a Virginia-
   pattern US baseline).
2. **A China-specific control set**, isolated from the rest of the region — data classification (DSL),
   CIIO assessment (CSL), algorithm/content filing (Generative AI Measures, Deep Synthesis, Algorithmic
   Recommendation Provisions) — because no other APAC jurisdiction requires pre-launch algorithm
   registration, this workstream cannot be merged into a general APAC program without over- or under-
   building every other market.
3. **A technical-testing layer built to AI Verify + Singapore's Gen AI Framework dimensions** — the most
   portable investment in the region, satisfying evidentiary expectations in Korea's AI Basic Act,
   Japan's AI Guidelines, and China's algorithm-filing documentation simultaneously, since fairness/
   explainability/robustness testing is the common technical substrate beneath every jurisdiction's
   different legal language.

## Key takeaway

Asia-Pacific has no regional GDPR to build toward. China requires pre-launch registration no Western
program anticipates; Korea just became the region's first binding horizontal AI statute; Singapore's
non-binding frameworks are the closest thing to a regional technical standard; the rest of the region
(India, Japan, and the nine table-only jurisdictions) runs on comprehensive privacy law with AI-specific
legislation still pending. Build the comprehensive-privacy core once, isolate China's registration
obligations as their own workstream, and invest in AI Verify-equivalent technical testing as the layer
that travels across every jurisdiction's differing legal text.
