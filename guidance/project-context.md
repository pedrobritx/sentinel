---
title: Security review input and evidence contract
owner: Maintainer
status: Active
last_updated: 2026-10-20
---

# Security review input and evidence contract

## Required project context
Obtain the actual system boundary, affected data, entry points, identities, permissions, dependency/configuration changes, deployment context and approved scope. The project supplies its own documents; no Axis folder layout is required.

## Review obligations
- Identify concrete assets, threats, trust boundaries and misuse/failure scenarios.
- Check untrusted-input rejection and access-control allowed/denied paths.
- Keep secrets out of source, logs and prompts; audit dependency changes.
- For Supabase projects, verify RLS and authorised/unauthorised access; other platforms require equivalent appropriate controls.
- Separate required session/token properties from actual application settings and repository disclosure policy.
- Check purpose, minimisation and consent/authority before collecting telemetry or personal data.
- Record evidence and unknowns; a documentation pass does not establish implemented security.

## Outputs and authority
Findings name severity, affected scope, reproduction/evidence, correction and verification. Critical exposure requires immediate human escalation. Do not configure providers, rotate credentials, deploy, publish or merge without explicit authorisation. Use the adopting project's incident process for live incidents; general operations do not move into Sentinel.

## Evidence-Based Engineering security evidence

Apply security checks locally before remote/shared publication, using synthetic fixtures and least-privilege test identities. Exercise denied access as well as allowed paths, including relevant RLS, ownership/tenant isolation, malformed input, error handling and sensitive-data redaction. Check changed dependencies and secret handling. Required failures/unknowns remain blockers; never weaken controls to pass. Record actual checks, environment, scope, results and fresh re-tests. Reuse the project's threat/finding record; a new evidence template or scanner is not mandatory.

Use Docker for compatible services when feasible; record image/runtime/dependency versions, isolate disposable data and avoid privileged containers, exposed ports or production credentials by default. Native Apple security properties require the native toolchain/device or simulator. Record contextual exceptions and fidelity limits. A container pass is not a security boundary attestation or proof of production controls.

Local Git commits are checkpoints, not publication. GitHub pushes/PRs, shared Figma writes, merge, library publication, deployment and release are separate actions. If local verification is blocked, complete available checks and name affected requirements; obtain an explicit scoped exception before dependent publication when it is a prerequisite. CI supplements local evidence; verify required-check enforcement separately and retain human gates.

Axis owns the broader engineering method at `guides/evidence-based-engineering.md` in its repository; standalone Sentinel use requires no sibling checkout. General observability/recovery stays with product engineering. Security review verifies purpose, redaction, retention, allow/deny behaviour and sensitive failure paths without authorising telemetry or provider changes.
