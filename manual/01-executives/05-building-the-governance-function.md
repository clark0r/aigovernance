# Ch. 5 — Building the Governance Function

*Audience: executives designing the organizational machinery — who leads, who owns what, which
policies must exist, how committees make decisions that stick, how culture determines whether any of it
works.*

## Key takeaway (stated up front in source)

Diffuse accountability is the primary structural failure mode. The fix: structure first, then policy,
then culture. A policy without an owner is a document; an owner without authority is a scapegoat.

## Organizational structure and leadership

**The Chief AI Officer (CAIO):** orgs with a CAIO rose from 11% (2023) to 26% (2025) — Gartner/IBM; >60%
hired externally (DataIQ 2025); AI governance/leadership roles command a 25% salary premium (Stanford AI
Index 2025). Reports to CEO or CRO (not buried under an existing function) so AI governance gets
executive attention. Owns: organizational AI policy translation, cross-business-unit compliance, risk
identification, initiative coordination, regulator liaison.

**Three-layer structure:**

| Layer | Body | Composition |
|---|---|---|
| Executive | CAIO or equivalent | Reports to CEO/board; owns strategy, risk appetite, regulatory compliance |
| Oversight | AI Governance Committee / Ethics Board | Cross-functional (legal, compliance, engineering, HR, business), + external advisors as needed |
| Operational | AI governance managers/specialized teams | Day-to-day: model documentation, bias testing, monitoring, incident response |

Large enterprises: full three layers. Mid-size: consolidate oversight+operational into one committee.
Small orgs: a single named AI steward (senior tech/compliance leader) with explicit authority and time
allocation, supported by external advisors.

**Two non-negotiable design rules regardless of size:**
1. The governance lead's reporting line must be **independent of the business units deploying AI** —
   otherwise it faces pressure to approve non-compliant systems to hit business objectives.
2. **Explicit budget and board-level reporting from day one** — a title without budget authority is how
   orgs perform governance without doing it.

## Ownership model — one owner per Stack layer

See [`../reference/stack-quick-reference.md`](../reference/stack-quick-reference.md) for the full
ownership-attribute list (authority/evidence/metrics/escalation). Standard assignments:

| Layer | Primary owner | Accountable for |
|---|---|---|
| 1 Data | Data stewards | Inventory/classification, quality, bias assessment, provenance, consent |
| 2 Model | ML engineering leads | Architecture review, validation, fairness/robustness testing, docs |
| 3 System Integration | Platform/infra teams | Integration architecture, pipeline security, cascading-failure analysis, boundary testing |
| 4 Control & Monitoring | Security/ops teams | Access controls, real-time monitoring, anomaly detection, incident response, deployment gates |
| 5 Audit & Evidence | Compliance/legal | Documentation standards, evidence preservation, audit, regulatory reporting |

The CAIO doesn't own a layer — owns the integrity of the whole, arbitrates cross-layer conflicts, and
resolves resourcing disputes between layers. Use the executive control mapping as a quarterly
diagnostic: any cell without a named owner and a current artifact is a gap, and gaps at lower layers
matter more (their failures propagate upward).

## Core policy development — the seven components

| Policy | Purpose | Key requirements |
|---|---|---|
| AI Acceptable Use | Permitted/prohibited applications | Scope, prohibited uses, approval workflow, exceptions |
| AI Risk Classification | Categorize systems by risk | Classification criteria, methodology, escalation triggers |
| Model Documentation | Standardize AI docs | Training data, architecture, performance metrics, version control |
| Bias Testing & Fairness | Equitable outcomes | Testing methods, protected characteristics, thresholds, remediation |
| Transparency | Disclosure requirements | Notification standards, explanation requirements, audience-specific formats |
| Human Oversight | Review requirements | Review triggers by risk tier, reviewer qualifications, override authority |
| Data Governance | Training/inference data mgmt | Quality, consent, retention, cross-border transfer, provenance |

**Two drafting principles:** write in language accessible to the audience that must follow it (not legal
jargon); commit to *specifics* rather than restating the law ("we will assess all AI systems for
fairness before deployment" gives employees something executable and auditors something verifiable;
"comply with applicable law" gives them nothing).

## Risk assessment and classification

The mechanism that makes governance affordable — low-risk systems get baseline controls, high-risk get
the full apparatus. Adopt EU AI Act's four-tier scheme (unacceptable/high/limited/minimal) if EU-exposed,
or a three-tier NIST-aligned scheme (high/medium/low) if primarily US-exposed.

Classification weighs **contextual** risk, not just technical risk: protected-characteristic
involvement, decision reversibility, vulnerable-population impact, novel methodology, whether humans
can meaningfully understand/override. Not one-time — reassess at least quarterly and immediately on
material system change.

**Common failure pattern:** deferring to the vendor's risk characterization. Vendors are incentivized to
call their product "low-risk decision support." Classify by what the system *does in your deployment
context* — a decision-support tool whose recommendation is accepted 98% of the time is functionally an
automated decision system.

## Committees done right

Five properties: **composition** (technical, legal/compliance, risk mgmt, affected business units,
ethics specialists, HR where relevant, + external advisors as needed); **authority** (power to
approve/block/condition deployments, escalate to the board — without this, business pressure will skip
governance steps whenever compliant); **cadence** (monthly, iterative review across concept →
development → pre-deployment, not a single gate); **reporting lines** (independent of the business
units they oversee, ideally with board audit-committee visibility); **charters and documentation** (an
AI Governance Charter is itself a Layer 5 artifact regulators/auditors ask for early).

## The five operational disciplines

1. **Model documentation & lifecycle management** — spans development (training data, feature
   selection, architecture, baseline metrics) → validation (testing, fairness eval, adversarial
   robustness, human review findings) → deployment (environment specs, integration points, access
   controls, rollback) → monitoring (drift thresholds, retraining triggers, decommissioning). Every
   artifact needs version control, authorship, timestamping. Undocumented models are ungovernable by
   definition.
2. **Bias testing & fairness assurance** — pre-deployment testing across all legally protected
   characteristics using multiple fairness metrics; ongoing monitoring for fairness drift; documented
   remediation; external audit capability. AI hiring tools are 74% more likely to schedule interviews
   for male-named candidates; women's-college resumes 31% less likely to advance past AI screening
   (Stanford AI Index 2025 compilation).
3. **Transparency & explainability** — external transparency (notification + explanation for affected
   individuals) vs. internal transparency (sufficient model insight for oversight bodies). Explainability
   depth scales with risk classification.
4. **Human oversight & accountability** — more than a rubber-stamp: reviewers need training to evaluate
   critically, time/authority to intervene, and access to context for independent judgment. Define
   oversight requirements by risk tier.
5. **Post-deployment monitoring** — continuous performance tracking, regular fairness re-evaluation,
   anomaly detection, user feedback, security monitoring, periodic full re-evaluation. Cadence
   proportional to risk: daily (high-risk) / weekly (medium) / monthly (low).

## Building a governance culture

Delegating governance entirely to a compliance department typically fails to achieve strong governance;
it works when leadership, product teams, and technical staff view it as essential rather than burden.
Four levers: **leadership commitment** (resource allocation + participation, not statements — link
manager compensation to governance outcomes); **response to failure** (blameless investigation vs.
punishment that hides problems); **training with reasoning**; **hiring/retention**. External consultants
accelerate but shouldn't replace internal capability — internal expertise lets the org adapt as
conditions change and actually own governance.

**Common failure pattern:** compliance theater — documented policies, minuted committees, clicked-
through training, none of it implemented in the systems actually running. Test: pick a high-risk system
at random, ask for its current model card, last fairness test, and named human reviewer. Any answer
taking more than a day means the program is theater.

## Cross-industry comparison

| Industry | Primary regulators | Key AI requirements | Governance priority |
|---|---|---|---|
| Healthcare | FDA, HHS, state health agencies | Clinical validation, demographic reporting, SaMD pre-market review | Patient safety, population representativeness, clinician override |
| Financial Services | OCC, Fed, FDIC, SEC, FINRA, states | Model risk mgmt, fair lending, conflict disclosure | Bias testing in lending/credit, explainability |
| Employment/HR | EEOC, NYC DCWP, state labor | Bias audits, candidate notification, consent | Annual audits, transparency notices, biometric consent |
| Insurance | State insurance commissioners, NAIC | Actuarial fairness, rate justification, disclosure | Algorithmic fairness in underwriting/claims |
| Autonomous Systems | NHTSA, FAA, state DMVs | Safety standards, incident reporting, ODD | Safety assurance, redundancy, human intervention |
| Education | DOE, state education agencies | Student data privacy, assessment fairness, accessibility | FERPA compliance, equitable access |

Sector-specific detail worth noting: a 2024 peer-reviewed analysis found only 3.6% of FDA-approved
AI/ML medical devices reported race/ethnicity data in clinical evaluations, 99.1% no socioeconomic
data, 81.6% no age demographics — enhanced documentation beyond vendor-supplied information is
therefore an org obligation, not an assumption. Multi-sector orgs face *compounding* requirements (e.g.,
a financial-services company using AI in hiring answers to banking model-risk standards, employment
bias-audit requirements, state consumer protection law, and possibly the EU AI Act simultaneously) —
an integrated Stack-based framework is the only efficient way to manage that.

## Key takeaway

Build in order: accountable leadership with independent reporting/budget → one owner per Stack layer →
the seven core policies → a committee with real decision authority → the five operational disciplines at
risk-proportional rigor → continuous culture investment. Ch. 6 sequences all of this into a 12-month
roadmap.
