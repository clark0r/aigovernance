# Ch. 3 — Ethics and Professional Responsibility

*Audience: everyone, especially practitioners making judgment calls the law doesn't settle. Ethics is
the decision layer that operates wherever regulation is silent, ambiguous, or in conflict.*

## Why ethics belongs alongside compliance

Regulations set legal minimums; ethics addresses what to do when legal requirements underdetermine the
answer. In practice they aren't separable: ethical frameworks create the decision criteria that Control
& Monitoring enforces and Audit & Evidence documents. An org that can't articulate *why* it resolved a
trade-off a particular way can't document that reasoning — and an undocumented value judgment is a
governance gap waiting for a finding.

### Ethical principles mapped to the Stack

| Principle | Layers activated | Operational form |
|---|---|---|
| Fairness & non-discrimination | L1, L2, L4 | Representative data + bias assessment; fairness testing/subgroup eval; production fairness monitoring |
| Transparency & explainability | L2, L3, L5 | Interpretability + model docs; human-AI interaction design; stakeholder comms/decision explanation |
| Privacy & data protection | L1, L5 | Consent, minimization, purpose limitation; DPIA docs and regulatory reporting |
| Accountability & responsibility | L4, L5 | Access controls, incident response, escalation; audit trails, governance records |
| Safety & robustness | L2, L3, L4 | Robustness/adversarial testing; cascading-failure analysis, circuit breakers; anomaly detection, rollback |
| Human autonomy & oversight | L3, L4 | Human-in-the-loop design + override; oversight requirements, automated-decision limits |

## Four ethical frameworks (complementary, not competing)

| Framework | Strength | Limit |
|---|---|---|
| **Consequentialism** (outcomes) | Maximizes positive outcomes | Can justify harm to a subgroup if aggregate outcomes are positive |
| **Deontology** (duties/rights) | Supplies the constraint consequentialism lacks | No answer when duties conflict; rights themselves are contested across cultures |
| **Virtue ethics** (cultivated judgment) | Fits domains no rulebook anticipates | Low specificity; virtues can conflict |
| **Care ethics** (relationships, particular needs) | Centers real people, not aggregates | Doesn't scale to decisions affecting millions |

Effective governance combines all four: consequentialist thinking about outcomes, deontological
thinking about rights, virtue-ethics about organizational character, care-ethics about particular needs.

## Five core principles

**Transparency** — enables autonomy and accountability but has real limits (some systems resist
explanation; full transparency risks IP/gaming). **Fairness & non-discrimination** — contested;
different conceptions can conflict (see Ch. 33's formal metrics). **Autonomy** — meaningful control,
not merely formal options (a nominal appeal channel no one can successfully use satisfies the form and
violates the principle). **Accountability** — requires clarity of responsibility across multi-party
systems; the one-owner-per-layer rule (Ch. 2) is the structural answer inside an org. **Privacy** —
informed consent, authorized purposes, protection against unauthorized access.

**Common failure pattern:** treating a fairness-vs-accuracy or transparency-vs-security trade-off as a
technical parameter for engineering to tune. These are value choices — route them to the accountable
decision-maker, record the reasoning at Layer 5, and revisit on a schedule.

## The ACM Code of Ethics — individual professional responsibility

Anchors individual (not institutional) responsibility; organizational governance and the ACM Code are
complements — the Stack keeps the org behaving well even when individuals fail; the Code gets
individuals to push back when the org fails.

- **1.1** Contribute to society/human well-being — attend to effects beyond the immediate customer
  (a hiring AI affects the labor market, not just the employer).
- **1.2** Avoid harm — requires *anticipating* non-obvious harms (surveillance enablement, bias
  reinforcement, erosion of agency), and addressing harms to *all* affected parties, not just the most
  severe.
- **1.3** Be honest and trustworthy — truthful about capabilities/limitations/testing; the MG-5 model
  card requirement is this principle rendered as an artifact.
- **1.4** Be fair, take action against discrimination — affirmatively, not just by avoiding intentional bias.
- **2.4 / 2.5** Comprehensive specifications; work only within competence — staff governance reviews
  with the competencies the decisions actually require.
- **2.1** Protect the public interest when it conflicts with organizational interest — willingness to
  escalate beyond normal channels; orgs wanting internal escalation must make that channel credible.
- **3.1 / 3.4 / 3.5 / 3.7** Support professional standards; respect employer policy *bounded by* human
  dignity; honest attribution of work — directly served by contemporaneous Layer 5 documentation.

## Six-step method for ethical decision-making

1. **Clarity about values and goals** — articulate them explicitly so decisions are consistent.
2. **Stakeholder identification** — including less-powerful stakeholders, not just the obvious ones.
3. **Explicit acknowledgment of trade-offs** — a documented trade-off is defensible; a hidden one is a finding.
4. **Reflection and learning** — willingness to change course when evidence warrants.
5. **Procedural justice** — known process, heard voices, stated reasons, available appeal — even where
   reasonable people disagree with the outcome.
6. **Attention to power dynamics** — unexamined processes concentrate influence in the powerful by default.

**Common failure pattern:** ethics review as a terminal checkpoint — one meeting late in the dev cycle
after architecture is fixed and the launch date committed, where the real options are "approve" or
"approve with comments." By then the significant value choices (data sources, target variable, fairness
conception, automation degree) were already made implicitly by whoever wrote the code weeks earlier.
Move the six-step method to where those choices actually get made.

## Institutional mechanisms (embedding ethics at scale)

Operationally these live at Control & Monitoring / Audit & Evidence:
- **AI ethics committees** — valuable review, but cannot be a layer *owner* (Ch. 1). Effectiveness
  depends on composition, authority, and culture; a committee that can't block a launch, or reviews
  only what teams volunteer, is advisory theater.
- **Impact assessments** — most effective when they involve affected communities, external review, and
  genuine willingness to change course. Appendix D template; Ch. 24-25 cover the legally-mandated
  variants (DPIAs, EU AI Act assessments) a well-designed process satisfies in one pass.
- **Governance policies/standards** — specific enough to guide, flexible enough to fit context; test:
  can an engineer with a concrete question find a concrete answer?
- **Training with reasoning** — explaining *why* outperforms reciting rules; someone who understands
  what fairness testing prevents runs the tests under deadline pressure, someone who only knows "you
  have to" skips them.
- **Incident reporting/learning systems** — need psychological safety to surface problems rather than
  hide them.
- **External accountability** — audit/regulatory/civil-society oversight isn't subject to the org's own
  incentives; mature orgs treat it as calibration, not threat.

## Domain-specific tensions

- **Facial recognition/surveillance:** privacy vs. public safety vs. non-discrimination — see the
  Detroit wrongful-arrest cases (Ch. 1).
- **Content moderation:** free expression vs. harm prevention vs. autonomy — not resolvable by technical
  optimization alone.
- **Predictive policing:** fairness vs. public safety vs. autonomy — biased predictions feed policing
  that targets the same communities disproportionately, feeding the biased data cycle.
- **Healthcare/diagnosis:** patient welfare/consent/autonomy vs. efficiency/cost containment (Ch. 42).

## Governance culture

Four levers: **leadership commitment** (resource allocation and behavior, not statements — has a launch
ever actually been delayed on a governance finding?); **response to failure** (blameless investigation
surfaces problems; punishment hides them — in Stack terms, punishment means Layer 4 signals exist but
never get raised); **training with reasoning**; **hiring and retention** (governance commitment is
itself a recruiting advantage, per Ch. 1's 1.5-2x turnover-cost figure).

**Common failure pattern:** compliance theater — policies documented, committee minuted, training
clicked through, none of it implemented in the running systems. Test: pick a high-risk system at
random and ask for its current model card, last fairness test result, and the name of its human
reviewer. If any answer takes more than a day, the program is theater.

## Governance across organizational boundaries (Ch. 3 §3.9)

- **Vendor-supplied AI:** governance responsibility is shared — the vendor builds responsibly and
  discloses limitations; the purchaser evaluates fit and monitors in its own context. Neither
  substitutes for the other; the contract makes the split explicit (Ch. 23, Ch. 41).
- **Cloud services:** limited visibility into the provider's practices; certifications/audit rights
  become the practical proxy (Ch. 38, 41).
- **Open source components:** diffuse responsibility — no vendor to hold accountable, so the integrator
  owns evaluation and maintenance.
- **Supply chain:** every boundary crossing is a Layer 3 integrity checkpoint and a Layer 5 evidence
  question — can you produce your vendor's fairness testing when the regulator asks for yours?

## Comparative frameworks (§3.11)

| Framework | Focus | Limitation |
|---|---|---|
| ACM Code of Ethics (2018 rev.) | Individual professional responsibility | Aspirational, no enforcement mechanism |
| IEEE Ethically Aligned Design | Detailed, domain-organized guidance | Length/complexity limit adoption |
| EU Ethics Guidelines for Trustworthy AI (2019) | Fed directly into the EU AI Act | EU-centric; some explainability asks aren't technically feasible |
| OECD AI Principles (2019, updated 2024) | Broadest intergovernmental consensus (46+ countries) | High-level, limited implementation detail |

Two management-system standards operationalize these: **NIST AI RMF** (Govern/Map/Measure/Manage — the
de facto US standard) and **ISO/IEC 42001** (first certifiable AI management-system standard, PDCA
methodology; orgs with existing ISO 27001/9001 report 30-40% implementation-effort savings — planning
benchmark). No single framework is comprehensive; most multi-jurisdiction orgs run one program mapping
NIST functions → ISO 42001 controls → OECD principles → specific statutes like the EU AI Act.

## Key takeaway

Effectiveness depends less on framework design than on organizational commitment. Choose one primary
framework, wire its principles into the Stack's layer requirements, give institutional mechanisms real
authority, and let the ACM Code govern the individual judgment no framework reaches.
