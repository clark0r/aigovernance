# The Discipline of AI Governance

*Audience: everyone. This is the shared foundation every other file assumes.*

## What counts as AI — definitions determine obligations

No universal legal definition of AI exists, and that gap has teeth: whether a system falls inside a
statutory definition determines whether an entire body of law applies. The first question for any
system is definitional, and it must be **re-asked on every inventory refresh**, not resolved once at
intake — a rules-based tool that gains a learned scoring component can cross a definitional threshold
mid-lifecycle.

**Anchor definitions:**
- **OECD:** a machine-based system that infers, from input, how to generate outputs (predictions,
  content, recommendations, decisions) that can influence physical/virtual environments.
- **EU AI Act (Art. 3(1)):** OECD language + "varying levels of autonomy" + "adaptiveness after deployment."
- **NIST AI RMF 1.0:** mirrors OECD.
- **US (15 U.S.C. §9401(3)):** adds "perceive," "abstract into models," "use model inference to formulate options."

Other jurisdictions diverge: China regulates by use case (algorithmic recommendation, deep synthesis,
generative services) rather than one statutory AI definition; Canada's AIDA was never enacted; the UK
uses principles organized around adaptivity/autonomy rather than a binding definition.

### Definitional triggers map directly onto the Stack

| Definitional phrase | Stack layer activated | Consequence |
|---|---|---|
| "Infers from input" | L1 Data Governance | Input data inventoried, quality-managed, bias-assessed |
| "Generates outputs (predictions/recommendations/decisions)" | L2 Model Governance | Architecture review, fairness/robustness testing |
| "Can influence physical/virtual environments" | L3 System Integration | Integration review, cascading-failure analysis, boundary testing |
| "Varying levels of autonomy" (EU) | L4 Control & Monitoring | Access control, real-time monitoring, human override |
| "Adaptiveness after deployment" (EU) | L5 Audit & Evidence | Continuous documentation, audit trail, regulatory reporting |

**Decision rule:** if a system matches any regulatory AI definition, all five layers activate, scaled by
risk classification.

### Classification determines scope

- **Narrow AI (EU AI Act Art. 6(3) exemption):** "narrow procedural task" → baseline rigor.
- **GPAI model with systemic risk (Art. 51, ≥10^25 FLOP):** all five layers at maximum rigor + red-teaming/adversarial testing.
- **US dual-use foundation model (≥10^26 FLOP):** one order of magnitude above the EU threshold — a
  model can trip EU systemic-risk rules while sitting below the US reporting threshold.

**Common failure pattern:** classifying once, at the vendor's marketing description, instead of at the
deployed use case. The same underlying model is minimal-risk as an internal search tool and high-risk
screening job applicants.

## Why governance matters — how failures propagate

Every documented AI failure category maps to a specific Stack-layer failure, which is why the Stack
exists as an operational rather than philosophical framework:

| Case | Root layer | What a functioning control would have done |
|---|---|---|
| Amazon hiring algorithm | **L1** (data) | Bias assessment/representativeness testing pre-training would have caught male-dominated training data before it encoded discrimination |
| Apple Card | **L2 + L5** (explainability/opacity, not proven discrimination — NYDFS found no fair-lending violation after analyzing ~400k NY applicants; CFPB's $89M order was for dispute-handling failures, not algorithmic bias) | Interpretability + stakeholder-communication mechanisms convert "we believe it's fair" into a demonstrable answer |
| Facial-recognition wrongful arrests (Robert Williams 2020, Porcha Woodruff 2023, Detroit) | **L3 + L4** | Human-AI interaction design requiring verification before consequential action |

**Cascading failure principle:** failures cascade upward — Layer 1 data failures
corrupt Layer 2 model outputs, which corrupt Layer 3 integration behavior, which evades Layer 4
detection (calibrated to *expected*, i.e., already-biased, behavior), which undermines Layer 5
accountability. Two rules follow: **fix at the source layer**, and **Layer 4 must monitor for signals
from every layer below it, not just its own.**

### Risk-to-layer mapping (working reference, expanded in [The AI Governance Stack](02-ai-governance-stack.md))

| Risk category | Primary layer | Secondary layer | Control | Failure signal | Escalation |
|---|---|---|---|---|---|
| Individual harm (bias) | Data | Model | Bias assessment, fairness testing | Subgroup divergence >5% | Halt deployment |
| Systemic risk (cascading failure) | System Integration | Control & Monitoring | Cascading-failure analysis, circuit breakers | Correlated failures across systems | Incident response, isolate |
| Reputational damage | Audit & Evidence | Control & Monitoring | Documented due diligence | Public reporting of failure | Executive escalation |
| Regulatory exposure | Audit & Evidence | All layers | Conformity assessment | Regulatory inquiry | Legal response, remediation plan |
| Concentration of power | Control & Monitoring | System Integration | Human oversight, override | Consequential decisions w/o human review | Mandate human-in-the-loop |
| Feedback-loop amplification | Data | Control & Monitoring | Drift detection, retraining governance | Training-data distribution shift >10% | Retrain with corrected data |

## Who is accountable — the stakeholder matrix

Diffuse accountability ("everyone owns responsible AI") is the primary organizational failure mode —
nobody owns the bias assessment that never ran. The matrix assigns determinate accountability across
five actor types (tech companies, government regulators, civil society, academia, standards bodies) and
five layers, using strict vocabulary:

- **PRIMARY** — owns implementation, bears liability
- **SHARED** — co-owns, must coordinate
- **OVERSIGHT** — sets/enforces requirements, doesn't implement
- **MONITOR** — external verification, catches what primary owners miss
- **RESEARCH** — develops methods/tools, doesn't own implementation

**Decision rule:** every Stack layer must have exactly one PRIMARY owner *inside the organization*.
Internally this maps to: data stewards (L1), ML engineering leads (L2), platform/infra teams (L3),
security/ops (L4), compliance/legal (L5).

**Common failure pattern:** appointing a cross-functional AI ethics committee as "the owner." A
committee can advise; it cannot halt training, block deployment, or trigger rollback — only a named
individual with that authority and performance accountability can.

## The cost of inaction

The deployment-governance gap is quantified and growing:
- 72% of organizations have deployed AI in ≥1 business function (up from ~55% in 2023) — McKinsey.
- Global corporate AI spend projected >$300B/yr by 2027 — IDC.
- 63% of orgs with AI-related breaches lacked or were still developing an AI governance policy; 97%
  had inadequate AI access controls — IBM Cost of a Data Breach Report 2025.
- AI-related breaches average $5.72M vs. $4.4M global average; AI is a factor in 16% of all breaches — IBM 2025.
- US states adopted ~100 AI measures in 2025; 59 federal AI regulations introduced in 2024 (2x 2023) — Stanford AI Index 2025.

### Regulatory penalty exposure (see also `reference/penalty-comparison.md`)

| Exposure | Range | Trend |
|---|---|---|
| EU AI Act, prohibited practices | €35M or 7% turnover | Enforcement began 2025 |
| EU AI Act, high-risk violations | €15M or 3% turnover | Applicability from Aug 2026 |
| GDPR maximum | €20M or 4% turnover | €1B+ cumulative fines since 2018 |
| Average AI-related breach | $5.72M/incident | Rising |
| Deepfake fraud (financial services avg.) | $603K/incident | Aggregate losses tripling yearly |
| Reactive vs. proactive compliance | **3-5x cost multiplier** (planning benchmark) | Widening as regulation matures |

Litigation and fraud data points: Clearview AI $50M biometric settlement; CFPB $89M Apple/Goldman
order (dispute handling, not algorithmic bias); iTutorGroup $365K EEOC age-discrimination settlement;
Workday age-discrimination class action allowed to proceed (2025); US deepfake fraud losses $1.1B in
2025 (up from $360M in 2024 — Regula Forensics); projected AI fraud losses $40B/yr by 2027 (Deloitte).

**The compliance cliff:** deferring governance until mandated means accumulated technical debt,
undocumented models, and fragmented data practices must all be remediated simultaneously under
deadline pressure. Reactive programs run **3-5x** proactive investment (planning benchmark); orgs with
pre-established governance contain incidents ~40% faster at markedly lower cost (advisory-experience
benchmark).

## The business case and governance ROI

Four ROI dimensions, each mapped to Stack layers:
1. **Risk reduction value** (L5+L4) — 3-5x governance investment for high-risk systems (planning benchmark).
2. **Deployment velocity** (all layers) — mature-governance orgs complete evaluation in ~6 months vs.
   ~18 months ad hoc (planning benchmark) — governance reviews become checklist executions against
   evidence that already exists rather than bespoke projects.
3. **Trust premium** (L5) — governance maturity supports premium positioning in regulated sectors and
   procurement; institutional investors increasingly factor it into portfolio engagement.
4. **Talent retention** (culture) — technical turnover runs 1.5-2x annual salary (advisory-experience
   planning figure); governance reputation widens the recruiting pool.

**Arithmetic:** governance typically costs 5-15% of dev budgets for high-risk systems; non-governance
costs run multiples higher. **Practitioner note:** lead the internal pitch with deployment velocity, not
fine avoidance — velocity gains are visible in the current fiscal year and land immediately with
product leadership, whereas fine avoidance is probabilistic and easy to discount.

## The Stack — first look

See [`../reference/stack-quick-reference.md`](../reference/stack-quick-reference.md) for the full spec.
Three structural properties: cascading dependency, upward failure propagation, feedback from
the top (L5 findings flow back into L1 as continuous improvement).

## Applied walkthrough: the AI credit decision system

Full worked example — see the "Applied example" section at the bottom of
[`../reference/stack-quick-reference.md`](../reference/stack-quick-reference.md).

## Key takeaway

Read the foundational material, then your role's reading path, then use the rest as a reference shelf.
The Stack tells you *where* an obligation lands; cross-references tell you where the answer lives.
