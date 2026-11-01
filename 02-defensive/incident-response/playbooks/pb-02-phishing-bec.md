# PB-02 Phishing and Business Email Compromise Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-02 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to malicious emails (credential harvesting, malware delivery) and business email compromise (account takeover, payment fraud, impersonation).
**ATT&CK:** T1566 Phishing, T1534 Internal Spearphishing, T1114 Email Collection, T1078 Valid Accounts, T1098 Account Manipulation.

## 2. Triggers / Detection
- [ ] User-reported suspicious email
- [ ] Email gateway/EDR alert on malicious attachment or URL
- [ ] Impossible-travel or anomalous sign-in following a click
- [ ] New inbox forwarding/redirect rules; OAuth app consent grants
- [ ] Finance reports changed payment/bank details request; CEO-fraud style request

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Email delivered, no interaction | SEV4 |
| Clicked link or opened attachment, no compromise confirmed | SEV3 |
| Credentials entered or malware executed | SEV2 |
| Executive/finance account compromised or fraudulent payment made | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |

## 5. Investigation
- [ ] Obtain original message with full headers; analyze sender, SPF/DKIM/DMARC, reply-to, lookalike domain
- [ ] Analyze URLs/attachments in sandbox; record IOCs
- [ ] Search mail logs for all recipients, delivery status, and clicks (URL rewrite/proxy logs)
- [ ] For clickers: review sign-in logs, MFA events, new devices, token issuance
- [ ] For suspected account takeover: review mailbox rules, delegates, forwarding, sent items, OAuth apps, audit log
- [ ] For BEC: identify any payment instructions, invoices, or data requests acted on

## 6. Containment
- [ ] Purge/quarantine message from all mailboxes
- [ ] Block sender, domain, URLs, and IPs at gateway, proxy, and DNS
- [ ] Reset passwords and revoke sessions/refresh tokens for affected users; re-enroll MFA
- [ ] Remove malicious inbox rules, forwarding, delegates, and rogue OAuth apps
- [ ] Isolate endpoint if payload executed (switch to PB-07 Malware)
- [ ] Contact finance/bank immediately to attempt payment recall if fraud involved

## 7. Eradication
- [ ] Confirm no persistence (rules, apps, devices, tokens)
- [ ] Hunt for same campaign across tenant (sender, subject, URL patterns)
- [ ] Tighten controls: impersonation protection, external sender banners, conditional access

## 8. Recovery
- [ ] Restore user access with verified identity
- [ ] Monitor affected accounts for 30 days
- [ ] Confirm no further fraudulent transactions

## 9. Communications & Notifications
- [ ] Warn staff of active campaign (short, actionable alert)
- [ ] Notify partners/customers if their data or accounts were targeted from our compromised account
- [ ] Notify bank/law enforcement for payment fraud; involve Legal for data exposure obligations
- [ ] Feedback to reporting user

## 10. Evidence to Collect
Original .eml/.msg with headers, URL/attachment samples, mail trace, sign-in and audit logs, mailbox rule exports, payment records.

### 10.1 Closure Criteria & Metrics
- Message removed, indicators blocked, accounts secured, no further malicious activity
- Metrics: time to report, time to purge, number of recipients/clickers/compromised accounts, financial loss

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
