# PB-03 Data Breach / Data Leakage Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-03 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to confirmed or suspected unauthorized access, disclosure, or exfiltration of sensitive, personal, or regulated data.
**ATT&CK:** T1530 Data from Cloud Storage, T1041 Exfiltration Over C2, T1567 Exfiltration to Web Service, T1213 Data from Information Repositories.

## 2. Triggers / Detection
- [ ] DLP alerts; unusual large downloads/transfers
- [ ] Publicly exposed storage bucket/database found
- [ ] Third party, researcher, or threat actor claims possession of data
- [ ] Data posted on paste/leak sites or dark web monitoring hit
- [ ] Misdirected email/mis-sharing with sensitive content
- [ ] Lost/stolen device with unencrypted data (see PB-08)

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Internal mis-sharing, contained, non-sensitive | SEV4 |
| Limited sensitive data, small number of individuals | SEV3 |
| Personal/regulated data of many individuals | SEV2 |
| Large-scale or highly sensitive data, public exposure | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| Data Owner | Identify data, business impact |
| DPO / Privacy Officer | Assess notification duties |

## 5. Investigation
- [ ] Confirm whether data was actually accessed/exfiltrated vs. only exposed
- [ ] Identify data types and classification (PII, PHI, PCI, credentials, IP)
- [ ] Determine volume, number and location of affected individuals/customers
- [ ] Identify access path, actor (internal/external), and time window
- [ ] Review access logs, DLP, proxy, cloud audit, database logs
- [ ] Determine if data was encrypted/tokenized and whether keys were exposed
- [ ] Establish whether data is public or in the hands of a threat actor

## 6. Containment
- [ ] Revoke access, rotate exposed credentials/keys/tokens
- [ ] Remove public exposure (bucket policy, firewall rule, link sharing)
- [ ] Block exfiltration channels and attacker infrastructure
- [ ] Request takedown of published data where possible
- [ ] Preserve logs before they roll over

## 7. Eradication
- [ ] Fix root cause (misconfiguration, vulnerability, excessive permissions)
- [ ] Remove attacker access and persistence
- [ ] Review similar exposures across environment

## 8. Recovery
- [ ] Validate controls restored; monitor for continued access or data resale
- [ ] Offer remediation to affected individuals (credit monitoring, password resets) as decided

## 9. Notification (Legal-led)
- [ ] Determine applicable laws and contracts (GDPR 72 h to regulator, HIPAA, state laws, PCI, customer contracts)
- [ ] Document risk-of-harm assessment and notification decision rationale
- [ ] Notify regulators, affected individuals, partners, insurer, law enforcement as required
- [ ] Prepare FAQ, call center scripts, and public statement (see Crisis Management Plan)
- [ ] Keep a record of all breaches, including those not notified

## 10. Evidence to Collect
Access/audit logs, DLP events, configuration snapshots, data inventory mapping, affected-subject list, communications and decision records.

### 10.1 Closure Criteria & Metrics
- Exposure closed, notifications completed, root cause remediated
- Metrics: records affected, time exposed, time to detect/contain/notify

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
