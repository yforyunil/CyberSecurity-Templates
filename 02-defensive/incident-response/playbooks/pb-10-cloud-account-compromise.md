# PB-10 Cloud Account Compromise Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-10 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond to compromise of cloud tenants/accounts (AWS, Azure, GCP, SaaS) including leaked keys, abused roles, cryptomining, and data theft.
**ATT&CK:** T1078.004 Cloud Accounts, T1537 Transfer Data to Cloud Account, T1496 Resource Hijacking, T1098 Account Manipulation, T1530 Data from Cloud Storage.

## 2. Triggers / Detection
- [ ] Cloud provider abuse/security notice or unexpected billing spike
- [ ] GuardDuty/Defender/Security Command Center findings
- [ ] Access keys exposed in public repo or paste site
- [ ] Unusual API calls (CreateUser, AttachPolicy, disabling logging, ListBuckets)
- [ ] New resources in unusual regions; new federated identities/apps
- [ ] Root/global admin sign-in

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Exposed key, no use observed, revoked | SEV4 |
| Limited misuse (e.g., cryptomining) | SEV3 |
| Privilege escalation or data access | SEV2 |
| Root/global admin compromise, mass data loss, logging disabled | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| Cloud / Platform Team | Tenant-level actions |

## 5. Investigation
- [ ] Ensure audit logging (CloudTrail/Activity Log/Audit Logs) is intact; export copies to a separate account
- [ ] Identify compromised principal(s), key IDs, source IPs, first and last activity
- [ ] Enumerate all actions by the principal: IAM changes, resource creation, storage access, snapshots shared, logging changes
- [ ] Check for persistence: new users/keys, roles with trust to external accounts, Lambda/functions, federated IdPs, app registrations
- [ ] Assess data accessed/exfiltrated (bucket access logs, data events, cross-account copies)
- [ ] Identify root cause (leaked secret, phishing, misconfigured role, vulnerable workload with metadata access)

## 6. Containment
- [ ] Deactivate/rotate compromised keys; revoke sessions; disable users
- [ ] Apply deny-all or restrictive policy to compromised principal (service control policy / permission boundary)
- [ ] Remove attacker-created identities, roles, trust relationships, and resources (snapshot first for evidence)
- [ ] Block attacker IPs where supported; enforce MFA and conditional access
- [ ] Re-enable and protect logging; enable guardrails
- [ ] Rotate secrets stored in affected accounts (secrets manager, parameter stores)

## 7. Eradication
- [ ] Remove all persistence mechanisms and unauthorized resources across all regions
- [ ] Fix root cause; remove hard-coded secrets; adopt short-lived credentials/workload identity
- [ ] Review IAM for over-permissive policies and public exposure

## 8. Recovery
- [ ] Validate resource inventory against baseline (IaC state)
- [ ] Re-deploy affected workloads from trusted pipelines
- [ ] Monitor with enhanced detections; reconcile billing and engage provider for credit if abuse

## 9. Communications
- [ ] Open provider support case; notify account owners
- [ ] Use PB-03 if data accessed; Legal assessment for obligations

## 10. Evidence to Collect
Audit logs, IAM snapshots, resource inventory, snapshots/images of affected instances, billing records, key exposure source.

### 10.1 Closure Criteria & Metrics
- Attacker access removed, logging verified, root cause fixed
- Metrics: dwell time, resources created by attacker, cost impact, data accessed

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
