# Sentinel

Independent security engineering guidance extracted from the original Polaris security role and review playbook. It owns threat/trust-boundary review, control requirements and evidence. It is not an authentication provider, a runtime dependency or an assurance certification.

Start with [the security review](playbooks/security_review.md), [project context](guidance/project-context.md) and [the security engineer role](agents/security_engineer.md). A project supplies its actual auth, data, deployment and privacy context; Axis and Polaris are optional.

```sh
python3 automation/validate_docs.py
python3 -m unittest discover -s tests -v
```

These commands validate Sentinel documentation/tooling, not a consuming application's security. [Provenance](migration/provenance.json) preserves original paths and hashes. No general redistribution licence is selected by this relocation.

## Optional Constellation composition

Polaris is the usual coordinating entry point; [the composition contract](https://github.com/pedrobritx/polaris/blob/main/integration/README.md) defines explicit adoption, task scope and evidence returns. [discipline.json](discipline.json) describes this capability without installing a runtime dependency. Start directly at this repository’s AGENTS.md for standalone work.

When receiving a handoff, inspect the actual adopting project and retain its request ID, acceptance criteria, constraints and reviewed source revision. Return project artifacts, checks actually run, limitations, interface changes and blockers. Product-specific implementation/findings belong in the product repository; reusable capability improvements belong here. Excluded disciplines are explicit choices and never imply that their quality or safety checks passed.

## Evidence-Based Engineering

[The owning guidance](guidance/project-context.md) applies local-first verification, contextual environments and evidence-backed reporting without adopting full Polaris governance.
