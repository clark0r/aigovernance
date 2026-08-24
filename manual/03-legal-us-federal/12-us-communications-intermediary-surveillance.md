# US Communications, Intermediary, and Surveillance Law

*Audience: lawyers for AI providers/platforms/enterprise deployers whose systems capture, store,
transmit, or analyze communications/device telemetry, or whose data flows cross the Atlantic.*

## Why this body of law reaches AI

These statutes were written for other technologies and applied to AI through litigation, not amendment:
VPPA (video rental records → analytics pixels), ECPA (1986 → AI meeting assistants), §230 (message
boards → generative-AI output liability). Application questions are live and circuit-split-prone, which
makes **contemporaneous Layer 5 documentation** unusually valuable — the record built today determines
which side of an unsettled doctrine you land on. Enforcement is dominated by **private plaintiffs**
(VPPA, ECPA carry statutory damages + fee-shifting, arriving without regulatory warning). Governmentaccess law (CLOUD Act, FISA §702) is, practically, a *commercial* compliance problem: it drives EU
transfer risk, enterprise customer diligence, and architecture decisions about localization/encryption/
key custody.

## Instruments at a glance

| Instrument | Citation | Enforcement | AI exposure | Headline consequence |
|---|---|---|---|---|
| VPPA | 18 U.S.C. §2710 | Private right only | Recommenders, pixels on video pages | $2,500 statutory damages/violation |
| §230 CDA | 47 U.S.C. §230 | Immunity defense | Generative AI output liability | Loss of immunity, not a penalty |
| CLOUD Act | 18 U.S.C. §2713; ECPA §2703 | DOJ; foreign govts via agreement | Cross-border data production | Contempt; ECPA civil/criminal |
| EU-US DPF | Adequacy decision Jul 2023; EO 14086 | FTC; EU DPAs; DPRC | EU-to-US training/inference flows | FTC §5 enforcement; loss of certification |
| FISA §702 | 50 U.S.C. §1881a | FISC; ODNI | Compelled provider assistance | Contempt/compulsion remedies |
| ECPA (all 3 titles) | 18 U.S.C. §§2510-2523, 2701-2713, 3121-3127 | DOJ; private | Interception, stored data, metadata | Greater of actual damages/statutory minimums + fees |
| CAN-SPAM | 15 U.S.C. §§7701-7713 | FTC/FCC/state AGs/ISPs | AI-generated marketing email | Up to $53,088/email |
| DPPA | 18 U.S.C. §2721 | DOJ; private | Motor-vehicle records in AI underwriting | Greater of actual damages or $2,500 + punitives |

## ECPA — comprehensive view

Three components: **Wiretap Act** (interception in transit; one-party or all-party consent by state),
**Stored Communications Act** (compelled-disclosure process — warrant for content, subpoena/court order
for non-content by age), **Pen Register Act** (metadata collection court-order requirement, interacting
with *Carpenter v. US* (2018) on when compelled metadata needs a warrant). For AI: three distinct
exposures — interception at capture, disclosure at storage/vendor routing, metadata at telemetry
design. A 2023-2025 class-action wave targets AI chat-replay/session-recording/meeting-assistant tools
that route content to third-party AI providers without disclosed consent. **Practitioner note:**
inventory telemetry, not just content — device identifiers, interaction timestamps, and addressing
metadata feeding AI personalization are the least-documented data flows and are exactly what the Pen
Register Act and post-*Carpenter* doctrine reach.

## VPPA — video viewing data and the analytics-pixel problem

Prohibits "video tape service providers" from knowingly disclosing PII identifying a person as having
requested specific video content, without written consent distinct from other legal terms. Modern
litigation applies this broadly to streaming services, video-embedded news pages, and — most
consequentially — **analytics pixels (Meta Pixel, Google Analytics)** transmitting viewing data
alongside identifiers. No agency gatekeeper: exposure scales directly with traffic × $2,500/violation.
Settlements: Hulu $7M, NBCUniversal $30M. **Common failure pattern:** the core streaming product is
audited for VPPA compliance while the marketing site/support portal/help center embed video with
third-party pixels unreviewed, and the recommendation team separately exports viewing histories to a
model-training vendor — each surface is a separate disclosure theory pleaded together.

## §230 CDA — intermediary liability and generative AI

Immunizes providers for third-party content (§230(c)(1)) and good-faith moderation (§230(c)(2)). The
**central open question of the post-ChatGPT era**: is a generative model's output the provider's *own*
content (no immunity) or third-party content passed through? Courts have generally treated chatbot-
generated defamation as actionable against the AI provider where it materially contributed to the
content; recommendation algorithms remain partly protected; product-liability/defect theories are
increasingly used to route around §230 entirely. **Working assumption: build the Layer 2 defense
record** (system-prompt versions, output-filter configs, moderation policies, dated and retained) —
don't build a content strategy assuming §230 covers model outputs.

## Cross-border government access and the transatlantic bridge

Read as one system: the **DPF is the bridge**, and **CLOUD Act + FISA §702 are why it keeps getting
inspected**.

- **CLOUD Act:** US providers must produce data within their possession/custody/control **regardless of
  where stored** ("possession, custody, control" follows the corporate entity, not the datacenter — EUregion hosting doesn't remove the obligation). Bilateral executive agreements (US-UK model) let foreign
  governments compel data from US providers with reciprocity.
- **EU-US Data Privacy Framework (adequacy, Jul 10, 2023):** third-generation transfer mechanism after
  Safe Harbor (struck 2015) and Privacy Shield (struck 2020, Schrems II). Pending Schrems III challenge;
  the underlying FISA surveillance architecture that prompted Schrems II remains unchanged. **Structure
  every EU-to-US AI flow with a dual basis** — DPF certification where certified, SCCs + a completed
  transfer impact assessment shelf-ready as fallback. Map which flows are training data vs. inference
  traffic vs. support telemetry, since a Schrems III invalidation would force flow-by-flow triage under
  time pressure.
- **FISA §702:** the April 2024 Reforming Intelligence and Securing America Act reauthorized §702
  through 2026 and **expanded the "electronic communication service provider" definition** — entities
  that never considered themselves communications providers (datacenter operators, some cloud/AI
  infrastructure) may now fall within the compulsion perimeter. Assess ECSP status *before* first
  receipt of a directive, not after.

**Common failure pattern:** an org certifies to the DPF, lists "cloud hosting" in its onward-transfer
disclosure, then routes EU personal data through model-training vendors/evaluation platforms/annotation
contractors that appear nowhere in the notice — each is an independent accountability-for-onward-
transfer violation (FTC §5), and surfaces in exactly the customer-diligence exercise the certification
was meant to satisfy. Keep the DPF notice synchronized with the *live* subprocessor list.

## Commercial electronic communications

**CAN-SPAM** — no misleading headers/subject lines, ad identification, physical address, functional
opt-out honored within **10 business days**, and **vicarious liability** for what your AI email-campaign
vendor does on your behalf. Up to $53,088/email, each non-compliant send a separate violation — at
AI-personalized-campaign volumes this reaches material figures in a single send. Add a compliance-lint
pass before send: ad-identification present, physical address present, functional unsubscribe, subject
line matches body.

## Motor vehicle records and the sectoral remainder

**DPPA** — motor-vehicle-record data may be used only for **enumerated permissible purposes**; the
limitation *travels with the record into every downstream model* — data lawfully obtained for one
purpose doesn't become general-purpose training data by passing through a data broker. Private right of
action; greater of actual damages or $2,500 + punitives. Analogous sectoral statutes: Cable
Communications Privacy Act, Right to Financial Privacy Act, Telecommunications Act CPNI rules — same
purpose-limitation logic.

## Working this chapter as one exposure map

- Every communications-adjacent AI feature needs a named legal basis for capture, a mapped recipient
  list, and a retention limit (addresses ECPA + VPPA + DPF onward-transfer simultaneously).
- Every EU-to-US flow needs a primary transfer mechanism + an executed fallback.
- Every generative-output surface needs a Layer 2 design record (§230 protection is narrowing).
- Every outbound-messaging channel needs real-time suppression enforcement (TCPA + CAN-SPAM short
  clocks, per-message penalties, multiplied by AI scale).
- Every sectoral data source (DPPA, cable, financial, CPNI) carries its purpose limitation into the
  model — it doesn't launder into "training data" via a broker.

**Common failure pattern (chapter-wide):** exposure here is discovered by outsiders in a predictable
order — plaintiffs' counsel find the pixels/meeting bots first, enterprise customers find government-
access gaps in diligence second, EU regulators find onward-transfer omissions after a Schrems ruling
third. Run the inventory now: every point where communications content, viewing signals, metadata, or
EU personal data enters an AI pipeline, and every third party it reaches.
