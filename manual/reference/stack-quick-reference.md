# The AI Governance Stack — Quick Reference

> Source: Ch. 1 (first look) and Ch. 2 (full specification)

## Why a "stack" instead of the usual principle → policy → committee → annual-audit line

Straight-line governance fails for AI because it was inherited from deterministic IT systems.
AI is probabilistic, drifts in production, and fails between annual checkpoints. The fix: match
governance to the system being governed — a stack of continuously-running controls, one per layer
where failure can originate, each with its own owner and its own evidence stream.

- A principle can't catch a bad training set → data problems need data controls (Layer 1).
- A committee can't see live model drift → production problems need production controls (Layer 4).
- An annual audit can't detect yesterday's bias → evidence problems need continuous evidence (Layer 5).

## The five layers

| # | Layer | Defining question | Core mechanisms | Default owner |
|---|---|---|---|---|
| 1 | **Data Governance** | Is the data safe to learn from? | Inventory & classification, quality mgmt, bias assessment, provenance, consent/privacy | Data teams |
| 2 | **Model Governance** | Is the model sound, fair, non-biased? | Architecture review, training/validation, fairness & robustness testing, interpretability, documentation | ML / data science |
| 3 | **System Integration** | Is it wired into the business safely? | Integration architecture, pipeline security, cascading-failure analysis, human-AI interaction design, boundary testing | Engineering |
| 4 | **Control & Monitoring** | Are we watching it in production? | Access control, real-time monitoring, anomaly detection, incident response, deployment gates | SRE / risk operations |
| 5 | **Audit & Evidence** | Can we prove all of the above? | Documentation standards, evidence preservation, audit mechanisms, regulatory reporting, stakeholder comms | Compliance / legal |

## Structural properties

1. **Cascading dependency** — each layer is the foundation for the next. Model quality can't exceed
   data quality; integration behavior inherits model quality; monitoring watches integration; audit
   proves everything below it.
2. **Upward failure propagation** — failures cascade *up*, never down, and must be fixed at their
   *source* layer. A Layer 1 bias problem "fixed" with a Layer 3 human-review patch is compensation,
   not correction — the defect keeps generating skewed outputs the patch only partially masks.
3. **Feedback from the top** — Layer 5 audit findings flow back to Layer 1 as the input to the next
   improvement cycle.

## Ownership model (Ch. 2 §2.9)

Every layer must have exactly **one PRIMARY owner** with:
- **Authority** — can halt training / block deployment / trigger rollback / refuse sign-off unilaterally
- **Evidence** — produces the layer's evidence as a byproduct of running it
- **Metrics** — measured on layer-specific governance metrics (below)
- **Escalation** — a defined path to executive level when a decision rule collides with a deadline

A cross-functional ethics/AI committee can *advise* an owner; it cannot *substitute* for one.
Chronic ownership gaps: **Layer 3** (falls between "we built the model" and "we consumed an API") and
**Layer 4** (assigned to uptime-measured SRE, which then never watches model *behavior*).

## Requirement IDs (stable identifiers used across the source manual)

Use these verbatim in internal policy docs / audit workpapers so gap analysis is a join, not a
translation exercise.

| Layer | IDs | Sample requirements |
|---|---|---|
| 1 Data Governance | DG-1…DG-5 | DG-1 inventory; DG-2 quality thresholds (completeness ≥95%, accuracy ≥98%, consistency ≥90%, staleness ≤30 days); DG-3 bias assessment; DG-4 privacy compliance; DG-5 provenance tracking |
| 2 Model Governance | MG-1…MG-5 | MG-1 architecture review; MG-2 fairness testing (≥2 metrics, >5% divergence blocks deployment); MG-3 robustness evaluation; MG-4 interpretability (scaled to risk); MG-5 model documentation/model card |
| 3 System Integration | SI-1…SI-5 | SI-1 integration architecture review; SI-2 pipeline security; SI-3 cascading-failure analysis + circuit breakers; SI-4 human-AI interaction design; SI-5 boundary-condition testing |
| 4 Control & Monitoring | CM-1…CM-5 | CM-1 access controls (least privilege — most commonly failed requirement industry-wide); CM-2 real-time performance/fairness/drift monitoring; CM-3 anomaly detection; CM-4 incident response (SLA: critical 1h / high 4h / medium 24h); CM-5 deployment gates |
| 5 Audit & Evidence | AE-1…AE-5 | AE-1 documentation standards (contemporaneous, not retroactive); AE-2 evidence preservation (EU AI Act: 10yr post-market); AE-3 internal audit (min. annual for high-risk); AE-4 external audit readiness; AE-5 stakeholder communication/explanation rights |

## Decision rules worth memorizing

- If a system matches any regulatory AI definition → **all five layers activate**, scaled by risk classification.
- Classification attaches to the **use case**, not the model artifact (a general-purpose model is minimal-risk as internal search, high-risk as a hiring screen).
- Training data demographic distribution diverging >15% from the deployment population → resample, augment, or document accepted risk.
- Proxy variables correlated >0.7 with protected characteristics → evaluate removal/transformation/fairness constraint.
- Fairness metric divergence >5% across subgroups → bias mitigation + retest before deployment.

## Cross-layer concerns

- **Explainability** is composite, not a single-layer feature: Layer 1 explains what data/limitations;
  Layer 2 explains how predictions are generated; Layer 3 explains how outputs become decisions and what
  oversight applied; Layer 4 explains what monitoring detected/actioned; Layer 5 explains the approval
  chain and evidence.
- **Governance metrics** per layer (read as *ranges*, not maxima/minima — e.g., a near-zero human
  override rate suggests rubber-stamping; a very high rate suggests the model isn't trusted):
  catalog coverage / quality scores (L1); fairness scores, robustness pass rate (L2); override rate,
  circuit-breaker activation frequency (L3); monitoring coverage, mean time to detect (L4); audit
  completion rate, documentation completeness (L5).

## Maturity model (Ch. 2 §2.11)

| Level | Name | Characteristics |
|---|---|---|
| 1 | Ad Hoc | No systematic governance, no documentation |
| 2 | Defined | Policies exist, inconsistent implementation |
| 3 | Managed | Standardized processes, metrics tracked |
| 4 | Measured | Effectiveness quantitatively measured, continuous improvement |
| 5 | Optimized | Fully automated, integrated into dev workflows, predictive |

**Target:** Level 3 minimum **at all five layers** for high-risk systems (a floor, not an average — the
weakest layer sets the effective maturity of the whole system); Level 4 for critical infrastructure.

## Applied example: the credit-decision walkthrough (Ch. 1 §1.7)

A single gradient-boosted credit model, governed vs. ungoverned, illustrates the whole stack:

| Dimension | Principles-and-audit governance | Stack governance |
|---|---|---|
| Detection of a fair-lending problem | Month 6, via regulator complaint | Day 1-2, via drift alert |
| Root cause | Weeks of reconstruction | Known before launch |
| Fairness evidence | Built under pressure | Already a scheduled artifact |
| Regulatory response time | ~60 days | ~4 hours (72hr package assembly) |
| Cost | Several $M + reputational damage | ~5-15% of dev budget, ongoing |

Layer-by-layer: L1 catches a zip-code proxy correlating 0.78 with race and removes it; L2 fairness
testing (demographic parity/equalized odds/calibration) cuts a 7.3% approval-rate disparity to 3.8%;
L3 adds a fallback queue so model timeouts route to manual review instead of silent auto-deny, and
logs 100% of overrides; L4 catches a 15% approval-rate shift from an unmodeled regional employment
shock within 48 hours and shadow-mode's the model; L5 assembles a complete regulator response package
in 72 hours from an already-maintained evidence trail.
