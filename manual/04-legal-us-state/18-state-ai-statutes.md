# State AI Statutes

*Audience: lawyers for any org whose AI reaches consumers, employees, patients, or job candidates in
the US. Comprehensive state privacy laws with AI-relevant profiling provisions are in
[Comprehensive State Privacy Laws](16-comprehensive-state-privacy-laws.md).*

## The landscape and its convergence

State legislatures have moved aggressively into AI-specific regulation absent federal legislation.
Despite textual variation, three structural elements recur:
1. **Consequential-decision impact assessments** — Colorado (annual + post-modification), Texas (state
   agencies), pending CT/MA/NY frameworks. Wherever AI makes/substantially contributes to a decision
   about employment, credit, housing, healthcare, insurance, education, government services, or legal
   services, expect this.
2. **Deployer transparency obligations** — notice AI is in use, explanation, appeal rights (CO, TX, UT,
   IL, NYC, CA in varying combinations).
3. **Developer documentation duties** — Colorado requires developers to equip deployers for their own
   compliance; CA AB 2013 makes training-data documentation public; SB 53 makes frontier safety
   practices a published framework.

**Intake questions for any AI system:** does it make/substantially influence a consequential decision?
Generate content presented to consumers/patients/voters? Evaluate candidates/employees? Use/reproduce a
person's voice or likeness? A "yes" to any pulls the system into at least one regime below.

## Enacted statutes at a glance

| Statute | Jurisdiction | Effective | Headline penalty |
|---|---|---|---|
| Colorado AI Act (SB 24-205) | CO | Feb 1, 2026 (delayed; phased) | Up to $20,000/violation (AG only) |
| TRAIGA | TX | Jan 1, 2026 (substantive) | $10,000-$200,000/violation |
| AB 2013 (training-data transparency) | CA | Jan 1, 2026 | UCL civil penalties + equitable relief |
| SB 942 (AI provenance/transparency) | CA | Jan 1, 2026 | $5,000/violation/**day** |
| AB 3030 (healthcare GenAI disclosure) | CA | Jan 1, 2025 | Medical Board discipline + civil |
| SB 53 (frontier AI transparency) | CA | Signed Sep 2025; phased 2026 | Scaled to frontier developer revenue |
| AB 2885 + companion package | CA | Various 2025-2026 | Varies |
| NYC Local Law 144 | NYC | Jan 2023; enforcement Jul 2023 | $500 first; $500-$1,500 subsequent |
| Illinois AI Video Interview Act | IL | 2020, amended 2022 | Employment-law remedies, class exposure |
| Illinois HB 3773 | IL | Jan 1, 2026 | Full IL Human Rights Act remedy set |
| Tennessee ELVIS Act | TN | Jul 1, 2024 | $25,000 statutory damages/violation + misdemeanor |
| Utah AI Policy Act | UT | May 1, 2024 (initial) | Up to $2,500/violation |

## Colorado AI Act (SB 24-205) — the first comprehensive consequential-decision law

Applies to developers and deployers of **high-risk AI systems**: those that make or are a substantial
factor in a consequential decision in employment, education, financial services/lending, essential
government services, healthcare, housing, insurance, or legal services. EU-AI-Act-inspired but sitting
inside US private-litigation exposure.

- **Developers:** documentation for deployers (intended uses, known/foreseeable harms, training-data
  summaries, evaluation results, mitigations); public high-level summary of high-risk systems developed;
  **AG notification within 90 days** of discovering the system caused or is reasonably likely to have
  caused algorithmic discrimination.
- **Deployers:** risk-management policy/program; **annual** impact assessment + after any intentional/
  substantial modification; consumer notice for consequential decisions + explanation + correction
  right; **appeal right including human review** where feasible; reasonable care against algorithmic
  discrimination.
- **Enforcement:** AG only, no private right; deceptive-trade-practice violation, up to $20,000/
  violation. **Rebuttable presumption of reasonable care for NIST AI RMF compliance** — the cheapest
  liability shield available under any US AI statute.
- **Practitioner note:** the 90-day AG-notification clock starts at *discovery of facts indicating it's
  reasonably likely*, not a formal legal conclusion — fairness-monitoring alerts and complaint patterns
  can start it. Wire Layer 4 monitoring directly into legal escalation.

## Texas TRAIGA — prohibitions + narrower consequential-decision framework

Combines: prohibitions on certain social scoring/harmful manipulation/sensitive-attribute biometric
categorization (mirroring select EU AI Act prohibitions); deployer notice/explanation/appeal for
consequential AI uses; state-agency AI inventory/impact-assessment/reporting to a Texas AI Council; a
**regulatory sandbox** with limited liability protection. Penalties $10,000-$200,000/violation
(scaling by curable/uncurable/prohibited-practice), with cure periods for first-time violations of
certain provisions — build compliance so defects discovered internally can be documented/remediated/
evidenced within the cure window.

## California's package (assembled from targeted statutes, not one omnibus act)

| Statute | Core requirement | AI-specific note |
|---|---|---|
| **AB 2013** | Public posting of generative-AI training-data documentation (sources, time period, whether copyrighted/personal/purchased/licensed data) before public availability | Generate the disclosure from the Layer 1 inventory of record, not from memory — divergence is simultaneously an AB 2013 violation, a UCL deception theory, and copyright-litigation impeachment material |
| **SB 942 (AI Provenance/Transparency Act)** | For providers w/ ≥1M monthly CA users: free AI-detection tool; visible + latent (C2PA-style) content disclosures | $5,000/violation/**day** — a systemic watermarking defect at high volume accrues fast |
| **AB 3030** | Healthcare provider disclosure when generative AI produces patient-facing clinical communications (human-reviewed messages exempt) | The exemption only works if review is real and provable — log reviewer identity, duration, edit activity |
| **SB 53 (Transparency in Frontier AI Act)** | Published Frontier AI Framework; critical safety incident reporting to AG; whistleblower protections | Successor to **vetoed SB 1047** (vetoed Sep 2024 for focusing on model size over risk profile) — SB 53 narrower but operative |
| **AB 2885 + companions** | Standardizes the AI definition across CA code; AB 2655/2839 (election deepfakes); AB 1836 (deceased-personality digital replicas); AB 2602 (employment digital-replica consent) | The connective tissue for the whole package |

## Employment AI: NYC and Illinois

**NYC Local Law 144** — annual **independent bias audit** of Automated Employment Decision Tools
(AEDTs), calculating selection rate/impact ratio by sex and race/ethnicity incl. intersectional
categories; public posting of the audit summary; **10-business-day advance candidate notice**. The
"substantially assist" test is broad — reaches any tool whose score is materially weighed, not just full
automation. $500 first violation, $500-$1,500 subsequent, **each affected candidate can be a separate
violation**. Only 18 of 391 covered employers had posted required audits as of a 2024 analysis —
compliance discipline is the differentiator, not statutory ambiguity.

**Illinois AI Video Interview Act** — notice + consent before AI-analyzed video interviews, access
restricted to authorized persons, **30-day destruction** on applicant request, annual demographic
reporting if AI is *solely* relied upon for interview eligibility. Private right of action; often pleaded
alongside BIPA (see
[State Biometric, Cybersecurity, and Breach Notification Law](17-state-biometric-cyber-breach.md)).

**Illinois HB 3773** (eff. Jan 1, 2026) — amends the IL Human Rights Act: AI use in employment decisions
having a **disparate-impact effect** on protected classes is a civil-rights violation (effects test,
intent irrelevant), and explicitly **prohibits ZIP codes as a proxy** for protected classes. Full IHRA
remedy set, private right of action, uncapped damages. **Common failure pattern:** removing the literal
ZIP-code field while leaving correlated features (commute distance, store location, regional salary
bands) — the prohibition targets proxies, and a fairness program checking only for the literal field
misses the exposure.

## Likeness, voice, and consumer protection

**Tennessee ELVIS Act** — extends right of publicity to voice/likeness in the AI context; prohibits both
unauthorized publication **and** knowingly distributing a tool whose *primary purpose* is unauthorized
voice/likeness generation (reaches developers/platforms, not just end users). $25,000 statutory
damages/violation + misdemeanor criminal exposure. Consent-gated architecture (only clone voices with
documented authorization) is the practical safe harbor.

**Utah AI Policy Act** — clear/conspicuous disclosure of generative-AI interaction in regulated
occupations (healthcare, legal); disclosure on request otherwise; **no defense based on AI involvement**
— liability attaches as if the entity made the statements directly ("the chatbot said it" is not a
defense); a regulatory sandbox. Up to $2,500/violation, multiplying across high-volume chatbot
interactions.

## Pending and emerging frameworks (readiness deadlines with uncertain dates)

- **Massachusetts** — comprehensive privacy bill (S25/H80, among the most consumer-protective pending —
  strict minimization, sensitive-data sale ban) + AI Strategic Plan (EO 25-1, state-agency governance).
- **Connecticut SB 2** — repeatedly near-passed Colorado-style consequential-decision framework; PA
  23-16 (already in force) sets state-agency AI inventory/assessment obligations reaching vendors via
  contract.
- **New York State** — LOADING Act (state-agency AI governance) + A 7634 (algorithmic discrimination),
  both consciously building on the Local Law 144 bias-audit architecture.
- **State healthcare AI wave** — CA AB 3030 leads; OK, FL, GA, and others considering/enacting
  physician-oversight, patient-disclosure, and clinician-review-of-AI-denial requirements. The
  clinician-review-of-denials element is spreading fastest.

## Synthetic content: deepfakes and NCII

**Election deepfakes** (CA, TX, MI, MN, and others) — prohibit/require disclosure of materially
deceptive synthetic media of candidates within 30/60/90-day windows of an election (some year-round);
satire/news/disclosed-parody exemptions vary by state. Build a jurisdiction-by-jurisdiction election-date
table and drive content-policy tightening from it automatically.

**Non-consensual intimate imagery (NCII)** — 47+ state statutes now cover **synthetic** (AI-generated)
NCII, layered with the **federal Take It Down Act (2025)**, which requires platforms to honor victim
takedown requests within **48 hours**. Log the full request lifecycle (arrival, removal, all-copies
reached) as a Layer 5 compliance record — compliance without an evidence trail can't be demonstrated on
inquiry.

## Key takeaway

Five effective dates cluster in a 13-month window: AB 3030 (Jan 2025); TRAIGA, AB 2013, SB 942, IL HB
3773 (all Jan 2026); Colorado AI Act (Feb 2026). An org not yet compliant is accruing *present* exposure
at per-violation/per-day/per-candidate rates. Sequence remediation: private-right-of-action statutes
first (IL, TN) → per-day penalty regimes second (SB 942) → AG-enforced program mandates third (CO, TX).
