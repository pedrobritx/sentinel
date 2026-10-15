# Sentinel

Independent security engineering guidance extracted from the BSF security role and review playbook. It owns threat/trust-boundary review, control requirements and evidence. It is not an authentication provider, a runtime dependency or an assurance certification.

Start with [the security review](playbooks/security_review.md), [project context](guidance/project-context.md) and [the security engineer role](agents/security_engineer.md). A project supplies its actual auth, data, deployment and privacy context; Axis and Polaris are optional.

```sh
python3 automation/validate_docs.py
python3 -m unittest discover -s tests -v
```

These commands validate Sentinel documentation/tooling, not a consuming application's security. [Provenance](migration/provenance.json) preserves original paths and hashes. No general redistribution licence is selected by this relocation.
