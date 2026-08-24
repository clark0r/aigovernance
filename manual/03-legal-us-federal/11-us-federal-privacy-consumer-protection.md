# US Federal Privacy and Consumer Protection Law

*Audience: lawyers on any US-touching AI deployment. No comprehensive federal privacy/AI statute exists,
but 13 federal instruments form a powerful de facto baseline. Comms/surveillance statutes (VPPA, §230,
CLOUD Act, DPF, FISA §702, full ECPA, CAN-SPAM, DPPA) are in
[US Communications, Intermediary, and Surveillance Law](12-us-communications-intermediary-surveillance.md);
civil rights/employment in [Civil Rights and Employment Law Applied to AI](13-civil-rights-and-employment.md);
critical infrastructure in
[Critical Infrastructure and Federal Cybersecurity Frameworks](14-critical-infrastructure-cybersecurity.md);
sector-regulator guidance in [Sector-Specific Federal Regulators on AI](15-sector-specific-federal-regulators.md).*

## Three structural features of the US regime

1. **Sectoral fragmentation** — FTC, HHS, CFPB, FCC, DOJ, DOE, OMB, banking agencies each apply their
   own statute with limited coordination. A system spanning sectors (e.g., a health-adjacent fintech
   chatbot) must satisfy several regulators whose requirements won't fully align — build one Stack-based
   program rather than per-agency silos.
2. **Private enforcement** — FCRA, TCPA, the Wiretap Act/SCA, CFAA, and the Privacy Act carry private
   rights of action with statutory damages + fee-shifting; class-action exposure routinely dwarfs
   regulator-driven penalties, and plaintiffs' counsel monitor FTC/CFPB actions as litigation roadmaps.
3. **Statutory durability vs. executive volatility** — EO 14110 (2023) was rescinded Jan 2025 and
   replaced by EO 14179 + the Federal AI Action Plan. Statutes don't change with administrations;
   executive priorities do. **Build to the statutory floor, not the executive policy ceiling.**

## The baseline at a glance

| Statute | Citation | Regulator | AI exposure | Headline penalty (2026-adj.) |
|---|---|---|---|---|
| FTC Act §5 | 15 U.S.C. §45 | FTC | Deceptive AI claims, unfair practices, algorithmic disgorgement | $53,088/violation of consent order/rule |
| HIPAA/HITECH | 42 U.S.C. §1320d+ | HHS OCR | PHI in clinical/operational AI | $137–$2,067,813/violation/yr; up to 10yr prison |
| GLBA/Safeguards Rule | 15 U.S.C. §6801+; 16 CFR 314 | FTC/banking/SEC | Financial AI security programs | No cap; injunctive relief + redress |
| FERPA | 20 U.S.C. §1232g | ED SPPO | EdTech AI on education records | Loss of federal education funding |
| COPPA | 15 U.S.C. §6501+; 16 CFR 312 | FTC/state AGs | Children's data in AI training | $53,088/violation/child |
| FCRA | 15 U.S.C. §1681+ | CFPB/FTC | AI screening/scoring | $100-$1,000/willful; CFPB up to $1,362,567/day |
| ECOA/Reg. B | 15 U.S.C. §1691+ | CFPB/DOJ | AI credit decisioning | Up to $10,000 individual; lesser of $500K or 1% net worth (class) |
| TCPA | 47 U.S.C. §227 | FCC/private | AI voice calls/texts | $500-$1,500/call, uncapped; FCC up to $25,000 |
| CFAA | 18 U.S.C. §1030 | DOJ/private | Training-data scraping, red-teaming | Criminal; civil suits >$5,000 loss |
| Wiretap Act/SCA | 18 U.S.C. §2510-2523, 2701-2713 | DOJ/private | AI meeting assistants, chat analytics | Greater of actual damages/$100 per day/$10,000 (Wiretap); $1,000 min (SCA) |
| Privacy Act 1974 | 5 U.S.C. §552a | OMB/private | Federal agency AI systems of records | Actual damages or $1,000 min |
| FISMA/FedRAMP | 44 U.S.C. §3551+ | OMB/CISA/NIST | AI cloud services sold to government | Loss of ATO; False Claims Act exposure |
| EO 14179/AI Action Plan | EO 14179 (Jan 2025) | White House/OMB/agency CAIOs | Federal AI procurement/inventories | Procurement/performance consequences |

## FTC Act §5 — the de facto AI regulator

No new authorization needed: deception/unfairness analysis applies to model claims and conduct exactly
as to any commercial practice. Core exposure: deceptive claims about AI capability/accuracy/fairness/
training data/human review ("AI-washing"); unsubstantiated marketing claims; inadequate data security;
training data obtained via deception or in violation of consumer representations. **Algorithmic
disgorgement** — courts have ordered destruction of models/algorithms built on improperly obtained data
(Everalbum, Cambridge Analytica, WW International). No general first-violation civil penalty, but consent
orders impose 20-year compliance regimes; per-consumer/per-transaction violation counting creates
exponential exposure at scale. Rite Aid (facial recognition) and Amazon Alexa (voice-data retention) are
notable AI actions; "Operation AI Comply" (2024) and the 2025-2026 agenda prioritize generative-AI
deception, biometric misuse, children's privacy. **Practitioner note:** treat every public AI statement
(marketing pages, model cards, sales decks) as an FTC representation — misalignment with internal
evaluation results is the fastest path to both deception and unfairness theories, and the precondition
for algorithmic disgorgement.

## Sector privacy statutes: health, finance, education, children

**HIPAA/HITECH** — PHI in Covered Entities/Business Associates. BAAs must flow down to every AI
subprocessor (model-hosting, evaluation platforms) — the "HIPAA-compliant AI API" that routes prompts
through an uncovered subprocessor converts a clinical workflow into a reportable breach. Minimum-
necessary scoping for AI training sets; risk analysis under §164.308 per AI system touching ePHI (2025
proposed Security Rule NPRM would make risk analysis annual, mandate MFA, and eliminate the
addressable/required distinction). ACA §1557 (2024 final rule) prohibits algorithmic discrimination in
patient-care decision-support tools and requires "reasonable efforts" to identify/mitigate it.

**GLBA/Safeguards Rule** — "financial institution" reaches lenders, mortgage brokers, debt collectors,
tax preparers, many fintechs. Written risk assessment must explicitly address AI/ML; 8-element written
information security program (access controls, encryption, MFA for anyone accessing customer
information, secure disposal, continuous monitoring or annual pen test + biannual vuln assessment);
30-day FTC breach notification for ≥500 consumers (since May 2024). **Common failure pattern:** AI
development/training environments excluded from the formal security program because they sit outside
the production data plane — the 30-day clock starts when *any* environment holding customer information
is compromised, not just production.

**FERPA** — education records; the "school official" exception lets EdTech vendors process under
"direct control," but does **not** authorize repurposing student data as commercial model-training
material — that exceeds the original consent's scope. No private right of action federally (funding
loss is the sanction); state student-privacy statutes (CA SOPIPA, CO, NY §2-d — see
[State Biometric, Cybersecurity, and Breach Notification Law](../04-legal-us-state/17-state-biometric-cyber-breach.md))
fill the private-enforcement gap.

**COPPA** — 2025 Rule revision (effective Jun 2025, full compliance Apr 2026): expanded PII definition
incl. biometric identifiers and their derived inferences, written security program, **separate**
verifiable parental consent for third-party disclosure/targeted advertising. Repurposing children's
data for AI training exceeds original consent scope under the collection/use/retention provisions.
Major settlements: TikTok ($5.7M 2019, $92M class 2021), YouTube/Google ($170M), Epic Games ($275M),
Microsoft Xbox ($20M). Run a multi-factor "directed to children" assessment (subject matter, visuals,
language, music, animated characters) — "we're not directed to children" fails where these factors
point the other way.

## Consumer reporting and credit: FCRA and ECOA

Both statutes predate ML and apply to it without amendment; the CFPB's position (Circulars 2022-03,
2023-03) is that **model complexity is never a defense** to explanation duties.

**FCRA** — "consumer report" reaches AI-driven background/tenant/employment screening. Reasonable-
accuracy procedures, adverse-action notices with the *specific* principal reasons (boilerplate fails
even for ML), 30-day reinvestigation of disputes. If a model uses *any* feature derived from
consumer-report-type data (credit, eviction, criminal, employment history), assume FCRA applies —
"derived features carry the same predictive signal" defenses have failed. Statutory damages $100-
$1,000/willful violation + actual/punitive + fees; CFPB up to $1,362,567/day.

**ECOA/Reg. B** — adverse-action notices must state specific reasons that *accurately reflect the
model's actual decision logic* — black-box justifications fail. Fair-lending testing must include
disparate-impact analysis and a documented, **prospective** search for less-discriminatory alternatives
(LDA) — this is the single most commonly missing artifact and often dispositive in litigation. Proxy
variables (ZIP code, name, school) are the classic fair-lending trap. Damages up to $10,000 individual;
lesser of $500K or 1% net worth for class actions.

## Telemarketing, computer misuse, intercepted communications

**TCPA** — Feb 2024 FCC ruling: **AI-generated voice is "artificial voice"** under §227(b), requiring
prior express written consent for marketing calls and a start-of-call disclosure that the call uses
AI, per the pending NPRM. $500-$1,500/call or text, uncapped, no statutory ceiling on aggregate damages
— consent records are the entire compliance basis.

**CFAA** — training-data scraping and adversarial red-teaming implicate "without authorization"/
"exceeds authorized access." *Van Buren* (2021) narrowed the latter but left scraping largely governed
by the *hiQ v. LinkedIn* line (public data generally protected, bypassing technical access controls is
not). Require documented authorization scoping for internal AI security testing before it happens.

**Wiretap Act/SCA** (full ECPA treatment in
[US Communications, Intermediary, and Surveillance Law](12-us-communications-intermediary-surveillance.md)) —
AI meeting assistants/session recording/chat analytics require jurisdiction-appropriate consent (many
states are all-party); routing content to third-party AI providers without disclosed consent has
produced a real 2023-2025 litigation wave.

## The federal government's own AI: Privacy Act, FISMA, executive policy

**Privacy Act of 1974** — SORN publication + PIA (E-Government Act §208) before procuring/developing
PII-handling AI; Computer Matching and Privacy Protection Act procedural protections for covered
matching programs. OMB M-24-10/M-25-21 (2024-2025) establish a federal AI governance baseline
(CAIO designation, AI use-case inventory, impact assessments for rights-/safety-impacting AI) closely
aligned with the Stack.

**FISMA/FedRAMP** — NIST SP 800-53 controls; FedRAMP authorization gateway for AI vendors selling to
government (2025 modernization permits agency-led authorizations); False Claims Act exposure for
materially false FISMA/FedRAMP attestations (SAIC, Aerojet, Penn State precedents). Treat FedRAMP as a
floor, not a ceiling — the marginal cost of also meeting SOC 2/ISO 27001/ISO 42001 is small.

**EO 14179 (Jan 2025)** — rescinded EO 14110; reframed federal AI policy around competitiveness/
deregulation but *carried over* the CAIO/inventory requirements. Illustrates executive volatility: orgs
that built to EO 14110 found those specific directives nullified within 15 months, while every statute
in this file survived unchanged.

## Working the federal baseline as one program

Recurring convergence points across all 13 instruments:
- **Data classification is the master switch** — a single Layer 1 inventory with statutory tags
  (PHI/GLBA-customer-info/FERPA-education-record/COPPA-children's-data/consumer-report-equivalent) is
  the single highest-leverage artifact.
- **Explainability is a legal requirement**, not an engineering preference, wherever FCRA/ECOA adverse
  action applies — design it at model selection, not at notice-drafting time.
- **Consent logs decide cases** — TCPA, COPPA, Wiretap Act litigation turns almost entirely on consent
  record quality; treat consent capture/propagation/withdrawal as a Layer 4 control with Layer 5
  evidence output.
- **Vendor chains inherit obligations** — BAAs (HIPAA), service-provider oversight (Safeguards Rule),
  "direct control" (FERPA), subprocessor disclosure (Wiretap Act) all flow down contractually.
- **Deadlines are short and specific** — HIPAA breach 60 days; GLBA/FTC 30 days (≥500 consumers); FCRA
  disputes 30 days; ECOA adverse action 30 days; do-not-call 30 days; CAN-SPAM opt-out 10 business days
  (see [US Communications, Intermediary, and Surveillance Law](12-us-communications-intermediary-surveillance.md)).
  Build monitoring/response to these clocks, not to internal comfort.

**Common failure pattern:** building a mini-program per regulator that has already sent a letter, and
nothing for statutes that haven't yet produced an inquiry — exactly the statutes with private rights of
action (FCRA, TCPA, Wiretap/SCA, CFAA) are least likely to announce themselves in advance. Inventory
first, map every system to every applicable statute, then consolidate controls by Stack layer.
