# NIST Cybersecurity Framework 2.0 Mapping

| Field | Value |
|---|---|
| Document ID | MAP-002 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | NIST CSF 2.0 (February 2024) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Maps repository documents to NIST CSF 2.0 Functions, Categories, and key Subcategories.

## 2. Notes
- CSF 2.0 has six Functions: Govern (GV), Identify (ID), Protect (PR), Detect (DE), Respond (RS), Recover (RC).
- The Respond and Recover functions are the repo's strongest areas; Govern (oversight), Identify (asset management), and Protect (awareness, data security, platform security) have the most gaps.
- Subcategory IDs below are a selected, high-relevance subset; extend as you add documents.

**Coverage legend**
- **Covered**: a repo document addresses the requirement's intent (still needs tailoring and implementation evidence)
- **Partial**: a repo document addresses part of it, or only the response/recovery side
- **Gap**: no document in this repo yet; see [Gap Analysis](gap-analysis.md)

> Coverage reflects what the **draft documents in this repo** address, not whether controls are implemented or effective. This mapping is indicative, is not legal or audit advice, and should be validated with your compliance owner or auditor.

## 3. Category-Level Mapping
**Coverage summary (22 items):** Covered 10 | Partial 9 | Gap 3

### GOVERN (GV)
| Ref | Category | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| GV.OC | Organizational Context | Partial | [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) | BIA and legal/regulatory requirements referenced |
| GV.RM | Risk Management Strategy | Partial | [GOV-001](../01-governance/risk-register-template.md) | Risk register and acceptance process; no risk strategy document |
| GV.RR | Roles, Responsibilities, and Authorities | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Operational roles defined; no governance roles document |
| GV.PO | Policy | Partial | [GOV-002](../01-governance/access-control-policy.md), [GOV-003](../01-governance/change-management-policy.md), [TPL](../templates/document-template.md) | Two policies; Information Security Policy missing |
| GV.OV | Oversight | Gap | - | Metrics, audit, and management review documents needed |
| GV.SC | Cybersecurity Supply Chain Risk Management | Partial | [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Incident response only; vendor risk policy needed |

### IDENTIFY (ID)
| Ref | Category | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| ID.AM | Asset Management | Gap | - | Asset inventory standard needed |
| ID.RA | Risk Assessment | Partial | [GOV-001](../01-governance/risk-register-template.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md), [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Risk register, threat-informed hunting, pentest findings |
| ID.IM | Improvement | Covered | [IR-004](../02-defensive/incident-response/post-incident-review-template.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Lessons learned, exercises, plan maintenance |

### PROTECT (PR)
| Ref | Category | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| PR.AA | Identity Management, Authentication, and Access Control | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| PR.AT | Awareness and Training | Gap | - | Security awareness plan needed |
| PR.DS | Data Security | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Backups and breach response; classification and crypto policies needed |
| PR.PS | Platform Security | Partial | [GOV-003](../01-governance/change-management-policy.md) | Config management via change control; hardening and patching standards needed |
| PR.IR | Technology Infrastructure Resilience | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Recovery strategy and capacity; architecture standards needed |

### DETECT (DE)
| Ref | Category | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| DE.CM | Continuous Monitoring | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) |  |
| DE.AE | Adverse Event Analysis | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |

### RESPOND (RS)
| Ref | Category | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| RS.MA | Incident Management | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md), [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) |  |
| RS.AN | Incident Analysis | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-005](../02-defensive/incident-response/chain-of-custody-form.md), [IR-003](../02-defensive/incident-response/incident-report-template.md) |  |
| RS.CO | Incident Response Reporting and Communication | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md), [IR-003](../02-defensive/incident-response/incident-report-template.md) |  |
| RS.MI | Incident Mitigation | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Containment and eradication in every playbook |

### RECOVER (RC)
| Ref | Category | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| RC.RP | Incident Recovery Plan Execution | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| RC.CO | Incident Recovery Communication | Covered | [BC-003](../02-defensive/business-continuity/crisis-management-plan.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |

## 4. Subcategory-Level Mapping (selected)
**Coverage summary (46 items):** Covered 36 | Partial 9 | Gap 1

| Ref | Outcome | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| GV.PO-01 | Policy for managing cybersecurity risks is established | Partial | [GOV-002](../01-governance/access-control-policy.md), [GOV-003](../01-governance/change-management-policy.md) | Overarching policy missing |
| ID.RA-01 | Vulnerabilities in assets are identified, validated, and recorded | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Via pentest; no vulnerability management procedure |
| ID.RA-02 | Cyber threat intelligence is received from information sharing sources | Gap | - | Threat intel program document needed |
| ID.RA-03 | Internal and external threats are identified and recorded | Partial | [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md), [GOV-001](../01-governance/risk-register-template.md) |  |
| ID.RA-05 | Threats, vulnerabilities, likelihoods, and impacts are used to understand inherent risk | Covered | [GOV-001](../01-governance/risk-register-template.md) | Likelihood x impact scoring |
| ID.RA-06 | Risk responses are chosen, prioritized, planned, tracked, and communicated | Covered | [GOV-001](../01-governance/risk-register-template.md) | Treatment options and owners |
| ID.RA-07 | Changes and exceptions are managed, assessed, recorded, and tracked | Covered | [GOV-003](../01-governance/change-management-policy.md), [GOV-001](../01-governance/risk-register-template.md) | Change process and risk acceptance |
| ID.IM-02 | Improvements are identified from security tests and exercises | Covered | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md), [IR-004](../02-defensive/incident-response/post-incident-review-template.md) |  |
| ID.IM-03 | Improvements are identified from execution of operational processes | Covered | [IR-004](../02-defensive/incident-response/post-incident-review-template.md) |  |
| ID.IM-04 | Incident response plans and other cybersecurity plans are established, communicated, maintained, and improved | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) |  |
| PR.AA-01 | Identities and credentials for authorized users, services, and hardware are managed | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| PR.AA-03 | Users, services, and hardware are authenticated | Covered | [GOV-002](../01-governance/access-control-policy.md) | MFA requirements |
| PR.AA-05 | Access permissions and authorizations are defined, managed, enforced, and reviewed (least privilege, separation of duties) | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| PR.AA-06 | Physical access to assets is managed, monitored, and enforced | Partial | [GOV-002](../01-governance/access-control-policy.md) | Physical access section only |
| PR.DS-11 | Backups of data are created, protected, maintained, and tested | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Backup management and testing |
| PR.PS-01 | Configuration management practices are established and applied | Partial | [GOV-003](../01-governance/change-management-policy.md) |  |
| PR.PS-04 | Log records are generated and made available for continuous monitoring | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) | Logging standard needed |
| PR.IR-03 | Mechanisms are implemented to achieve resilience requirements | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) |  |
| DE.CM-01 | Networks and network services are monitored | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) |  |
| DE.CM-03 | Personnel activity and technology usage are monitored | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md) |  |
| DE.CM-09 | Computing hardware and software, runtime environments, and their data are monitored | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) |  |
| DE.AE-02 | Potentially adverse events are analyzed | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) |  |
| DE.AE-03 | Information is correlated from multiple sources | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) |  |
| DE.AE-04 | Estimated impact and scope of adverse events are understood | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| DE.AE-07 | Cyber threat intelligence and other contextual information are integrated into the analysis | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Enrichment steps; no TI program |
| DE.AE-08 | Incidents are declared when adverse events meet defined criteria | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) | Severity criteria |
| RS.MA-01 | The incident response plan is executed once an incident is declared | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md) |  |
| RS.MA-02 | Incident reports are triaged and validated | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) |  |
| RS.MA-03 | Incidents are categorized and prioritized | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| RS.MA-04 | Incidents are escalated or elevated as needed | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) |  |
| RS.MA-05 | Criteria for initiating incident recovery are applied | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md) | Closure and recovery criteria in playbooks |
| RS.AN-03 | Analysis is performed to establish what has taken place and the root cause | Covered | [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-004](../02-defensive/incident-response/post-incident-review-template.md) |  |
| RS.AN-06 | Actions performed during an investigation are recorded, and integrity and provenance are preserved | Covered | [IR-005](../02-defensive/incident-response/chain-of-custody-form.md), [IR-003](../02-defensive/incident-response/incident-report-template.md) |  |
| RS.AN-07 | Incident data and metadata are collected, and integrity and provenance are preserved | Covered | [IR-005](../02-defensive/incident-response/chain-of-custody-form.md) |  |
| RS.AN-08 | An incident magnitude is estimated and validated | Covered | [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| RS.CO-02 | Internal and external stakeholders are notified of incidents | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) |  |
| RS.CO-03 | Information is shared with designated internal and external stakeholders | Covered | [BC-003](../02-defensive/business-continuity/crisis-management-plan.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| RS.MI-01 | Incidents are contained | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) |  |
| RS.MI-02 | Incidents are eradicated | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) |  |
| RC.RP-01 | The recovery portion of the incident response plan is executed once initiated | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) |  |
| RC.RP-02 | Recovery actions are selected, scoped, prioritized, and performed | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| RC.RP-03 | The integrity of backups and other restoration assets is verified before use | Covered | [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) |  |
| RC.RP-05 | The integrity of restored assets is verified, systems and services are restored, and normal operating status is confirmed | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) |  |
| RC.RP-06 | The end of incident recovery is declared and incident-related documentation is completed | Covered | [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-004](../02-defensive/incident-response/post-incident-review-template.md) |  |
| RC.CO-03 | Recovery activities and progress are communicated to designated stakeholders | Covered | [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) |  |
| RC.CO-04 | Public updates on incident recovery are shared using approved methods and messaging | Covered | [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) |  |

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
