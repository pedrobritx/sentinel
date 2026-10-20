---
title: Evidence-Based Engineering continuity
owner: Maintainer
status: Active
last_updated: 2026-10-20
---

# Current Evidence-Based Engineering work

Owner-approved policy implementation is prepared on `docs/evidence-based-engineering`. Polaris records operational adoption (ADR-007); Axis owns engineering methods; Sentinel owns security evidence; Constellation maintains workflow/profile adapters. Canonical philosophical text and architecture remain unchanged. Local validation results and exact revisions are reported with the review changes. Required GitHub protection enforcement, merge, deployment and account-plugin activation are separate states and are not implied by this record.

Review coordinated changes before merge; resolve any contrary ratified commitment explicitly. Use existing records rather than introducing per-task bureaucracy.

## Preserved previous record

---
title: Sentinel handoff
owner: Maintainer
status: Active
last_updated: 2026-10-16
---

# Current handoff

The 2026-10-16 owner request establishes Polaris as the usual coordinator and keeps each discipline independently usable. Composition changes are prepared for coordinated review on refactor/constellation-composition. The shared contract and audit record live in Polaris; local discipline manifests describe reusable ownership and evidence outputs. Product-specific artifacts remain in their product repository.

Run the documented local checks. Review the coordinated changes before merge; no release, deployment, provider configuration or automatic merge is included. Source revisions and local modifications are recorded by the planner; its output is a plan, not completed specialist work.

## Naming follow-up provenance

The standalone canonical-naming draft (Sentinel PR #2) corrected the extraction-origin wording and introduced [the normalization ledger](migration/name-normalization.json). This combined review retains that exact ledger and the composed README from Sentinel PR #3. The ledger's `before_sha256` and `after_sha256` values refer to the original, earlier naming-only snapshot; they **do not** claim that the combined composition revisions have identical hashes. The naming follow-up is historical review evidence, not a second active composition policy.

## Previous record (historical)

Canonical naming follow-up originally used `refactor/canonical-polaris-axis-names`. The initial extraction was already merged; the naming-only normalization snapshot requires its own review evidence and is retained separately from the latest handoff. It should not replace current operational guidance.


---
title: Sentinel extraction handoff
owner: Maintainer
status: Active
last_updated: 2026-10-15
---

# Current handoff

2026-10-15: the owner explicitly authorised moving capability files to their corresponding repositories and committing. Original file provenance is recorded in migration/provenance.json. The reviewed operating directions are applied; the philosophical canon and historical ADRs remain unchanged.

## Remaining review gates
Review destination branches before Polaris removal; inspect licence/distribution separately before any release. No automatic merge, deployment or auth posture changes are authorised.
