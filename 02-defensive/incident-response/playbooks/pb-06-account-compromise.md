# PB-06 Account / Credential Compromise Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-06 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to compromised user, privileged, service, or cloud identities.
**ATT&CK:** T1078 Valid Accounts, T1110 Brute Force, T1555 Credentials from Password Stores, T1528 Steal Application Access Token, T1621 MFA Request Generation.

## 2. Triggers / Detection
- [ ] Impossible travel, anonymizer/unusual geolocation sign-ins
- [ ] MFA fatigue (repeated prompts), new MFA method registered
- [ ] Credential stuffing/brute force success; leaked credentials notice
- [ ] Unexpected privilege changes, new admin accounts, new API keys
- [ ] User reports unknown activity or lost control of account
- [ ] Service account used interactively or from unusual host

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Standard user, blocked or no activity | SEV4 |
| Standard user, malicious activity observed | SEV3 |
| Privileged, service, or executive account | SEV2 |
| Domain/cloud admin or root with confirmed misuse | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| IAM Team | Reset credentials, token revocation, MFA reset |

## 5. Investigation
- [ ] Validate with user via out-of-band channel
- [ ] Review sign-in logs: IPs, devices, user agents, MFA outcomes, conditional access results
- [ ] Review post-auth activity: mailbox rules, file access, downloads, role/permission changes, app consents, API key creation, VM/resource creation (cloud)
- [ ] Identify how credentials were obtained (phishing, reuse, infostealer, brute force, leaked)
- [ ] Check for lateral movement and other accounts using same IPs/devices
- [ ] Scope blast radius using the account's entitlements

## 6. Containment
- [ ] Disable or lock account; force sign-out and revoke all sessions, refresh tokens, and app passwords
- [ ] Reset password and MFA factors after verifying user identity
- [ ] Rotate API keys, SSH keys, service credentials the account could access
- [ ] Block attacker IPs/devices; tighten conditional access
- [ ] For cloud: disable unauthorized access keys, roles, and resources; snapshot before termination
- [ ] Isolate the user's endpoint if infostealer/malware suspected (PB-07)

## 7. Eradication
- [ ] Remove persistence: rogue MFA devices, inbox rules, OAuth apps, delegated access, new accounts, backdoor roles
- [ ] Remove malware from endpoints; reimage if infostealer
- [ ] For AD: check for Kerberoasting/DCSync/Golden ticket signs; escalate to ransomware/AD playbook as needed

## 8. Recovery
- [ ] Re-enable access with strong auth (phishing-resistant MFA preferred)
- [ ] Monitor account and related accounts for 30 days
- [ ] User guidance: password hygiene, reporting

## 9. Communications
- [ ] Inform user and manager; inform data owners if sensitive access occurred
- [ ] Trigger PB-03 if data accessed or exfiltrated

## 10. Evidence to Collect
Identity provider logs, cloud audit logs, endpoint logs, mailbox audit, token/session records, IOC list.

### 10.1 Closure Criteria & Metrics
- Account secured, persistence removed, root cause identified
- Metrics: dwell time, accounts affected, time to revoke

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
