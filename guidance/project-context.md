---
title: Security review input and evidence contract
owner: Maintainer
status: Active
last_updated: 2026-10-15
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
