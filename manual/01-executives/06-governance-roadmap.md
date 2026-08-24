# Ch. 6 — The Governance Roadmap

*Audience: executives/leaders with mandate and org design (Ch. 4-5) who need the build plan. Program
managers should pair this with Appendix C's item-level checklist (not yet in this knowledge base).*

## Key takeaway

Building an AI governance framework is a multi-month organizational initiative, not a policy-drafting
exercise. Sequence matters: authority and inventory before policy detail, high-risk systems before
everything else, evidence generation built in from the start rather than bolted on for the audit.

## The three-phase shape

| Phase | Months | Focus | Duration |
|---|---|---|---|
| 1. Foundation | 1-3 | Leadership, inventory, policies | 3 months |
| 2. Build & Operationalize | 4-8 | Documentation, testing, monitoring | 5 months |
| 3. Scale & Sustain | 9-12 | Audit, certification, reporting | 4 months |

Follows the Stack's cascading dependency: you can't classify systems you haven't inventoried, can't test
models whose data you haven't assessed, can't audit a program that never generated evidence. Timeline
assumes real executive sponsorship (named leader, budget, board reporting from month one) — programs
without that stall in Phase 1 regardless of plan quality.

## Phase 1: Foundation (months 1-3)

- **Executive sponsorship** — appoint CAIO/equivalent; minimum budget 0.5-1% of AI spend; charter the
  Governance Committee; dedicated team at min. 1 FTE per 50 high-risk AI systems.
- **AI inventory & mapping** — catalog *all* systems including shadow AI and vendor-embedded AI, not
  just internally-built models. Document business function, use case, data I/O, affected populations,
  lifecycle stage, data sources/dependencies, third-party vendors, usage patterns, training data
  characteristics. **Practitioner note:** organizations routinely discover hundreds of systems they had
  no centralized visibility into. Three habitual undercounts: vendor-embedded AI (features inside
  existing SaaS), shadow AI (employee use of public tools on company data), "analytics" that quietly
  crossed into automated decision-making.
- **Initial risk classification** — apply the org's framework (EU 4-tier or NIST-aligned 3-tier) to
  every inventoried system; document rationale; create a risk registry; schedule quarterly reviews.
- **Risk assessment methodology & risk appetite** — documented scoring methodology, severity ratings by
  harm type, standards for assessing reversibility/oversight capability, peer review, and an *explicit
  risk appetite statement* by business unit with defined acceptance authority levels — without this,
  every deployment decision relitigates the org's risk philosophy from scratch.
- **Regulatory gap assessment** — map applicable regulations by jurisdiction, assess current practice,
  prioritize by risk/enforcement likelihood, estimate remediation effort, assign ownership.
- **Foundational policy development** — draft/approve at minimum the AI Acceptable Use Policy, AI Risk
  Classification Policy, and AI Governance Charter.

**Phase 1 deliverables:** signed Charter; complete inventory with risk classifications; gap analysis
with remediation plan; foundational policies distributed; budget/resource plan for Phases 2-3.

**Common failure pattern:** writing all seven policies before classifying any systems. Policy drafting
feels like progress and needs no cross-functional cooperation, so weak programs overproduce documents
and arrive at month four with no inventory and no idea which systems the policies even apply to.

## Phase 2: Build and Operationalize (months 4-8)

Six workstreams, run against the high-risk-system subset first: **model documentation** (model card,
training-data records, architecture records, validation results, deployment specs — version-controlled,
lifecycle-tracked, automated where feasible via MLflow/DVC); **bias testing program** (identify
protected characteristics → define fairness metrics → baseline by subgroup → implement detection
tooling → pre-deployment audits → ongoing cadence weekly(high)/monthly(medium) → remediation
procedures → external audit capability); **explainability implementation** (model-appropriate methods,
quality standards, testing with actual target audiences, scaled to risk tier); **security/adversarial
robustness testing** (identify attack vectors per system, adversarial-example testing, distribution-shift
testing, poisoning-scenario testing — made a deployment precondition, not a research project); 
**monitoring infrastructure** (KPIs per system, dashboards for performance/fairness/drift/reliability/
compliance status, alerting thresholds, real-time anomaly detection for critical systems); **human
oversight protocols** (training + time/authority + context — the same three conditions from Ch. 5);
**third-party governance** (AI vendor assessment folded into procurement — this is where DPA/AI-
addendum terms from Ch. 23 enter operationally); plus parallel **legal/compliance alignment** work
(EU AI Act readiness if applicable, GDPR Art. 22/DPIA mapping, sector-specific compliance) and
**training and awareness** with documented completion records.

**Phase 2 deliverables:** complete model docs for all high-risk systems; initial bias-audit reports;
monitoring dashboards/alerting; trained human reviewers with documented procedures; vendor AI governance
assessment results; org-wide training completion records.

## Phase 3: Scale and Sustain (months 9-12)

- **Extend to medium-risk systems** using the Phase 2 templates/protocols incrementally.
- **Incident response readiness** — define what constitutes an AI incident (performance degradation,
  bias drift, security breach, compliance violation), severity classification, response team,
  investigation methodology, communication protocols. Root-cause discipline matters: biased data, model
  corruption, integration failure, and adversarial attack each demand *different* remediation. Build
  two notification tracks: **regulatory** (which obligations apply to which systems, who owns
  notification) and **affected-party** (clear, timely, explains what happened and what recourse exists).
  Track incidents and review trends — patterns across incidents are the cheapest early warning the
  program will ever get.
- **Internal audit** covering structure, policy adherence, technical controls, documentation
  completeness, fairness, security.
- **External audit preparation** — if pursuing ISO 42001 or EU AI Act conformity, readiness assessment
  with a third-party auditor first.
- **Maturity assessment** — formal scoring against the Ch. 2 maturity model with 12-month targets.
- **Governance reporting** — quarterly cadence for high-risk, semi-annual for medium; useful metrics:
  % systems in governance inventory (target ~100%), % with documented fairness assessment, % with
  complete/current docs, % incidents detected internally vs. externally, time to resolve compliance
  issues, training completion rate.

**Phase 3 deliverables:** protocols extended to medium-risk systems; incident response procedure with
completed tabletop exercises; internal audit report; external audit readiness assessment; formal
maturity assessment with 12-month targets; integrated board reporting.

## Budget and resourcing rules

- **Program budget:** 0.5-1.5% of AI spend (0.5-1% floor in year one).
- **Staffing floor:** minimum 1 FTE per 50 high-risk AI systems (small orgs meet this via the steward
  model + external advisory support).
- **Contingency:** 15-20% of budget — the inventory *will* surface systems you didn't budget for.
- **Multi-year commitment:** a one-year-only budget signals to every business unit that waiting it out
  is a viable strategy.
- Track and report budget variance to the committee alongside program metrics.

## The ongoing cadence (month 13+)

| Activity | Cadence |
|---|---|
| High-risk system monitoring | Daily dashboards; weekly fairness review |
| Medium-risk system monitoring | Weekly dashboards; monthly fairness review |
| Low-risk system monitoring | Monthly |
| Risk classification review | Quarterly + on material change |
| Governance committee meeting | Monthly |
| Management review of effectiveness | Quarterly |
| Board reporting | Quarterly (high-risk) / semi-annual (medium) |
| Internal audit | Semi-annual |
| External audit (high-risk) | Annual |
| Policy review/update | At least annual |
| Training refresh | Annual + on regulatory change |

Own regulatory monitoring as a standing workstream: track agency announcements/proposed rules, run an
impact assessment per change (which systems, what changes, what timeline), manage remediation through a
tracked roadmap — so new requirements arrive as planned work rather than emergencies.

## Key takeaway

Twelve months from ad hoc deployment to operational maturity: 3 months to establish authority/inventory/
baseline policy, 5 to build documentation/testing/monitoring/oversight/vendor-governance/training
against high-risk systems, 4 to scale, prove via internal audit, and wire board reporting. Fund at
0.5-1.5% of AI spend with 1 FTE per 50 high-risk systems and 15-20% contingency; verify against the
NIST-aligned maturity tiers rather than deliverable checklists alone; transition at month 12 to the
standing cadence.
