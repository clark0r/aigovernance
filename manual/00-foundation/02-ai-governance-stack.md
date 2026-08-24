# Ch. 2 — The AI Governance Stack

*Audience: everyone — "the one chapter no reader should skip." The spine every later chapter cites.*

> The full layer-by-layer specification (scope, requirements DG-1…AE-5, decision rules, verification
> criteria, failure modes, ownership model, maturity model) has been consolidated into
> [`../reference/stack-quick-reference.md`](../reference/stack-quick-reference.md) to avoid duplicating
> content across files. This file covers what that reference doesn't: the *why* behind the design and
> the verification/failure-mode detail per layer.

## Why straight-line governance fails (§2.1)

Principle → policy → committee → annual audit was inherited from deterministic IT governance and fails
structurally for AI: AI is probabilistic, opaque, drifts in production, and produces outputs its
developers didn't anticipate. A principle can't catch a bad training set (data problems need data
controls); a committee can't see live model drift (production problems need production controls); an
annual audit can't detect yesterday's bias (evidence problems need continuous evidence). The Stack
replaces checkpoints with continuously-running controls at each layer where failure can originate.

## Layer-by-layer verification criteria and common failure modes

### Layer 1 — Data Governance
- **Verification:** data catalog completeness, quality-metric dashboards, bias-assessment
  documentation, PIA records, provenance spot-checks. Useful test: pick a random production prediction
  and have the owner walk the chain back to source records/transformations/consent basis in one working
  session — if it takes longer, provenance tracking is aspirational.
- **Failure modes:** undocumented data sources, stale quality metrics, bias assessment run *after*
  training instead of before, consent mechanisms that don't support withdrawal.

### Layer 2 — Model Governance
- **Verification:** does the evidence show fairness/robustness testing occurred *before* deployment
  approval and fed the decision, or was it generated afterward to dress an already-made decision
  (sequencing is the tell)?
- **Failure modes:** accuracy-only evaluation ignoring subgroup performance; robustness testing skipped
  under time pressure; model cards written post-deployment as compliance theater rather than design
  documents.

### Layer 3 — System Integration
- **Verification:** (1) failure-path check — trigger a controlled timeout/upstream degradation in test
  and confirm the fallback actually engages; (2) override completeness — every human override logged
  with operator + reason code.
- **Failure modes:** silent default-to-deny on timeout; reviewers rubber-stamping scores because the
  interface gives no basis to do otherwise; overrides happening but unlogged; stale integration
  diagrams. Behavioral test for SI-4 (human-AI interaction): if operators agree with the system *more*
  than its measured accuracy justifies, the interface is producing over-reliance regardless of training
  materials.

### Layer 4 — Control & Monitoring
- **Verification:** monitoring coverage %, alert config vs. the CM-2 metric list, incident-response
  drills (not just written procedures), deployment-gate logs. A gate that's never blocked anything
  deserves scrutiny — either exceptional discipline or decorative.
- **Failure modes:** monitoring tracks infra health (latency/uptime) but not model behavior
  (drift/fairness); alerts routed to an unowned mailbox; incident procedures never rehearsed; broad
  standing access left over from development; gates bypassable with an admin flag under delivery
  pressure. **CM-1 (access controls) is the single most commonly failed requirement in the entire
  Stack** — 97% of orgs with AI-related breaches had inadequate access controls (IBM 2025).

### Layer 5 — Audit & Evidence
- **Verification:** documentation-completeness scoring against AE-1, immutability/retention testing of
  the audit trail, timed retrieval exercises (how long to assemble a regulator-ready package for a
  named system — evidence should be a query, not a project), testing of AE-5 individual-facing
  explanation channels.
- **Failure modes:** documentation scattered across teams/tickets/chat with no system of record;
  records reconstructed after the fact (sophisticated regulators detect this via metadata
  inconsistency); retention set to storage defaults instead of regulatory minimums; audit findings
  logged but never remediated. "If the evidence doesn't exist before the complaint, you are not being
  audited; you are being discovered."

## The maturity-model transitions (§2.11)

- **Level 2 → 3** is the hardest and most valuable transition: policies-that-exist become
  processes-that-run — this is where the deployment-velocity gains from Ch. 1/4 first appear.
- **Level 3 → 4** is a measurement problem: instrument already-running processes with the Ch. 2 metrics
  so effectiveness (not just execution) is visible.
- **Level 4 → 5** is an automation problem: wire gates/evidence-generation/monitoring directly into
  dev workflows so compliance becomes a property of the pipeline.

## Key takeaway

This chapter is the specification the rest of the manual builds on. When any later chapter cites
"DG-1" through "AE-5," it's citing the requirement IDs defined here — see the reference file for the
full list.
