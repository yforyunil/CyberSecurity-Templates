# Threat Hunting Playbook

| Field | Value |
|---|---|
| Document ID | DEF-002 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
## 2. Scope & Objectives
## 3. Hunting Maturity Model (HMM0-HMM4) - current target level
## 4. Hunt Types
- Hypothesis-driven (ATT&CK / threat intel based)
- IOC/IOA sweeps
- Baseline / anomaly (statistical)
- Situational (new vulnerability, advisory)

## 5. Hunt Process
1. Trigger / hypothesis creation
2. Data and tooling readiness check
3. Query development and execution
4. Analysis and pivoting
5. Findings: confirm, escalate to IR, or close
6. Detection engineering handoff (new rules)
7. Documentation and metrics

## 6. Hunt Plan Template
| Field | Value |
|---|---|
| Hunt ID | |
| Hypothesis | |
| ATT&CK Technique(s) | |
| Data Sources | |
| Tools | |
| Queries | |
| Time Range | |
| Expected Benign Activity | |
| Findings | |
| Outcome / Actions | |

## 7. Hypothesis Library (outline)
| ID | Hypothesis | ATT&CK |
|---|---|---|
| H-01 | Adversaries use scheduled tasks for persistence | T1053 |
| H-02 | Credential dumping from LSASS | T1003 |
| H-03 | Living-off-the-land binaries used for execution | T1218 |
| H-04 | Unusual service account interactive logins | T1078 |
| H-05 | DNS tunneling / beaconing | T1071.004 |
| H-06 | Rogue cloud API keys / OAuth apps | T1528 |
| H-07 | Lateral movement via admin shares | T1021.002 |

## 8. Metrics
Hunts per quarter, detections created, incidents found, ATT&CK coverage gain, mean time to hunt.

## 9. Required Data Sources
Endpoint telemetry, DNS, proxy, firewall/NetFlow, authentication, cloud audit logs.

## 10. Roles & Responsibilities
## 11. Revision History
