# Comprehensive State Privacy Laws

*Audience: lawyers building a US multistate privacy position for AI. Covers all 20 comprehensive state
consumer privacy laws in force/enacted as of 2026. State biometric/cyber/breach regimes are in
[State Biometric, Cybersecurity, and Breach Notification Law](17-state-biometric-cyber-breach.md);
state AI-specific statutes (Colorado AI Act, TRAIGA) are in [State AI Statutes](18-state-ai-statutes.md).*

## Reading the patchwork

No federal preemption exists (see the ADPPA discussion below) and none is imminent. Two templates:
**California pattern** (CCPA/CPRA) — enforcement-agency-driven (CPPA), opt-out rights, sensitive-info
limits, and since 2025, explicit **ADMT** (automated decisionmaking technology) obligations.
**Virginia pattern** — GDPR-style controller/processor model: opt-out for sale/targeted ads, opt-in for
sensitive data, DPIAs for high-risk processing. Colorado introduced third-generation features (UOOM
recognition, detailed AG rules, standalone biometric/neural-data protections) that propagate through
later laws. Nearly every post-2023 statute is a Virginia/Connecticut variant + state-specific additions.

**Three features matter disproportionately for AI:**
1. **Inferences are personal information** (CA definition, functionally true elsewhere) — a model that
   infers income/health/purchase-propensity is creating regulated personal data subject to access/
   deletion/disclosure. Most orgs don't track/surface/delete inferences separately from source data.
2. **ADM/profiling rights are mainstream** — CA's ADMT opt-out, Virginia-pattern profiling opt-outs, and
   MN's right to question profiling collectively build a US analogue to GDPR Art. 22, assembled state by
   state.
3. **Assessments are the enforcement interface** — confidential when produced, discoverable on inquiry.
   The assessment is where a regulator first sees your AI governance.

**Practical strategy:** build to the strictest obligation **per element**, not per state — in practice
that means California for ADMT/SPI, Colorado for biometrics/profiling, Texas/Nebraska for breadth (no
volume threshold), Maryland for minimization, Minnesota for inventory/explainability, Washington
(MHMDA — see [State Biometric, Cybersecurity, and Breach Notification Law](17-state-biometric-cyber-breach.md))
for inferred health data.

## Applicability, penalties, cure periods (verify before relying)

| Law (state) | Effective | Threshold | Max penalty | Cure period |
|---|---|---|---|---|
| CCPA/CPRA (CA) | 2020/2023 | $26.625M rev, or 100k consumers, or 50% rev from sale/share | $2,500 ($7,500 intentional/minor); breach PRA $100-750/consumer | None |
| VCDPA (VA) | 2023 | 100k consumers, or 25k+50% sale rev | $7,500 | 30 days, permanent |
| CPA (CO) | 2023 | 100k consumers, or 25k+any sale rev | $20,000 | Sunset 1/1/2025 |
| CTDPA (CT) | 2023 | 100k (excl. payment), or 25k+25% rev | $5,000 willful | Sunset 7/1/2025 |
| UCPA (UT) | 2023 | $25M rev AND (100k, or 25k+50% rev) | $7,500 | 30 days |
| TDPSA (TX) | 2024 | **No volume threshold**; SBA carve-out | $7,500 | 30 days, preserved |
| FDBR (FL) | 2024 | $1B rev + platform criteria | $50,000; treble for children/opt-out | None |
| OCPA (OR) | 2024/25 | 100k, or 25k+25% rev | $7,500 | Sunset 1/1/2026 |
| MCDPA (MT) | 2024 | 50k (excl. payment), or 25k+25% rev | Montana UTPA | Sunset 4/1/2026 |
| ICDPA (IA) | 2025 | 100k, or 25k+50% rev | $7,500 | 90 days, permanent |
| NDPA (NE) | 2025 | **No volume threshold**; SBA carve-out | Nebraska CPA | 30 days |
| DPDPA (DE) | 2025 | 35k (excl. payment), or 10k+20% rev | $10,000 willful | Sunset 60 days post-effective |
| NHDPA (NH) | 2025 | 35k, or 10k+25% rev | NH CPA | Sunset 1/1/2026 |
| NJDPA (NJ) | 2025 | 100k, or 25k+any sale rev/discount | NJ CFA, treble damages | 18 months (first), sunsets 7/1/2026 |
| TIPA (TN) | 2025 | $25M rev AND (175k, or 25k+50% rev) | Treble, up to $15,000 willful | 60 days |
| MNCDPA (MN) | 2025 | 100k, or 25k+25% rev | MN CFA | AG discretion through 1/31/2026, then sunset |
| MODPA (MD) | 2025 | 35k, or 10k+20% rev | $10,000; $25,000 repeat | 60 days, sunsets 4/1/2027 |
| INCDPA (IN) | 2026 | 100k, or 25k+50% rev | $7,500 | 30 days, permanent |
| KCDPA (KY) | 2026 | 100k, or 25k+50% rev | $7,500 | 30 days, permanent |
| RIDTPPA (RI) | 2026 | Disclosure duty: all commercial sites; substantive: volume thresholds | $10,000 knowing/willful | None |

## Rights, ADM opt-outs, assessments (verify before relying)

| Law | Sensitive-data consent | Profiling/ADM opt-out | Assessments | UOOM honoring | Distinctive feature |
|---|---|---|---|---|---|
| CCPA/CPRA (CA) | Right to limit SPI; opt-in for secondary uses | **Yes — ADMT opt-out for significant decisions**, pre-use notice + alternative process | Risk assessments; **annual cybersecurity audits** | Yes (GPC) | ADMT regs; inference=personal info; dedicated agency (CPPA) |
| VCDPA (VA) | Opt-in | Yes, certain profiling | Yes | — | Original 2nd-gen template |
| CPA (CO) | Opt-in (incl. **neural data**) | Yes, profiling | Yes | Yes (7/2024) | **Biometric + neural data** protections; detailed AG rules |
| CTDPA (CT) | Opt-in | Yes | Yes | Yes | Minors' protections; engagement-prolongation ban |
| UCPA (UT) | Opt-out | No | No | No | Most business-friendly |
| TDPSA (TX) | Opt-in | Yes, profiling | Yes | — | No volume threshold; biometric-sale disclosure |
| OCPA (OR) | Opt-in (expanded def.) | Yes | Yes | — | **Specific third-party identity disclosure**; nonprofits covered |
| MODPA (MD) | Opt-in; **sale of sensitive data prohibited per se** | Yes, legal/similarly-significant effects | Yes | Yes | **Strict minimization**; under-18 ad/sale ban; healthcare geofence ban |
| MNCDPA (MN) | Opt-in | Yes, **plus right to question profiling results and review data used** | Yes | Yes | **Mandatory data inventory**; designated compliance person |
| NDPA (NE) / TDPSA (TX) | Opt-in | Yes | Yes | — | No volume threshold (Texas model) |

*(Remaining states largely track the Virginia or Connecticut pattern — see the full source for
per-state entries if a state not highlighted above becomes operationally relevant.)*

## AI-specific pressure points (recurring across states)

1. **Inference tracking and deletion** — because inferences are personal information, access/deletion
   rights extend to model-derived attributes. Build a Layer 1 register of derived inferences separate
   from raw source data (most AI systems have no such register today).
2. **Training data and the deletion right** — if a consumer's data trained a model and they request
   deletion, must you retrain? Defensible baseline: exclude the consumer's data from *future* training
   and document the exclusion. Building training-data lineage now is the hedge if regulator
   interpretation (particularly CPPA) requires more.
3. **Opt-out vs. service degradation** — non-discrimination provisions constrain how far service quality
   can drop for residents who opt out of profiling; design the non-personalized fallback as a real
   product experience, not a punishment.

## Enforcement patterns

State AGs and the CPPA concentrate on: refusing to honor deletion/access/opt-out requests; vulnerable
populations (children especially); sensitive data (health/financial/location); deception (claiming
controls work when they don't, claiming deletion when data is retained). **Coordinated multistate
actions** (CA + CT + CO + OR) are increasingly the operating model — a finding in one state seeds
inquiries in the others.

**Common failure pattern:** cookie consent / GPC honoring treated as a CMP-vendor checkbox rather than a
real-time data-flow enforcement problem — a "do not sell" toggle exists in the footer, but ad/analytics
SDKs still receive identifiers because suppression is client-side *after* the request fires. Regulators
read the network capture, not the consent banner (Sephora $1.2M 2022, DoorDash $375K 2024, Honda $632K
2025 all turned on this).

## The preemption question

Proposals like the **ADPPA** would establish a federal baseline preempting stricter state law (carve-outs
for children's/health/financial privacy); political division over preemption scope has repeatedly
prevented passage. **Plan on the patchwork continuing; don't plan on federal rescue.**

## Key takeaway

Twenty statutes don't require twenty programs — one program built to the strictest obligation per
element, jurisdiction-tagged data inventory, documented per-state applicability determinations, and
assessment artifacts kept production-ready satisfies all of them.
