# Critical Infrastructure and Federal Cybersecurity Frameworks

*Audience: counsel/CISOs at energy, transportation, nuclear, aviation, defense-connected orgs; OT
security teams evaluating AI deployments; AI vendors selling into critical infrastructure.*

## Structural logic of the overlay

AI in energy/transportation/nuclear/aviation/financial/defense infrastructure faces the most stringent
US expectations. This is an **overlay** — it stacks on top of general obligations (FTC Act, sector
privacy, state law), not a replacement. A predictive-maintenance model at a utility can simultaneously
sit inside NERC CIP scope, feed FERC Order 901 monitoring, and trigger CIRCIA reporting if compromised.

Three distinguishing features:
1. **The IT/OT boundary is a legal boundary.** Rapid patching, cloud telemetry, continuous model updates
   — normal IT practice — can violate OT requirements built around segmentation, change management, and
   qualification. Most of these regimes therefore concentrate at **Stack Layer 3**.
2. **Sector Risk Management Agencies (SRMAs) fragment the landscape** — CISA coordinates across 16
   sectors, but sector-specific agencies (DOE, TSA, Treasury…) impose their own requirements; multi-
   sector operators answer to multiple SRMAs for the same system.
3. **Incident-reporting clocks are short and multiplying** — CIRCIA (pending rules) will require 72hr
   incident / 24hr ransomware-payment reports; TSA directives already require 24hr reporting. The
   incident-classification playbook must recognize AI failure modes (poisoned training data, manipulated
   OT decision support) *before* the clock starts.

## Stack mapping for this domain

L2 = qualification/integrity (verification to sector assurance standards); L3 = architecture (IT/OT
segmentation, supply-chain risk, human-judgment boundaries); L4 = monitoring/incident response with
regulatory reporting hooks; L5 = audit-ready evidence for NERC/TSA/NRC/DOD review. L1 matters mostly
through **provenance as a supply-chain control**, not just a data-quality practice.

## Regimes at a glance

| Regime | Sector | Key obligation for AI | Reporting clock |
|---|---|---|---|
| CISA Act / CIRCIA | Cross-sector coordination | Secure-by-design AI guidance (2024, w/ NCSC-UK) | 72hr incident / 24hr ransomware (rules pending) |
| NERC CIP | Bulk electric system | CIP-013 supply-chain risk mgmt covers AI vendors; AI inside electronic security perimeter draws audit attention | Per CIP standards |
| TSA Security Directives | Pipeline, rail | Performance-based cybersecurity plans (2024 model); network segmentation | 24hr to CISA |
| NRC (10 CFR §73.54) | Nuclear | High-assurance protection; AI in safety-significant functions faces extensive qualification review; non-safety AI still needs defense-in-depth | License-driven |
| FAA (DO-178C family) | Aviation | ML component qualification via emerging EUROCAE/SAE G-34 (ARP 6983); AI Roadmap (2024) anticipates 2030+ for full autonomy | Certification-driven |
| FERC Order 901 | Bulk electric system | Internal Network Security Monitoring (INSM); AI-based anomaly detection is a *permitted compliance tool*, not just a subject | Phased through 2027 |
| DOD Responsible AI (DODD 3000.09) | Defense | Human-judgment requirement for autonomous weapons; 5 Ethical Principles (responsible/equitable/traceable/reliable/governable); contractor flow-down via DFARS/CMMC | Program-specific |

## Detail worth retaining

- **CIRCIA:** definitions of "covered entity"/"covered incident" (final rule pending, ~2026-2027) will
  determine how AI-specific compromises enter mandatory reporting. Rehearse the AI-incident-to-report
  pipeline now — route AI anomaly detections into the same incident-management system the SOC uses,
  with explicit escalation criteria for suspected adversarial causes.
- **NERC CIP:** continuous-learning/frequently-retrained models collide directly with CIP change
  management — every material model update to an in-scope system is a configuration change requiring
  the associated process/evidence. Either fix the model lifecycle to the CIP change cadence, or
  architect the AI outside the electronic security perimeter via a controlled, one-way interface.
- **TSA:** the 2024 shift to performance-based directives moves the burden from "comply with the listed
  control" to "demonstrate your AI deployment preserves the segmentation/monitoring/incident-response
  performance your plan commits to." Pre-agree which AI failure modes count as reportable incidents.
- **NRC:** position AI as advisory decision support with a qualified human or deterministic system
  retaining the action, and *document* that no credible AI failure can propagate into a safety/security/
  emergency-preparedness function.
- **FAA:** the certification question is never "does the model perform" but "can you demonstrate, with
  traceable artifacts, why it performs, on what data, within what bounds, and how out-of-bounds behavior
  is contained." Design the evidence stream as a build artifact from day one.
- **FERC Order 901:** where an AI anomaly detector *is* your INSM control, govern it like a compliance
  system — baseline documentation, detection-coverage mapping, threshold change management, false-
  negative analysis, alert-response records must be producible at audit.
- **DOD:** "traceable" and "governable" translate into concrete deliverables — lineage from data through
  model to deployed behavior, and demonstrated mechanisms to disengage systems exhibiting unintended
  behavior. Commercial vendors entering DOD subcontracts should price the Layer 5 documentation delta
  (CMMC-aligned cybersecurity, program-specific test-and-evaluation support) into the bid before
  signature.

## Consolidated reporting-clock table

| Regime | What's reported | Deadline | To whom |
|---|---|---|---|
| CIRCIA (pending) | Covered cyber incidents | 72hr | CISA |
| CIRCIA (pending) | Ransomware payments | 24hr | CISA |
| TSA directives | Cybersecurity incidents | 24hr of identification | CISA |
| NERC CIP | Incident reporting/response | Per CIP standards | Regional Entity |
| FDA-regulated device AI (see [Sector-Specific Federal Regulators on AI](15-sector-specific-federal-regulators.md)) | MDR-reportable events | Per 21 CFR 803 | FDA |

## Deployment checklist for AI in critical infrastructure

1. **Scope determination** — which regimes/SRMA apply; does the AI system inherit the criticality
   categorization of what it can influence?
2. **Supply-chain file** — vendor risk assessments, contractual flow-down, provenance for models/data/
   tooling.
3. **Boundary architecture record** — segmentation design, controlled crossing paths, human-judgment
   interfaces, with an explicit no-propagation analysis.
4. **Change-management alignment** — model update cadence reconciled with the sector's change-control
   regime.
5. **Monitoring/reporting integration** — AI anomaly detections routed into the SOC pipeline, pre-agreed
   incident classification, rehearsed 24hr/72hr reporting paths.
6. **Qualification evidence** — verification/validation matched to the sector's assurance standard,
   generated as a build artifact.
7. **Audit-ready evidence package** — standing Layer 5 file per system: categorization analysis, control
   mapping, test records, incident logs, vendor documentation.

## Key takeaway

Critical infrastructure regulators will not meet AI halfway — they've spent decades building assurance
regimes calibrated to physical consequence, and AI enters on their terms: categorize what the system can
touch, control its supply chain, respect the boundaries, qualify to the sector's evidence standard, and
be ready to report compromise in hours.
