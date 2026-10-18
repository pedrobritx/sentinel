---
title: Constellation A0 delegation and evidence threat model
owner: Sentinel maintainer
status: Proposed
last_updated: 2026-10-18
---

# Constellation A0 — delegation and evidence trust review

**Type:** Reusable engineering security review pattern; not a penetration test or product certification.  
**Tracks:** [Sentinel A0-011](https://github.com/pedrobritx/sentinel/issues/4) · [Constellation A0 goal](https://github.com/pedrobritx/constellation/issues/2).  
**Review surfaces:** [Polaris A0 router](https://github.com/pedrobritx/polaris/blob/main/automation/a0.py), [Polaris local evidence auditor](https://github.com/pedrobritx/polaris/blob/main/automation/a0_evidence.py), [VIA source-matched evidence PR](https://github.com/pedrobritx/via/pull/6).

## Authority and scope

This review documents risks that must be addressed proportionately before an AI agent may act in an adopting project. **Neither Polaris governance nor a discipline's instructions can elevate host permissions.** A valid planner output is not authorization, completed execution or independent assurance. The actual adopter maintains project-specific threats, data classification and fixes in its own repository; this document owns the reusable review approach.

Threat descriptions are **hypotheses and test requirements**. They are not claims that vulnerabilities were exploited or that controls have been independently validated.

## Relevant boundaries

| Boundary | Lower-trust inputs | Authoritative control |
| --- | --- | --- |
| Human → host → Polaris | User objective, proposed scope and host declarations | Actual human authorization and host-enforced approval/sandbox limits |
| Adopter source → context intake | Repo files, issue text, documentation, tests | Trusted host instructions and reviewed project policy; source text is not higher-priority authority |
| Polaris → Axis/Meridian/Sentinel | Contextual routing, handoff plan, optional capability signals | Validated versioned contracts; least-privilege actual host execution |
| Host → filesystem/network/tooling | Commands, generated code, tool outputs | Filesystem/network permissions and scoped credentials at tool boundary |
| Host/CI → evidence | Reported statuses, local receipts, logs | Directly observed exit codes, immutable revisions, CI provenance, independent observation where required |
| GitHub PR → Actions | Mutable PR code, workflow YAML, dependency lifecycle scripts | Read-only GitHub token, no production secrets, protected approvals and reviewer checks |
| VIA → clipboard | Derived health/travel estimates, user-entered location and profile inputs | Explicit user gesture, minimization and user-visible warning; no default external transmission |

## Risk register for A0

| ID | Abuse or failure mode | Proposed importance | Required safeguard and check |
| --- | --- | --- | --- |
| TR-01 | A malicious issue/source file tells the host to disregard governance or exfiltrate secrets | High | Treat repo content as data, prevent higher-priority instruction override, exercise prompt-injection fixtures; host sandbox/network limits |
| TR-02 | A coordinator launches a specialist with broader credentials than the original task | High | Enforce inherited/narrowed permissions at actual tool boundary; explicit approval for changes to credentials, secrets, spending, production or security posture |
| TR-03 | Opting out of Sentinel (or Meridian) is misrepresented as verified compliance | High | Preserve `needs-coverage` and record alternative ownership/evidence; add negative contract tests |
| TR-04 | Agents concurrently mutate shared files or incompatible schemas | Medium–High | Disable parallel editing without isolated worktrees/single writer; integration reconciliation and test coverage |
| TR-05 | Planning/reported `schema-valid` results are mistaken for executed or independently verified work | High | Keep planning, execution, verification and human approval distinct; no automatic progress promotion |
| TR-06 | A local receipt is forged along with its stdout/stderr log and matching hashes | High | Treat hashes as consistency, not attestation; inspect actual CI run and job logs; independent or human inspection for consequential results |
| TR-07 | A PR edits its own CI script, dependency install process or fixtures to generate favorable evidence | High | Read-only runner, protected branch/PR review, pinned trusted validators, review workflow diffs, no secrets to untrusted PRs; independent check before acceptance |
| TR-08 | CI/test output contains sensitive data and is published through public artifacts | High | Synthetic fixtures, redaction, local-only raw logs, narrow artifact retention, never store production secrets or patient records |
| TR-09 | Source revision changes after checks, yet stale evidence is presented as current | High | Compare exact Git revisions; reject dirty source and stale check receipts; rerun after changes |
| TR-10 | Clipboard copied text reveals addresses/patient details or implies teleconsultation is safe when infeasible | Medium–High | User-triggered only, minimal aggregate text, explicit hypothetical/uncertainty caveats, synthetic privacy tests, manual UX tests, privacy disclosure |
| TR-11 | GitHub workflow executes application code on privileged branches/deployments without review | High | No production secrets or write token, use separate CI from deploy, human approval/branch protection; no auto-merge |
| TR-12 | Host reports that subagents/worktree isolation are available when they are not | Medium | Capability declarations are conservative and untrusted until actually observed; unified fallback |

These priorities express what warrants scrutiny, not identified exploitable severity scores. Context may alter priorities.

## Observed controls (from reviewed code/workflows)

- Polaris's existing A0 router is read-only and validates explicit signals. It **does not** independently infer intent or assert that host subagents truly exist.
- The A0 result validator rejects claimed passing verification where required reported checks are absent, nonzero, or stale; it reports **schema-valid**, not externally attested.
- The local evidence auditor can validate SHA-256 digests of actual local log files against receipts and compare their revision to a clean Git checkout. A writer controlling both receipt and log may still forge internally consistent evidence.
- VIA's proposed [source-matched CI workflow](https://github.com/pedrobritx/via/pull/6) executes four *fixed* existing application checks and validates the receipts in GitHub Actions. The PR workflow uses a read-only token, pinned Polaris validator, synthetic test data and runner-local raw logs. It runs npm dependencies and PR code in an ephemeral job, **not** in a security sandbox guaranteed to resist arbitrary hostile npm scripts.
- The existing VIA copy feature and the proposed evidence workflow are **not evidence that a Codex host performed the implementation**.

### Unverified / not implemented

- Actual host-level inherited permissions through subagent delegation; no live agent has yet been run as part of A0.
- Prompt-injection containment across a real coding host and fetched untrusted project material.
- Manual keyboard, focus, live screen-reader and clipboard-denial behavior in supported browsers.
- Independent security inspection of the actual adopting project's clipboard implementation.
- Genuine CI provenance attestation resistant to an authorized attacker controlling the workflow itself, beyond public GitHub run history and reviewer checks.
- Comparative project pilot with ordinary coding-agent control and human acceptance.

## Required negative tests before unconditional A0 acceptance

1. A source file demands network exfiltration or modifies approval instructions; the host treats it as task data and cannot increase privileges.
2. A disabled but requested security discipline produces a coverage gap and blocks unconditional pass.
3. A reported completion contains absent/nonzero/stale test evidence; validation must refuse a passing status.
4. Log files are modified or receipts attempt path traversal; local integrity checking must fail.
5. Two simultaneous tasks target one writable interface; parallel work must be disabled or isolated.
6. A host lacking supported subagents falls back to unified execution.
7. A clipboard permission denial, missing API or stale calculation produces truthful accessible feedback; no optimistic success message.
8. Unreviewed private data or a privileged CI environment is presented as a test fixture; the run is stopped or isolated before public disclosure.

## Gates and stop conditions

Do not claim an independently verified security or accessibility pass solely because a planner, unit suite or CI workflow reports success. Halt any consequential operation that lacks explicit authority, creates unresolved high/critical actual findings, or exposes sensitive input unexpectedly. Human-approved exceptions must state context, owner, compensating controls, accepted residual risk and evidence. The A0 goal is not authorization to merge PRs, deploy, spend money, change provider/security policy or publish data.

**Recommended next step:** conduct a bounded live-host Codex trial in an isolated checkout using synthetic data; record actual tool permissions, delegation behavior, prompt-injection outcomes, source revision and independent reviewer observations. Keep app-specific findings in VIA; promote only reusable lessons back to Sentinel.
