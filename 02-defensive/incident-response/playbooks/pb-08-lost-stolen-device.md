# PB-08 Lost or Stolen Device Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-08 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to loss or theft of laptops, phones, tablets, removable media, or security tokens.
**ATT&CK:** T1078 Valid Accounts, T1005 Data from Local System.

## 2. Triggers / Detection
- [ ] User or manager report of loss/theft (physical or travel)
- [ ] MDM/EDR device offline or reporting from unexpected location
- [ ] Police report received

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Fully encrypted, locked, MDM-managed, no sensitive data | SEV4 |
| Encrypted device with access to corporate accounts | SEV3 |
| Unencrypted device or contains sensitive/regulated data | SEV2 |
| Executive/admin device, or confirmed data misuse | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| Service Desk | Intake and device actions |
| Physical Security / HR | Theft reporting, travel incidents |

## 5. Investigation
- [ ] Collect: device type, serial/asset tag, owner, last seen time/location, circumstances
- [ ] Confirm encryption status (BitLocker/FileVault), screen lock, MDM enrollment
- [ ] Identify data stored locally and accounts/tokens/certificates on device
- [ ] Review recent sign-ins and activity from the device and user account
- [ ] Assess likelihood of targeted theft (travel, espionage, break-in)

## 6. Containment
- [ ] Remote lock and, if warranted, remote wipe (document decision and timing)
- [ ] Revoke device certificates, VPN profiles, tokens, and sessions
- [ ] Reset user's passwords; re-enroll MFA if phone/token lost
- [ ] Disable device in IdP/MDM; add to blocklist
- [ ] Suspend access for lost security keys/smartcards

## 7. Eradication
- [ ] Rotate any secrets stored on device (SSH keys, API keys, saved credentials)
- [ ] Remove device from asset inventory and mark status

## 8. Recovery
- [ ] Issue replacement device; restore data from backup
- [ ] Monitor account for 14-30 days

## 9. Communications & Notifications
- [ ] File police report where theft is suspected
- [ ] Assess breach notification duty if unencrypted personal data (use PB-03)
- [ ] Remind user of reporting expectations and travel guidance

## 10. Evidence to Collect
Report details, MDM logs, encryption status proof, wipe confirmation, police report number.

### 10.1 Closure Criteria & Metrics
- Device locked/wiped, credentials rotated, notification decision documented
- Metrics: time from loss to report, time to lock/wipe

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
