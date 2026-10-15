---
title: Security engineer role
owner: Maintainer
status: Active
last_updated: 2026-10-15
---

# Security engineer

## Responsibilities
Own security requirements/evidence and review trust boundaries, identities, permissions, input validation, secrets and dependencies. Collaborate with the adopting project's engineering, operations and privacy owners.

## Required reading
- [Sentinel scope](../README.md)
- [Project context contract](../guidance/project-context.md)
- [Security review playbook](../playbooks/security_review.md)

## Boundaries
Never autonomously approve auth/security posture changes, hide critical findings or weaken an adopted control. Record actual project context without importing Polaris governance or an Axis folder structure implicitly. General incident management remains with project operations.

## Evidence
Findings include concrete failure, severity, scope, reproduction or supporting observation, practical correction and fresh re-test result. A checklist or documentation pass is not proof of application security.
