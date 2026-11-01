# PB-01 Ransomware Response Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-01 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to malware that encrypts or locks systems/data for extortion, including double-extortion (data theft plus encryption).
**ATT&CK:** T1486 Data Encrypted for Impact, T1490 Inhibit System Recovery, T1567 Exfiltration, T1021 Remote Services, T1078 Valid Accounts.

## 2. Triggers / Detection
- [ ] Mass file renames or new extensions; ransom notes on shares/desktops
- [ ] EDR ransomware behavior alerts; shadow copy deletion (vssadmin, wmic)
- [ ] Sudden spike in file I/O or SMB traffic
- [ ] User reports of inaccessible files
- [ ] Threat actor contact or leak-site listing

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Single endpoint, contained, no spread | SEV3 |
| Multiple hosts or a file server | SEV2 |
| Domain controller, critical systems, or confirmed exfiltration | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |

## 5. Investigation
- [ ] Open incident record; start timeline and decision log
- [ ] Identify patient zero and initial access vector (phishing, RDP/VPN, vulnerable edge device, third party)
- [ ] Identify ransomware family/variant (ransom note, extension, sample hash); check for known decryptors
- [ ] Determine scope: encrypted hosts, shares, backups, cloud storage
- [ ] Check for exfiltration (large outbound transfers, rclone/MEGA/cloud sync tools)
- [ ] Review privileged account use, new accounts, GPO changes, scheduled tasks, remote tools
- [ ] Determine whether domain is compromised (DCs, krbtgt, DCSync indicators)

## 6. Containment
- [ ] Isolate affected hosts via EDR/network (do not power off unless necessary; preserve memory first where feasible)
- [ ] Disable compromised accounts; block malicious IPs/domains at perimeter
- [ ] Segment or shut down affected network zones and file shares
- [ ] Protect backups: disconnect, verify immutability, suspend backup jobs that could overwrite clean data
- [ ] Disable or restrict VPN/remote access if it is the entry point
- [ ] Preserve evidence before wiping (see Section 10)

## 7. Eradication
- [ ] Remove malware, persistence, and attacker tools from all affected systems
- [ ] Close the initial access path (patch, MFA, disable exposed service)
- [ ] Reset credentials for affected and privileged accounts; rotate service accounts and secrets
- [ ] If AD compromised: staged krbtgt reset (twice), review of trusts, GPOs, and ACLs
- [ ] Rebuild from known-good images rather than cleaning where integrity is uncertain

## 8. Recovery
- [ ] Verify backups are clean (scan, test restore in isolated environment)
- [ ] Restore in priority order (identity, core infrastructure, critical apps, then rest)
- [ ] Reconnect in stages with enhanced monitoring and EDR coverage
- [ ] Validate data integrity and application function with owners
- [ ] Monitor for re-infection for at least 30 days

## 9. Communications & Decisions
- [ ] Notify executives, legal, and cyber insurer early (follow policy conditions)
- [ ] Engage external IR/forensics retainer if needed
- [ ] Law enforcement notification (decision with Legal)
- [ ] Regulatory/customer notification if personal or regulated data exfiltrated
- [ ] Ransom payment: executive and legal decision only; check sanctions exposure; never decided by IR team alone
- [ ] Use out-of-band communication if corporate email/chat is affected

## 10. Evidence to Collect
Ransom note, encrypted sample files, malware sample and hashes, memory and disk images of patient zero, EDR/SIEM logs, firewall/proxy/VPN logs, AD logs, backup logs.

### 10.1 Closure Criteria & Metrics
- All systems restored and validated; access path closed; credentials reset
- Metrics: time to detect, time to isolate, hosts affected, downtime, data exfiltrated (Y/N), recovery time

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
