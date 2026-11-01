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
│   │   └── playbooks/
│   └── business-continuity/
├── 03-offensive/
├── 04-compliance-mapping/
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
| [PB-01 Ransomware](02-defensive/incident-response/playbooks/pb-01-ransomware.md) | IR-PB-01 |
| [PB-02 Phishing / BEC](02-defensive/incident-response/playbooks/pb-02-phishing-bec.md) | IR-PB-02 |
| [PB-03 Data Breach](02-defensive/incident-response/playbooks/pb-03-data-breach.md) | IR-PB-03 |
| [PB-04 Insider Threat](02-defensive/incident-response/playbooks/pb-04-insider-threat.md) | IR-PB-04 |
| [PB-05 DDoS](02-defensive/incident-response/playbooks/pb-05-ddos.md) | IR-PB-05 |
| [PB-06 Account Compromise](02-defensive/incident-response/playbooks/pb-06-account-compromise.md) | IR-PB-06 |
| [PB-07 Malware Outbreak](02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md) | IR-PB-07 |
| [PB-08 Lost / Stolen Device](02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md) | IR-PB-08 |
| [PB-09 Web App Compromise](02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md) | IR-PB-09 |
| [PB-10 Cloud Account Compromise](02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md) | IR-PB-10 |
| [PB-11 Supply Chain Compromise](02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | IR-PB-11 |
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

### 04 - Compliance Mapping
| Document | Framework |
|---|---|
| [Folder overview](04-compliance-mapping/README.md) | - |
| [ISO/IEC 27001:2022](04-compliance-mapping/iso-27001-2022-mapping.md) | MAP-001 |
| [NIST CSF 2.0](04-compliance-mapping/nist-csf-2.0-mapping.md) | MAP-002 |
| [SOC 2](04-compliance-mapping/soc2-mapping.md) | MAP-003 |
| [PCI DSS v4.0.1](04-compliance-mapping/pci-dss-4.0.1-mapping.md) | MAP-004 |
| [GDPR](04-compliance-mapping/gdpr-mapping.md) | MAP-005 |
| [HIPAA](04-compliance-mapping/hipaa-mapping.md) | MAP-006 |

### Templates
- [Document Template](templates/document-template.md)

## Conventions
- Markdown, kebab-case filenames
- Every document starts with the standard header (ID, version, status, owner)
- Status: Draft -> Review -> Approved -> Retired
- Update the README index when adding documents
