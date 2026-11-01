# Cybersecurity Documentation Repository

Draft policies, plans, playbooks, and templates covering defensive, offensive, and governance areas of cybersecurity.

> All documents are **drafts/outlines**. Review with legal, compliance, and technical owners before adoption.

## Structure
```
cybersec-docs/
├── 01-governance/
├── 02-defensive/
│   ├── detection-and-monitoring/
│   ├── incident-response/
│   └── business-continuity/
├── 03-offensive/
└── templates/
```

## Index

### 01 - Governance
| Document | ID |
|---|---|
| [Risk Register Template](01-governance/risk-register-template.md) | GOV-001 |
| [Access Control Policy](01-governance/access-control-policy.md) | GOV-002 |
| [Change Management Policy](01-governance/change-management-policy.md) | GOV-003 |

### 02 - Defensive
| Document | ID |
|---|---|
| [Alert Triage Runbooks](02-defensive/detection-and-monitoring/alert-triage-runbooks.md) | DEF-001 |
| [Threat Hunting Playbook](02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | DEF-002 |
| [Incident Response Plan](02-defensive/incident-response/incident-response-plan.md) | IR-001 |
| [IR Playbooks (Outline)](02-defensive/incident-response/incident-response-playbooks-outline.md) | IR-002 |
| [Incident Report Template](02-defensive/incident-response/incident-report-template.md) | IR-003 |
| [Post-Incident Review Template](02-defensive/incident-response/post-incident-review-template.md) | IR-004 |
| [Chain of Custody Form](02-defensive/incident-response/chain-of-custody-form.md) | IR-005 |
| [Disaster Recovery Plan](02-defensive/business-continuity/disaster-recovery-plan.md) | BC-001 |
| [Business Continuity Plan](02-defensive/business-continuity/business-continuity-plan.md) | BC-002 |
| [Crisis Management Plan](02-defensive/business-continuity/crisis-management-plan.md) | BC-003 |

### 03 - Offensive
| Document | ID |
|---|---|
| [Rules of Engagement](03-offensive/rules-of-engagement.md) | OFF-001 |
| [Statement of Work](03-offensive/statement-of-work.md) | OFF-002 |
| [Scope and Authorization Letter](03-offensive/scope-and-authorization-letter.md) | OFF-003 |
| [Pentest Report Template](03-offensive/pentest-report-template.md) | OFF-004 |

### Templates
- [Document Template](templates/document-template.md)

## Conventions
- Markdown, kebab-case filenames
- Every document starts with the standard header (ID, version, status, owner)
- Status: Draft -> Review -> Approved -> Retired
- Update the README index when adding documents
