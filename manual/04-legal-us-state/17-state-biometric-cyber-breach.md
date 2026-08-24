# State Biometric, Cybersecurity, and Breach Notification Law

*Audience: lawyers assessing litigation/enforcement exposure for AI touching biometric data, health
inferences, or security-regulated information. These regimes apply **no matter what** — mostly no
consumer-volume threshold, and several carry private rights of action independent of any comprehensive
privacy law.*

## Why this file is different

1. **No threshold shelter** — BIPA applies to any private entity obtaining biometric identifiers of an
   Illinois resident; the SHIELD Act/201 CMR 17 apply to any entity holding covered info of a NY/MA
   resident; breach notification applies wherever an affected individual resides. Small AI vendors that
   escape every threshold in
   [Comprehensive State Privacy Laws](16-comprehensive-state-privacy-laws.md) remain fully exposed here.
2. **Litigation, not just enforcement** — BIPA has a private right of action with statutory damages and
   **no injury requirement** (Rosenbach v. Six Flags, 2019), making it the leading US privacy class-
   action vehicle. MHMDA and several breach statutes also carry private rights.
3. **Strictest-standard-or-geofence** — for biometrics, Illinois supplies the strictest binding consent
   standard; applying BIPA-grade consent nationally is a common design choice rather than attempting
   state-level segmentation of a vision pipeline.

## Biometric regimes at a glance

| Regime | Enforcement | Consent standard | Retention limit | Headline exposure |
|---|---|---|---|---|
| **BIPA (IL)** | Private right only | Written notice + written executed consent *before* collection | Public written retention/destruction policy | $1,000 negligent/$5,000 intentional per violation + fees; **2024 amendment: one violation per individual per type**. Facebook $650M, TikTok $92M, Google $100M, BNSF $75M |
| **CUBI (TX)** | AG only, no private right | Prior informed consent before capture, commercial purpose | ≤1yr after purpose expires | Up to $25,000/violation, **counted per individual/image**. Meta $1.4B (2024), Google $1.375B (2025) — largest privacy settlements in US history |
| RCW 19.375 (WA) | AG (Consumer Protection Act) | Notice+consent before **enrollment** in a commercial database | Limited to service necessity | Up to $7,500/violation |
| CPA biometric provisions (CO) | AG | Notice+consent before collection; written policies | 24 months unless extended | Up to $20,000/violation (CPA framework) |

**BIPA:** applies even where source images were public and the original collection purpose was
unrelated — models computing face embeddings/voiceprints/gait analysis are in scope. **Common failure
pattern:** a computer-vision feature trained on public images ships globally with the face-geometry
computation running in production for Illinois users, with no written-consent infrastructure because
no one classified the system as a biometric pipeline. Build the biometric classification check at the
model-card stage.

**CUBI:** for years treated as dormant (no private right of action) until the Texas AG's enforcement
campaign proved otherwise. Reaches biometric identifiers *derived* from images even where original
collection purpose differed. One-year retention limit requires deletion automation tied to purpose-end
events, not calendar cleanup.

**Colorado** (2024 CPA amendments): first US state to extend privacy protection to **neural data**
(treated as sensitive, opt-in required). Biometric obligations apply **independently of general
consumer status**.

## Consumer health data — Washington MHMDA

First-mover state consumer-health-data law (eff. Mar/Jun 2024), reaching far beyond HIPAA-covered
entities: fitness/wellness/mental-health/fertility apps, and critically, **any AI system inferring
health-related information from non-health data**. A model deriving health attributes from purchase
history, search behavior, or location creates "consumer health data" within the statute's meaning —
the inference itself is the regulated event, no health data collection required. Requires a distinct
Consumer Health Data Privacy Policy, affirmative consent for collection/sharing, heightened "valid
authorization" for sale, a shared-categories/recipients list, access/deletion/consent-withdrawal rights,
and a **prohibition on geofencing in-person healthcare services**. Private right of action under WA's
Consumer Protection Act; up to $7,500/violation. Nevada (SB 370) and Connecticut have followed the
model. If your AI infers any health-related attribute (fertility, mood, addiction risk, sleep quality,
chronic condition), assume MHMDA scope and build a separate consent flow.

## State cybersecurity regulation

| Regime | Scope | Key AI-relevant requirement | Penalty |
|---|---|---|---|
| **NY SHIELD Act** | Any entity holding NY resident private info | Reasonable safeguards; breach notice for "access" (not just acquisition) to private info incl. biometric/credentials | Up to $5,000/violation |
| **NY DFS 23 NYCRR Part 500** | NY-licensed financial services entities | Written cybersecurity program, CISO, annual risk assessment (2024 guidance explicitly covers AI risk, calls out AI-inference-as-a-service as high-attention 3rd-party category), MFA, encryption, **72hr cybersecurity-event notification** | Up to $1,000/violation; PayPal $40M (2025) |
| **Massachusetts 201 CMR 17** | Anyone owning/licensing MA resident personal info | Written Information Security Program (WISP) incl. 3rd-party service-provider oversight; encryption in transit/on portable devices | Up to $5,000/violation (M.G.L. c.93A) |

**Part 500 practitioner note:** treat it as the de facto US financial-services AI cybersecurity floor —
if your program satisfies Part 500 it likely satisfies most other state/sectoral cyber requirements. The
CISO personal-certification requirement creates accountability that survives executive turnover.
**Common failure pattern:** third-party AI providers mapped under §500.11 only at procurement, refreshed
annually as paperwork — the 2024 AI guidance + 72hr clock require *continuous* monitoring, since a
model-hosting-provider breach requires determining within 72hr whether nonpublic info was implicated.

## The breach-notification patchwork (54 jurisdictions)

No comprehensive federal breach law; state-of-residence of the affected individual governs, not entity
headquarters or data location. AI training-data/inference-log breaches are subject to **every**
jurisdiction where affected individuals reside.

| Divergence point | Range | Examples |
|---|---|---|
| Trigger event | Unauthorized acquisition vs. mere access | NY SHIELD reaches access |
| Covered data | Name+SSN/DL/financial baseline, expanding | IL adds biometric; MD adds passport (+genetic from 2025); CT adds biometric + email+password |
| Timing | "Without unreasonable delay" to fixed 30/45/60/90-day clocks | NY DFS: 72hr to regulator |
| Regulator notice | ~30 jurisdictions require it, varying triggers | CA AG + web posting at 500+; NY AG/CPB/State Police at 5,000+ |
| Content prescriptions | Free-form to mandated elements | MD, IA specify required content |
| Remediation | None to mandatory credit monitoring | CA, CT require it for SSN breaches |
| Private enforcement | AG-only to private right | CA, AK, IL, MA |

**AI-relevant novelty:** training-data breaches (data may be derived rather than directly collected) and
prompt-log breaches (may contain personal info never previously inventoried) present analyses most
playbooks haven't run. Build the breach playbook with explicit AI-incident classifications mapped to
each state's trigger language, and **inventory prompt logs as a personal-information store before the
incident.**

## Student privacy (predates and operates alongside FERPA — see
[US Federal Privacy and Consumer Protection Law](../03-legal-us-federal/11-us-federal-privacy-consumer-protection.md))

| Statute | Core prohibition | AI relevance |
|---|---|---|
| CA SOPIPA | No targeted ads/non-school profiling/sale of K-12 student data | A recommender modeling students beyond school purposes violates it at the feature-engineering stage |
| CO Student Data Transparency & Security Act | Same, + first regulation of free EdTech ("on-demand providers") | Free AI study aids/classroom chatbots enter this channel |
| NY Education Law §2-d | Contractors must adopt NIST CSF; parental inspect/challenge rights; mandatory breach notice | Loss of state-contract eligibility is the operative sanction |
| Pending NY biometric bill (S 1144/A 2434) | BIPA-modeled, would add a private right of action | Given BIPA's litigation history, enactment would be a step-change in exposure |

## Key takeaway

These regimes have no threshold shelter, the sharpest private enforcement in US privacy law, and
settlement records ($1.4B Texas, $650M Illinois) dwarfing comprehensive-law penalties. Treat biometric
classification, health-inference scoping, and breach readiness as first-class governance obligations;
build to the strictest expression of each control (BIPA consent, Part 500 cybersecurity, shortest
applicable breach clock).
