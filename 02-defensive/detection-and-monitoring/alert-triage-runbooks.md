# Alert Triage Runbooks

| Field | Value |
|---|---|
| Document ID | DEF-001 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Standard steps for SOC analysts to triage, enrich, and disposition alerts.

## 2. General Triage Workflow
1. Acknowledge alert and record timestamp
2. Validate: true positive / false positive / benign true positive / needs more data
3. Enrich: asset criticality, user, IP/domain reputation, threat intel, recent activity
4. Scope: other affected hosts/users, related alerts
5. Decide: close, escalate, or contain
6. Document findings and tune detection if needed

## 3. Severity & SLA
| Severity | Criteria | Triage SLA | Escalation |
|---|---|---|---|
| Critical | Confirmed compromise, critical asset | 15 min | IR lead immediately |
| High | Likely malicious, sensitive asset | 30 min | Tier 2 |
| Medium | Suspicious, unconfirmed | 4 h | Tier 2 if confirmed |
| Low | Informational | 24 h | None |

## 4. Runbook Template (copy per alert type)
- **Alert name / detection ID:**
- **Data sources:**
- **Description & MITRE ATT&CK mapping:**
- **Triage questions:**
- **Investigation queries (SIEM/EDR):**
- **True positive indicators:**
- **False positive indicators:**
- **Containment actions:**
- **Escalation criteria / contacts:**
- **Closure notes required:**

## 5. Runbook Index (to be written)
| ID | Alert Type | ATT&CK | Status |
|---|---|---|---|
| RB-01 | Phishing email reported | T1566 | Outline |
| RB-02 | Suspicious login / impossible travel | T1078 | Outline |
| RB-03 | Multiple failed logins / brute force | T1110 | Outline |
| RB-04 | Malware detected by EDR | T1204 | Outline |
| RB-05 | Suspicious PowerShell / script execution | T1059 | Outline |
| RB-06 | Privilege escalation / new admin account | T1098 | Outline |
| RB-07 | Data exfiltration / large outbound transfer | T1041 | Outline |
| RB-08 | C2 beaconing / DNS anomalies | T1071 | Outline |
| RB-09 | Lateral movement (RDP/SMB/WinRM) | T1021 | Outline |
| RB-10 | Cloud IAM anomaly | T1078.004 | Outline |
| RB-11 | Web attack (SQLi/XSS/WAF) | T1190 | Outline |
| RB-12 | Ransomware indicators | T1486 | Outline |

## 6. Example: RB-01 Phishing Email Reported
1. Retrieve original email (headers, body, attachments, URLs)
2. Check sender, SPF/DKIM/DMARC results, reply-to mismatch
3. Detonate/scan attachments and URLs in sandbox
4. Search mail logs for other recipients; check who clicked/opened
5. If malicious: purge from mailboxes, block sender/domain/URL, reset credentials of clickers, isolate host if payload executed
6. Escalate to IR plan if credentials or malware confirmed
7. Notify reporter and close

## 7. Revision History
