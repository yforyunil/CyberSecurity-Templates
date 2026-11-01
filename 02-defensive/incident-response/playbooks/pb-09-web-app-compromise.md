# PB-09 Web Application Compromise Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-09 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to exploitation of web applications and APIs (injection, auth bypass, web shells, defacement, data theft).
**ATT&CK:** T1190 Exploit Public-Facing Application, T1505.003 Web Shell, T1059 Command Execution, T1213 Data Access.

## 2. Triggers / Detection
- [ ] WAF/IDS alerts for SQLi, RCE, path traversal, deserialization
- [ ] Unexpected files in web root; web shell indicators
- [ ] Web server spawning shells (cmd, powershell, bash, curl/wget)
- [ ] Defacement, unusual database queries, spike in 4xx/5xx or large responses
- [ ] Vulnerability disclosure or bug bounty report of active exploitation
- [ ] Newly published CVE affecting an exposed component

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Probing/blocked attempts only | SEV4 |
| Exploit succeeded, limited impact, no data access | SEV3 |
| Code execution or data access | SEV2 |
| Mass data theft, pivot to internal network, payment/auth systems | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| Application / DevOps Team | Code fix, redeploy, config |

## 5. Investigation
- [ ] Preserve web, application, WAF, database, and OS logs
- [ ] Identify exploited vulnerability, entry time, attacker IPs, payloads
- [ ] Search for web shells, modified files, new accounts, cron jobs, outbound connections
- [ ] Determine database/API data accessed and credentials exposed (app secrets, DB creds, tokens)
- [ ] Check pivoting to other hosts, cloud metadata service use, or internal systems
- [ ] Compare deployed code/artifacts with known-good repository version

## 6. Containment
- [ ] Block attacker IPs; add virtual patch/WAF rules for the exploit
- [ ] Take application offline or switch to maintenance page if active exploitation continues
- [ ] Snapshot server/container before changes
- [ ] Rotate DB credentials, API keys, session secrets, JWT signing keys, cloud keys
- [ ] Restrict egress from the web server

## 7. Eradication
- [ ] Patch/fix vulnerable code or dependency; add input validation/auth checks
- [ ] Remove web shells and unauthorized artifacts; redeploy from trusted build
- [ ] Rebuild host/containers from clean images
- [ ] Review similar code paths and sibling applications for the same flaw

## 8. Recovery
- [ ] Redeploy, run security regression tests, confirm fix with a retest
- [ ] Enhanced monitoring and WAF logging for 30 days
- [ ] Force password resets/session invalidation for users if credentials exposed

## 9. Communications
- [ ] Notify app owners and leadership; use PB-03 if data compromised
- [ ] Coordinate with researchers/bug bounty reporters; update security advisories if customer-facing

## 10. Evidence to Collect
Web/WAF/DB logs, file system snapshot, web shell samples, vulnerable code/commit, deployment records.

### 10.1 Closure Criteria & Metrics
- Vulnerability fixed and verified, no attacker access remains, secrets rotated
- Metrics: dwell time, records accessed, time to patch

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
