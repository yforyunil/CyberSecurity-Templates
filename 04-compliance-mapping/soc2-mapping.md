# SOC 2 Trust Services Criteria Mapping

| Field | Value |
|---|---|
| Document ID | MAP-003 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | AICPA Trust Services Criteria (2017, with 2022 revised points of focus) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Maps repository documents to the SOC 2 Trust Services Criteria to support readiness planning.

## 2. Notes
- **Security (Common Criteria CC1-CC9)** is always in scope. Availability (A), Confidentiality (C), Processing Integrity (PI), and Privacy (P) are optional categories you select with your auditor.
- SOC 2 auditors test **operating evidence** (tickets, logs, reviews, training records), not just documents. Use these mappings to plan evidence collection.

**Coverage legend**
- **Covered**: a repo document addresses the requirement's intent (still needs tailoring and implementation evidence)
- **Partial**: a repo document addresses part of it, or only the response/recovery side
- **Gap**: no document in this repo yet; see [Gap Analysis](gap-analysis.md)

> Coverage reflects what the **draft documents in this repo** address, not whether controls are implemented or effective. This mapping is indicative, is not legal or audit advice, and should be validated with your compliance owner or auditor.

## 3. Security: Common Criteria
**Coverage summary (33 items):** Covered 12 | Partial 15 | Gap 6

### CC1 Control Environment
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC1.1 | Demonstrates commitment to integrity and ethical values | Gap | - | Code of conduct / ethics policy needed |
| CC1.2 | Board exercises oversight of internal control | Gap | - |  |
| CC1.3 | Establishes structure, authority, and responsibility | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Operational structures only |
| CC1.4 | Demonstrates commitment to competence | Gap | - | Training plan needed |
| CC1.5 | Enforces accountability | Partial | [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md) | Disciplinary reference |

### CC2 Communication and Information
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC2.1 | Obtains or generates relevant, quality information | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) |  |
| CC2.2 | Internally communicates information and responsibilities | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Incident and crisis communications |
| CC2.3 | Communicates with external parties | Covered | [BC-003](../02-defensive/business-continuity/crisis-management-plan.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Customers, regulators, partners |

### CC3 Risk Assessment
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC3.1 | Specifies suitable objectives | Gap | - |  |
| CC3.2 | Identifies and analyzes risk | Covered | [GOV-001](../01-governance/risk-register-template.md) |  |
| CC3.3 | Considers the potential for fraud | Partial | [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md) | BEC and insider scenarios |
| CC3.4 | Identifies and assesses changes that could significantly impact controls | Covered | [GOV-003](../01-governance/change-management-policy.md), [GOV-001](../01-governance/risk-register-template.md) |  |

### CC4 Monitoring Activities
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC4.1 | Performs ongoing and/or separate evaluations | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Penetration testing; no internal audit program |
| CC4.2 | Evaluates and communicates deficiencies | Partial | [OFF-004](../03-offensive/pentest-report-template.md), [IR-004](../02-defensive/incident-response/post-incident-review-template.md) | Findings and corrective actions |

### CC5 Control Activities
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC5.1 | Selects and develops control activities | Partial | [GOV-001](../01-governance/risk-register-template.md) |  |
| CC5.2 | Selects and develops general controls over technology | Partial | [GOV-002](../01-governance/access-control-policy.md), [GOV-003](../01-governance/change-management-policy.md) |  |
| CC5.3 | Deploys control activities through policies and procedures | Partial | [GOV-002](../01-governance/access-control-policy.md), [GOV-003](../01-governance/change-management-policy.md), [TPL](../templates/document-template.md) | More policies needed |

### CC6 Logical and Physical Access Controls
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC6.1 | Implements logical access security software, infrastructure, and architectures | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| CC6.2 | Registers and authorizes new users before issuing credentials | Covered | [GOV-002](../01-governance/access-control-policy.md) | Joiner process |
| CC6.3 | Authorizes, modifies, or removes access (least privilege, separation of duties) | Covered | [GOV-002](../01-governance/access-control-policy.md) | Mover/leaver, access reviews |
| CC6.4 | Restricts physical access to facilities and assets | Partial | [GOV-002](../01-governance/access-control-policy.md) |  |
| CC6.5 | Discontinues logical and physical protections over assets when no longer needed (disposal) | Gap | - | Data retention and disposal policy needed |
| CC6.6 | Implements logical access security measures against threats from outside system boundaries | Partial | [GOV-002](../01-governance/access-control-policy.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md) | Remote access; network standards needed |
| CC6.7 | Restricts transmission, movement, and removal of information | Gap | - | Encryption and data transfer policy needed |
| CC6.8 | Prevents or detects unauthorized or malicious software | Partial | [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md) | Response side only |

### CC7 System Operations
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC7.1 | Uses detection and monitoring procedures to identify configuration changes and new vulnerabilities | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md), [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Vulnerability management procedure needed |
| CC7.2 | Monitors system components for anomalies indicative of malicious acts, disasters, and errors | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) |  |
| CC7.3 | Evaluates security events to determine whether they are incidents | Covered | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| CC7.4 | Responds to identified security incidents through an incident response program | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md), [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-005](../02-defensive/incident-response/chain-of-custody-form.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) |  |
| CC7.5 | Identifies, develops, and implements activities to recover from incidents | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [IR-004](../02-defensive/incident-response/post-incident-review-template.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) | Includes lessons learned |

### CC8 Change Management
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC8.1 | Authorizes, designs, develops, tests, approves, and implements changes | Covered | [GOV-003](../01-governance/change-management-policy.md) | Emergency changes and rollback included |

### CC9 Risk Mitigation
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| CC9.1 | Identifies, selects, and develops risk mitigation activities for business disruptions | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md), [GOV-001](../01-governance/risk-register-template.md) |  |
| CC9.2 | Assesses and manages risks associated with vendors and business partners | Partial | [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Vendor risk management policy needed |

## 4. Availability (optional)
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| A1.1 | Maintains, monitors, and evaluates current processing capacity and use | Gap | - | Capacity management standard needed |
| A1.2 | Authorizes, designs, implements, operates, approves, maintains, and monitors environmental protections, software, data backup processes, and recovery infrastructure | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Backup and recovery strategy |
| A1.3 | Tests recovery plan procedures supporting system recovery | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) | Testing and maintenance sections |

## 5. Confidentiality (optional)
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| C1.1 | Identifies and maintains confidential information | Gap | - | Data classification policy needed |
| C1.2 | Disposes of confidential information | Gap | - | Retention and disposal policy needed |

## 6. Processing Integrity and Privacy (optional)
| Ref | Requirement / Control | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| PI1.1-PI1.5 | Processing integrity criteria | Gap | - | Only if Processing Integrity is in scope |
| P1-P8 | Privacy criteria | Partial | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Only if Privacy is in scope; breach handling only |

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
