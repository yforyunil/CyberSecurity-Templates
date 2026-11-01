# Incident Response Playbooks (Outline)

| Field | Value |
|---|---|
| Document ID | IR-002 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Playbook Structure (applies to each)
1. Trigger / detection criteria
2. Severity guidance
3. Roles
4. Investigation steps
5. Containment
6. Eradication
7. Recovery
8. Communications / notifications
9. Evidence to collect
10. Closure criteria and metrics

## 2. Playbook Index
| ID | Playbook | Status |
|---|---|---|
| PB-01 | [Ransomware](playbooks/pb-01-ransomware.md) | Draft |
| PB-02 | [Phishing / Business Email Compromise](playbooks/pb-02-phishing-bec.md) | Draft |
| PB-03 | [Data breach / data leakage](playbooks/pb-03-data-breach.md) | Draft |
| PB-04 | [Insider threat](playbooks/pb-04-insider-threat.md) | Draft |
| PB-05 | [DDoS](playbooks/pb-05-ddos.md) | Draft |
| PB-06 | [Account / credential compromise](playbooks/pb-06-account-compromise.md) | Draft |
| PB-07 | [Malware outbreak](playbooks/pb-07-malware-outbreak.md) | Draft |
| PB-08 | [Lost / stolen device](playbooks/pb-08-lost-stolen-device.md) | Draft |
| PB-09 | [Web application compromise](playbooks/pb-09-web-app-compromise.md) | Draft |
| PB-10 | [Cloud account compromise](playbooks/pb-10-cloud-account-compromise.md) | Draft |
| PB-11 | [Third-party / supply chain compromise](playbooks/pb-11-supply-chain-compromise.md) | Draft |

Full playbooks live in the [`playbooks/`](playbooks/) folder. The sections below are the original summaries.

## PB-01 Ransomware
- **Trigger:** Encrypted files, ransom note, mass file modification alerts
- **Investigate:** Patient zero, variant identification, scope of encryption, exfiltration check (double extortion)
- **Contain:** Isolate hosts, disable affected accounts, block C2, segment network, protect backups
- **Eradicate:** Remove persistence, rebuild from clean images, reset credentials (including krbtgt if AD compromised)
- **Recover:** Restore from verified backups, staged reconnection, enhanced monitoring
- **Decisions:** Law enforcement, legal, insurer, ransom stance (executive/legal decision)
- **Evidence:** Memory/disk images, ransom note, logs, sample

## PB-02 Phishing / BEC
- **Trigger:** Reported email, suspicious forwarding rule, payment-change request
- **Investigate:** Email trace, recipients, clicks, mailbox rules, sign-in logs
- **Contain:** Purge email, block indicators, reset credentials, revoke sessions/tokens
- **Recover:** Remove malicious rules, verify finance transactions
- **Notify:** Finance/bank if payment fraud

## PB-03 Data Breach
- **Trigger:** Confirmed unauthorized access/exfiltration of sensitive data
- **Investigate:** Data types, volume, affected individuals, access path
- **Contain:** Close access path, revoke credentials
- **Notify:** Legal/privacy, regulators, individuals, partners
- **Document:** Timeline, decisions, notification evidence

## PB-04 Insider Threat
- Involve HR and Legal early; covert evidence preservation; access restriction timing; interview procedures.

## PB-05 DDoS
- Confirm attack type (volumetric / protocol / application), engage ISP/CDN/scrubbing, rate limiting, traffic filtering, communications to stakeholders.

## PB-06 Account Compromise
- Identify scope of access, force password reset and MFA re-enrollment, revoke tokens, review mailbox/cloud activity, hunt for persistence.

## PB-07 to PB-11
To be expanded using the structure in Section 1.

## 3. Revision History
