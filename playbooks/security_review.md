---
title: Security review playbook
owner: Maintainer
status: Active
last_updated: 2026-10-15
---

# Security review

## When to use
Review a sensitive change, periodic security scope or pre-release risk within explicit authorisation.

## Required reading
- [Project context and evidence](../guidance/project-context.md)
- The adopting project's actual architecture, authentication, security requirements and privacy/incident procedures.

## Steps
1. Confirm scope and concrete trust boundaries.
2. Review auth/permission allow and deny paths, input validation, secrets, dependencies and applicable storage policies.
3. Run applicable project checks and record exact outputs; do not invent a scanner result.
4. File concrete findings with severity and practical correction; escalate critical exposure to the human owner.
5. Verify fixes with fresh regression/re-test evidence and record residual risk.

## Completion
Required evidence exists; no unresolved critical/high finding is treated as passed. Unknowns remain explicit. Update the adopting project's threat model or incident record when the review changes them. No deployment or external configuration is authorised by this playbook.
