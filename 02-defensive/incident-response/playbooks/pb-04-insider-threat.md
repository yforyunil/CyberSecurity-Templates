# PB-04 Insider Threat Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-04 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to malicious, negligent, or compromised insiders (employees, contractors) misusing access to harm the organization.
**ATT&CK:** T1078 Valid Accounts, T1213 Data from Information Repositories, T1052 Exfiltration Over Physical Medium, T1567 Exfiltration to Web Service, T1485 Data Destruction.
**Note:** Handle with strict confidentiality. Involve HR and Legal before any action against an individual.

## 2. Triggers / Detection
- [ ] DLP/UEBA alerts: unusual downloads, after-hours access, mass copying
- [ ] Use of personal cloud/email/USB for company data
- [ ] Access outside role, repeated policy violations, privilege abuse
- [ ] Resignation or termination notice combined with unusual data activity
- [ ] Tip from colleague/manager/ethics hotline
- [ ] Sabotage indicators (deleted data, logic bombs, disabled controls)

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Policy violation, negligent, no data loss | SEV4 |
| Limited unauthorized access or data copy | SEV3 |
| Sensitive data exfiltration or privilege abuse | SEV2 |
| Sabotage, large-scale theft, executive/admin involvement | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| HR | Employment actions, interviews |
| Legal | Evidence admissibility, privacy and labor law |

## 5. Investigation (need-to-know team only)
- [ ] Obtain written authorization from Legal/HR before monitoring or collecting
- [ ] Define scope and time window; avoid tipping off the subject
- [ ] Collect logs: authentication, file access, email, proxy, DLP, print, USB, badge
- [ ] Review data accessed vs. role entitlements
- [ ] Establish intent where possible (malicious vs. negligent vs. compromised account)
- [ ] Rule out account compromise by an external actor
- [ ] Identify collusion or external recipients

## 6. Containment
- [ ] Coordinate timing with HR: restrict/disable access at the agreed moment
- [ ] Disable accounts, VPN, tokens, badge; retrieve devices and media
- [ ] Remote-wipe/lock company devices as appropriate
- [ ] Preserve mailbox, home drive, and device images before reassignment

## 7. Eradication
- [ ] Remove backdoors, shared credentials, and personal-device access
- [ ] Rotate shared secrets and credentials the individual knew
- [ ] Review permissions of peers and similar roles

## 8. Recovery
- [ ] Restore any deleted/modified data and verify integrity
- [ ] Re-establish normal operations; address team/knowledge gaps

## 9. Communications & Actions
- [ ] Restrict information to need-to-know; no speculation in chat/email
- [ ] HR-led disciplinary or termination process; Legal-led civil/criminal referral decision
- [ ] Cease-and-desist or data return demand if applicable
- [ ] Notify data owners and, if required, regulators/customers (see PB-03)

## 10. Evidence to Collect
Forensic images, access/DLP/proxy/email logs, timeline of actions, HR records, interview notes. Use full chain of custody.

### 10.1 Closure Criteria & Metrics
- Access removed, evidence preserved, decision made by HR/Legal, controls improved
- Metrics: time to detect, data affected, access-control gaps found

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
