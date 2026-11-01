# ISO/IEC 27001:2022 Mapping

| Field | Value |
|---|---|
| Document ID | MAP-001 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | ISO/IEC 27001:2022 (Annex A, 93 controls) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Maps this repository's documents to ISO/IEC 27001:2022 management system clauses and Annex A controls to show coverage and gaps.

## 2. Notes
- Annex A has 93 controls in four themes: Organizational (5.x), People (6.x), Physical (7.x), Technological (8.x).
- The 2013 edition transition period has ended; use 2022 control numbering (includes Amd 1:2024 climate-change clause updates, which do not change Annex A numbering).
- Selecting which controls apply, and justifying exclusions, belongs in your Statement of Applicability (not yet in this repo).

**Coverage legend**
- **Covered**: a repo document addresses the requirement's intent (still needs tailoring and implementation evidence)
- **Partial**: a repo document addresses part of it, or only the response/recovery side
- **Gap**: no document in this repo yet; see [Gap Analysis](gap-analysis.md)

> Coverage reflects what the **draft documents in this repo** address, not whether controls are implemented or effective. This mapping is indicative, is not legal or audit advice, and should be validated with your compliance owner or auditor.

## 3. Management System Clauses (selected)
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 6.1.2 | Information security risk assessment | Partial | [GOV-001](../01-governance/risk-register-template.md) | Register and scales; methodology document needed |
| 6.1.3 | Information security risk treatment | Partial | [GOV-001](../01-governance/risk-register-template.md) | Treatment tracked; Statement of Applicability not yet written |
| 7.5 | Documented information | Partial | [TPL](../templates/document-template.md) | Standard header with version/owner/status |
| 8.2 | Risk assessment (operation) | Partial | [GOV-001](../01-governance/risk-register-template.md) | Periodic review cadence defined |
| 9.1 | Monitoring, measurement, analysis and evaluation | Gap | - | Metrics and KPI guide needed |
| 9.2 | Internal audit | Gap | - | No audit program document |
| 9.3 | Management review | Gap | - | No management review template |
| 10.2 | Nonconformity and corrective action | Partial | [IR-004](../02-defensive/incident-response/post-incident-review-template.md) | Corrective action plan in post-incident review |

## 4. Annex A Controls
**Coverage summary (93 items):** Covered 17 | Partial 29 | Gap 47

### 5. Organizational controls
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 5.1 | Policies for information security | Partial | [GOV-002](../01-governance/access-control-policy.md), [GOV-003](../01-governance/change-management-policy.md) | Topic policies exist; overarching Information Security Policy not yet written |
| 5.2 | Information security roles and responsibilities | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Roles defined per plan; no enterprise security roles document |
| 5.3 | Segregation of duties | Covered | [GOV-002](../01-governance/access-control-policy.md), [GOV-003](../01-governance/change-management-policy.md) | Separation of duties in access and change processes |
| 5.4 | Management responsibilities | Gap | - |  |
| 5.5 | Contact with authorities | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Regulator and law-enforcement contact in IR and crisis plans |
| 5.6 | Contact with special interest groups | Gap | - |  |
| 5.7 | Threat intelligence | Partial | [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Intel-driven hunt hypotheses; no threat intelligence program document |
| 5.8 | Information security in project management | Gap | - |  |
| 5.9 | Inventory of information and other associated assets | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Asset inventory appendix in DRP only |
| 5.10 | Acceptable use of information and other associated assets | Gap | - |  |
| 5.11 | Return of assets | Gap | - |  |
| 5.12 | Classification of information | Gap | - |  |
| 5.13 | Labelling of information | Gap | - |  |
| 5.14 | Information transfer | Gap | - |  |
| 5.15 | Access control | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| 5.16 | Identity management | Covered | [GOV-002](../01-governance/access-control-policy.md) | Joiner/mover/leaver process |
| 5.17 | Authentication information | Partial | [GOV-002](../01-governance/access-control-policy.md) | References a Password Policy not yet written |
| 5.18 | Access rights | Covered | [GOV-002](../01-governance/access-control-policy.md) | Access requests, approvals, and reviews |
| 5.19 | Information security in supplier relationships | Partial | [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Response only; no vendor risk policy |
| 5.20 | Addressing information security within supplier agreements | Gap | - |  |
| 5.21 | Managing information security in the ICT supply chain | Partial | [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Supply chain incident response only |
| 5.22 | Monitoring, review and change management of supplier services | Partial | [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Vendor access restriction during incidents |
| 5.23 | Information security for use of cloud services | Partial | [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md) | Cloud incident response only; no cloud security standard |
| 5.24 | Information security incident management planning and preparation | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md), [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) |  |
| 5.25 | Assessment and decision on information security events | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) | Severity classification and triage |
| 5.26 | Response to information security incidents | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) |  |
| 5.27 | Learning from information security incidents | Covered | [IR-004](../02-defensive/incident-response/post-incident-review-template.md) |  |
| 5.28 | Collection of evidence | Covered | [IR-005](../02-defensive/incident-response/chain-of-custody-form.md) |  |
| 5.29 | Information security during disruption | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) |  |
| 5.30 | ICT readiness for business continuity | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) | RTO/RPO and recovery procedures |
| 5.31 | Legal, statutory, regulatory and contractual requirements | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Breach notification obligations; no legal register |
| 5.32 | Intellectual property rights | Gap | - |  |
| 5.33 | Protection of records | Gap | - |  |
| 5.34 | Privacy and protection of PII | Partial | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Breach handling only; no privacy program |
| 5.35 | Independent review of information security | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Pentest provides independent technical assurance; no audit program |
| 5.36 | Compliance with policies, rules and standards for information security | Gap | - |  |
| 5.37 | Documented operating procedures | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md), [TPL](../templates/document-template.md) | Runbooks, playbooks, standard template |

### 6. People controls
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 6.1 | Screening | Gap | - |  |
| 6.2 | Terms and conditions of employment | Gap | - |  |
| 6.3 | Information security awareness, education and training | Gap | - |  |
| 6.4 | Disciplinary process | Partial | [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md) | HR-led disciplinary process referenced |
| 6.5 | Responsibilities after termination or change of employment | Partial | [GOV-002](../01-governance/access-control-policy.md) | Leaver access removal |
| 6.6 | Confidentiality or non-disclosure agreements | Partial | [OFF-002](../03-offensive/statement-of-work.md) | Confidentiality clause for testers only |
| 6.7 | Remote working | Gap | - |  |
| 6.8 | Information security event reporting | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md) | Reporting channels referenced; no reporting procedure |

### 7. Physical controls
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 7.1 | Physical security perimeters | Gap | - |  |
| 7.2 | Physical entry | Partial | [GOV-002](../01-governance/access-control-policy.md) | Physical access in access control policy |
| 7.3 | Securing offices, rooms and facilities | Gap | - |  |
| 7.4 | Physical security monitoring | Gap | - |  |
| 7.5 | Protecting against physical and environmental threats | Gap | - |  |
| 7.6 | Working in secure areas | Gap | - |  |
| 7.7 | Clear desk and clear screen | Gap | - |  |
| 7.8 | Equipment siting and protection | Gap | - |  |
| 7.9 | Security of assets off-premises | Partial | [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md) | Lost/stolen device response |
| 7.10 | Storage media | Partial | [IR-005](../02-defensive/incident-response/chain-of-custody-form.md) | Handling of evidence media only |
| 7.11 | Supporting utilities | Gap | - |  |
| 7.12 | Cabling security | Gap | - |  |
| 7.13 | Equipment maintenance | Gap | - |  |
| 7.14 | Secure disposal or re-use of equipment | Gap | - |  |

### 8. Technological controls
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 8.1 | User endpoint devices | Partial | [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md) | Lost device response only |
| 8.2 | Privileged access rights | Covered | [GOV-002](../01-governance/access-control-policy.md) | PAM, JIT, break-glass |
| 8.3 | Information access restriction | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| 8.4 | Access to source code | Gap | - |  |
| 8.5 | Secure authentication | Covered | [GOV-002](../01-governance/access-control-policy.md) | MFA, lockout, session timeout |
| 8.6 | Capacity management | Gap | - |  |
| 8.7 | Protection against malware | Partial | [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md) | Response only; no anti-malware standard |
| 8.8 | Management of technical vulnerabilities | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Pentest supports vulnerability discovery; no patch/vuln management procedure |
| 8.9 | Configuration management | Partial | [GOV-003](../01-governance/change-management-policy.md) | Baselines updated after change |
| 8.10 | Information deletion | Gap | - |  |
| 8.11 | Data masking | Gap | - |  |
| 8.12 | Data leakage prevention | Partial | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md) | Response to leakage; no DLP standard |
| 8.13 | Information backup | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Backup management section |
| 8.14 | Redundancy of information processing facilities | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Recovery strategies include replication/failover |
| 8.15 | Logging | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Log sources referenced; no logging standard |
| 8.16 | Monitoring activities | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) |  |
| 8.17 | Clock synchronization | Gap | - |  |
| 8.18 | Use of privileged utility programs | Gap | - |  |
| 8.19 | Installation of software on operational systems | Gap | - |  |
| 8.20 | Networks security | Gap | - |  |
| 8.21 | Security of network services | Gap | - |  |
| 8.22 | Segregation of networks | Gap | - |  |
| 8.23 | Web filtering | Gap | - |  |
| 8.24 | Use of cryptography | Gap | - |  |
| 8.25 | Secure development life cycle | Gap | - |  |
| 8.26 | Application security requirements | Gap | - |  |
| 8.27 | Secure system architecture and engineering principles | Gap | - |  |
| 8.28 | Secure coding | Gap | - |  |
| 8.29 | Security testing in development and acceptance | Gap | - |  |
| 8.30 | Outsourced development | Gap | - |  |
| 8.31 | Separation of development, test and production environments | Gap | - |  |
| 8.32 | Change management | Covered | [GOV-003](../01-governance/change-management-policy.md) |  |
| 8.33 | Test information | Gap | - |  |
| 8.34 | Protection of information systems during audit testing | Partial | [OFF-001](../03-offensive/rules-of-engagement.md) | Safety constraints and stop conditions |


## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
