# The United Kingdom and the Americas

*Audience: counsel/privacy officers for AI operations touching the UK, Canada, or Latin America.*

## Orientation: two divergences from the EU pattern

**UK divergence** — retained the GDPR wholesale post-Brexit, now reforming selectively (Data (Use and
Access) Act 2025 widens ADM/legitimate-interest pathways while keeping the accountability core). On AI
specifically, the UK rejected horizontal legislation for a **sectoral, principles-based model**: existing
regulators (FCA, ICO, Ofcom, MHRA, CMA) apply five cross-sectoral principles within their own remits,
backstopped by the AI Safety Institute's voluntary frontier evaluations. Practical consequence: EU-
compliant systems are almost always UK-deployable, but the UK offers flexibilities orgs that architect
only to the EU baseline leave unused.

**Latin America divergence** — GDPR-inspired but administratively distinctive: database-registration
regimes (Colombia, Peru, Uruguay, Costa Rica), sectoral enforcement absent a unified regulator
(Dominican Republic), and reform waves at different maturity stages (Chile's Dec 2026 deadline,
Argentina's pending modernization, Brazil's pending AI bill). Canada sits between the patterns:
principles-based federal PIPEDA awaiting modernization, with **Quebec Law 25 functioning as the de facto
national floor for AI obligations**.

## Regional comparison at a glance

| Jurisdiction | Principal law | Regulator | Max penalty | AI instrument |
|---|---|---|---|---|
| UK | UK GDPR/DPA 2018/DUAA 2025 | ICO | £17.5M or 4% turnover | Sectoral principles; AISI; ICO AI Code (developing) |
| UK | Online Safety Act 2023 | Ofcom | £18M or 10% qualifying revenue | Recommender/AI-content risk assessment |
| Canada | PIPEDA; Quebec Law 25 | OPC; CAI (QC) | QC: CAD $25M or 4% | QC ADM consent+human review; Bill C-36 (2nd reading) |
| Brazil | LGPD | ANPD | BRL 50M/infraction or 2% | Pending PL 2338/2023 (Marco Legal da IA) |
| Mexico | LFPDPPP | INAI (transitioning) | ~MXN 32M | INAI guidance |
| Argentina | Ley 25.326 | AAIP | PDPL fines (reform pending) | AAIP ADM guidance |
| Chile | Law 19.628, amended by 21.719 | DPA (forming) | Up to 4% turnover (**from Dec 1, 2026**) | ADM opposition right in reform |
| Colombia | Law 1581/2012 | SIC | ~2,000 min. wages (~USD 1.4M+) | SIC ADM guidance |
| Peru / Uruguay / Costa Rica | Laws 29733 / 18.331 / 8968 | ANPDP / URCDP / PRODHAB | Admin fines | Registration-centric, no AI-specific instrument yet |
| Dominican Republic | Law 172-13 | Sectoral (no unified DPA) | Sectoral | None yet |
| Panama | Law 81/2019 | ANTAI | USD 100,000+ | ANTAI AI-relevant guidance |
| Ecuador | LOPDP 2021 | DPA (forming) | Up to 1% revenue | ADM rights in statute |

## United Kingdom — three overlapping instruments

**UK GDPR/DPA 2018/DUAA 2025:** DUAA reforms of direct AI consequence — an Art. 22 reform widening
lawful ADM pathways (legitimate interest, contract, or consent, not just the narrow original menu) while
*retaining* transparency, human-review-on-request, and contest-right safeguards, with tighter
restrictions where special-category data is involved; a "recognised legitimate interests" framework
(national security, safeguarding, crime prevention presumed legitimate, no balancing test needed).
**Common failure pattern:** relaxing Art. 22 controls across the board after learning of DUAA flexibility
— the reformed regime still requires the safeguards, just via a wider basis menu; loosen deliberately and
document the register of divergences (which recognised-legitimate-interest / DUAA pathway was relied on
for which system).

**Sectoral AI regulation:** five cross-sectoral principles (safety; transparency/explainability;
fairness; accountability/governance; contestability/redress) operationalized by sector regulators — the
applicable "UK AI law" is whatever your sector regulator says, read through these principles. The AI
Safety Institute conducts voluntary pre-deployment frontier-model evaluation (a strong governmental
expectation, not legally mandated, for major releases). The 2025 AI Opportunities Action Plan signals
future legislation for the *most powerful* models while holding the sectoral line elsewhere. Map your UK
AI estate to **regulators**, not risk tiers — a credit model answers to the FCA, a triage tool to the
MHRA, a recommender to Ofcom, and all of them to the ICO for personal data.

**Online Safety Act 2023:** risk assessments for illegal content + content harmful to children (**childsafety duties effective Jul 2025**); AI-generated illegal content and recommender-system amplification
are explicit risk-assessment subjects; age assurance carries its own UK-GDPR considerations; scope
triggers on links to the UK, no UK establishment required. Up to £18M or **10%** worldwide qualifying
revenue (exceeds UK GDPR's 4%) + senior-management criminal liability. **Common failure pattern:** a risk
assessment identifying AI-content/recommender risks with no corresponding detection/labeling/throttling
controls built and no evidence trail linking assessment to system change — Ofcom's record-keeping duties
are designed to expose exactly this gap.

## Canada — PIPEDA, Quebec Law 25, and Bill C-36

Bill C-27 (incl. the never-enacted AIDA) died on the Order Paper Jan 2025; **Bill C-36 (PPCDA)**,
introduced Jun 2026 and at second reading as of Aug 2026, is the current reform vehicle (automated-
decision transparency, stronger enforcement, children's-data protections, a new regulator). In the
meantime, **Quebec Law 25** is the de facto Canadian AI privacy floor: consent **before** automated
decisioning of personal data producing significant effects, transparency about the decisioning, and a
**right to human review** — CAD $25M or 4% worldwide turnover, no automatic cure since Jan 1, 2025.
**Practitioner note:** build Canadian AI compliance to Quebec first — it's stricter than PIPEDA, stricter
than most US state ADM opt-outs, and operationally similar to GDPR Art. 22. An org satisfying Quebec's
consent+human-review+PIA regime satisfies every current Canadian jurisdiction and is well-positioned for
Bill C-36.

## Brazil — LGPD and the Marco Legal da IA

LGPD's **10 enumerated lawful bases** (broader than GDPR's six — includes credit protection and research
bases with no GDPR equivalent) require basis-specific documentation; can't port a GDPR lawful-basis
analysis unexamined in either direction. DPIR/RIPD (Data Protection Impact Report) required for high-
risk processing — ANPD increasingly requests these on inquiry, so the assessment must exist *before* the
inquiry does. **Pending PL 2338/2023** would be the most comprehensive AI framework in the Americas if
enacted (risk-based, explicit prohibitions, high-risk categorization, national AI authority) — track its
risk categories against your EU AI Act classification work, since the architectures are convergent.
Penalties: BRL 50M/infraction or 2% Brazil revenue, + daily penalties for continuing violations.

## The rest of Latin America — registration-centric compliance

Colombia (SIC RNBD registration, ADM guidance, active enforcement), Peru (ANPDP database registration),
Uruguay (URCDP registration + 2019 DPO reform, first South American EU-adequate jurisdiction), Costa
Rica (PRODHAB registration, consent-focused enforcement), Dominican Republic (sectoral enforcement, no
unified regulator — a fintech deployment answers to Superintendencia de Bancos and should build its
evidence pack to banking-supervision conventions), Panama (72hr breach notice, DPO for certain
processing), Ecuador (LOPDP, explicit ADM rights + DPO/DPIA obligations). **The recurring practical
obligation across this group is database registration** — cheap to do, expensive to have missed, since
it's the first thing a Latin American regulator checks; assign one owner to keep registrations
synchronized with the Layer 1 data inventory.

**Chile is the deadline to watch:** Law 21.719 (2024 reform) takes the country from one of the region's
lightest regimes to one of its heaviest **on December 1, 2026** — independent DPA, ARCO+ rights incl.
**automated-decision opposition**, DPO, RoPA, breach notification, up to 4% turnover. Organizations with
Chilean operations should be in active preparation now; the reform's structure maps nearly 1:1 onto a
GDPR baseline, so a gap assessment against the EU program is the fastest route to readiness.

## Compliance strategy across the region

Four workstreams, not fifteen programs:
1. **A GDPR-derivative core** (UK, Brazil, Chile from Dec 2026, Ecuador, Uruguay, Quebec) — one program
   on lawful basis / data subject rights / DPO or privacy officer / impact assessment / 72hr-class
   breach response; jurisdiction files capture the deltas.
2. **A registration ledger** (Colombia, Peru, Uruguay, Costa Rica, Argentina in transition).
3. **An ADM rights matrix** — consent-before-decisioning (Quebec), opposition rights (Chile, Ecuador),
   explanation-supporting documentation (Argentina), reformed Art. 22 (UK) — one matrix of which systems
   make significant-effect decisions about which populations and which right each jurisdiction attaches
   (the same matrix your EU/US-state programs need, extended by rows).
4. **A watch list with dates** — Chile Dec 1, 2026 (fixed statutory deadline, leads the list); Brazil PL
   2338/2023; Canada Bill C-36; Argentina reform; Mexico regulator transition; possible UK frontier-model
   legislation.

## Key takeaway

The UK rewards documenting the flexibilities you use; Latin America rewards registering/appointing/
notifying on time; Canada rewards building to Quebec. Layer 5 is the region's center of gravity —
registrations, DPIRs, PIAs, DPO designations, breach records are what every regulator from the ICO to
the SIC to PRODHAB actually inspects.
