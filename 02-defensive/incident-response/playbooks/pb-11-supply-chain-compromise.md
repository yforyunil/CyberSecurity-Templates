# PB-11 Third-Party / Supply Chain Compromise Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-11 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Respond when a vendor, software dependency, managed service provider, or build pipeline is compromised and may affect our environment or data.
**ATT&CK:** T1195 Supply Chain Compromise, T1199 Trusted Relationship, T1078 Valid Accounts.

## 2. Triggers / Detection
- [ ] Vendor breach notification or public disclosure
- [ ] Security advisory on a library, package, plugin, or appliance we use
- [ ] Malicious package version or typosquat found in dependency tree
- [ ] Unexpected activity from vendor accounts or remote access tools
- [ ] Compromised software update/signed binary reported
- [ ] Anomalies in CI/CD (unauthorized pipeline changes, leaked build secrets)

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Vendor breach, we are not affected | SEV4 |
| Vendor holds our non-sensitive data | SEV3 |
| Vendor holds sensitive data or has privileged access to us | SEV2 |
| Compromised software deployed in our environment or build pipeline | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| Vendor Management / Procurement | Vendor contact, contracts |
| Engineering / DevSecOps | Dependency and pipeline analysis |

## 5. Investigation
- [ ] Identify the vendor/component, version, and how we use it (inventory, SBOM, CMDB)
- [ ] Determine exposure: data shared, network access, credentials, integrations, deployed versions
- [ ] Obtain vendor IOCs, timeline, and advisories; request a point of contact
- [ ] Hunt for IOCs and anomalous activity involving vendor accounts, connections, or updates
- [ ] For software: verify hashes/signatures, check build logs and artifact provenance
- [ ] Determine whether malicious code executed or data was accessed

## 6. Containment
- [ ] Suspend or restrict vendor access (VPN, API keys, admin tools, shared accounts)
- [ ] Rotate credentials and secrets shared with or accessible to the vendor
- [ ] Block vendor-related malicious indicators
- [ ] Pin/rollback to known-good versions; freeze updates and pipeline deployments
- [ ] Isolate systems running compromised software
- [ ] Pause data feeds/integrations as needed

## 7. Eradication
- [ ] Remove or replace compromised components; rebuild from verified sources
- [ ] Rebuild affected build agents; rotate signing keys and pipeline secrets
- [ ] Apply vendor patches only after validation

## 8. Recovery
- [ ] Restore integrations with minimum necessary permissions
- [ ] Validate integrity of artifacts; resume pipelines after review
- [ ] Heightened monitoring of vendor connections

## 9. Communications & Contractual Actions
- [ ] Track vendor's notification obligations and SLAs; require updates in writing
- [ ] Notify internal stakeholders, customers, and regulators if our data or customers are affected (see PB-03)
- [ ] Review contract rights (audit, termination, liability); coordinate with Legal and Vendor Management
- [ ] Share relevant IOCs with trusted communities (TLP)

## 10. Evidence to Collect
Vendor notices, version/SBOM inventory, integrity hashes, access logs for vendor accounts, pipeline logs, communications with vendor.

### 10.1 Closure Criteria & Metrics
- Exposure assessed and remediated, vendor access reviewed, contract/risk actions recorded
- Metrics: time to identify exposure, systems affected, time to rotate credentials

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
