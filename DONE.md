---
title: Sentinel review completion
owner: Maintainer
status: Active
last_updated: 2026-10-20
---

# Review completion

Record scope, concrete findings, required evidence, re-test results and residual risk. Unknowns cannot count as passed. Applicable critical/high findings block release. Run Sentinel's own documentation/tooling checks separately; they do not validate a consuming system's controls.

Apply [local-first security evidence](guidance/project-context.md): required checks run locally before remote/shared publication or an explicit scoped exception records the gap. Report environment, actual allow/deny checks, fresh re-tests and remaining gates separately from local commits, CI and release.
