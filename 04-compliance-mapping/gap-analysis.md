# Compliance Gap Analysis and Recommended Next Documents

| Field | Value |
|---|---|
| Document ID | MAP-007 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | Cross-framework |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Lists documents that would close the most coverage gaps across the six mapped frameworks, in suggested priority order.

## 2. Coverage Snapshot
| Framework (scope counted) | Covered | Partial | Gap |
|---|---|---|---|
| ISO 27001:2022 Annex A | 17 | 29 | 47 |
| NIST CSF 2.0 categories | 10 | 9 | 3 |
| SOC 2 Common Criteria | 12 | 15 | 6 |
| PCI DSS v4.0.1 requirements | 2 | 7 | 3 |
| GDPR articles | 4 | 8 | 8 |
| HIPAA Security Rule items | 7 | 13 | 5 |

Snapshot is generated from the mapping tables; counts change as documents are added.

## 3. Recommended Next Documents
| Priority | Document | Frameworks / Controls Addressed | Why |
|---|---|---|---|
| High | Information Security Policy | ISO 5.1; CSF GV.PO; SOC 2 CC5.3; PCI 12.1; HIPAA 164.316 | Anchors every other policy |
| High | Acceptable Use Policy | ISO 5.10; SOC 2 CC1.1, CC5.3; PCI 12.7 / 12.1.x | Needed for workforce accountability |
| High | Password / Authentication Policy | ISO 5.17; CSF PR.AA; PCI 8.3; HIPAA 164.308(a)(5)(ii)(D) | Already referenced by the Access Control Policy |
| High | Data Classification & Handling Policy | ISO 5.12-5.14; SOC 2 C1.1; GDPR Art. 5; PCI 3.x | Drives encryption and retention rules |
| High | Data Retention & Disposal Policy | ISO 8.10, 7.14; SOC 2 CC6.5, C1.2; GDPR Art. 5(1)(e); PCI 3.2 | Needed for privacy and PCI storage limits |
| High | Cryptography & Key Management Policy | ISO 8.24; GDPR Art. 32(1)(a); PCI 3, 4; HIPAA 164.312(a)(2)(iv), (e) | Encryption gaps appear in most frameworks |
| High | Patch & Vulnerability Management Procedure | ISO 8.8; CSF ID.RA-01; SOC 2 CC7.1; PCI 6.3, 11.3 | Pentests alone do not satisfy this |
| High | Logging & Monitoring Standard | ISO 8.15; CSF PR.PS-04; PCI 10; HIPAA 164.312(b) | Underpins detection and forensics |
| High | Third-Party / Vendor Risk Management Policy | ISO 5.19-5.22; CSF GV.SC; SOC 2 CC9.2; PCI 12.8; GDPR Art. 28; HIPAA 164.308(b) | Includes DPA / BAA templates |
| High | Security Awareness & Training Plan | ISO 6.3; CSF PR.AT; SOC 2 CC1.4; PCI 12.6; HIPAA 164.308(a)(5) | Training records are common audit evidence |
| Medium | Business Impact Analysis (BIA) | ISO 5.30; SOC 2 CC9.1; HIPAA 164.308(a)(7)(ii)(E) | Feeds RTO/RPO targets in DRP/BCP |
| Medium | Risk Assessment Methodology | ISO 6.1.2; CSF GV.RM; HIPAA 164.308(a)(1)(ii)(A) | Pairs with the risk register |
| Medium | Statement of Applicability (ISO 27001) | ISO 6.1.3 | Only if pursuing ISO certification |
| Medium | Asset Inventory Standard | ISO 5.9; CSF ID.AM | Foundation for scoping and risk analysis |
| Medium | Secure Network Architecture / Network Security Standard | ISO 8.20-8.22; PCI 1; SOC 2 CC6.6 | Segmentation and boundary controls |
| Medium | Server / Endpoint Hardening Baselines | ISO 8.9; PCI 2.2; CSF PR.PS-01 | Config standards |
| Medium | Security Metrics & KPI Guide; Internal Audit and Management Review | ISO 9.1-9.3; CSF GV.OV | Required for ISO; useful for SOC 2 |
| Medium | Privacy: RoPA, DPIA, DSAR procedure | GDPR Art. 12-23, 30, 35 | Needed if processing EU personal data |
| Medium | Secure SDLC Policy | ISO 8.25-8.29; PCI 6.2; GDPR Art. 25 | For organizations developing software |
| Low | Threat Intelligence Program Plan | ISO 5.7; CSF ID.RA-02 | Supports hunting and triage |
| Low | Secure Disposal / Physical Security Standard | ISO 7.x; PCI 9; HIPAA 164.310 | Depends on on-prem footprint |
| Conditional | PAN Discovery Playbook | PCI 12.10.7 | Only if cardholder data is in scope |
| Conditional | BAA Template | HIPAA 164.308(b), 164.410 | Only if handling ePHI |

## 4. Reading the Gaps
- **Strengths:** incident response, detection and triage, business continuity, access control, change management, penetration test engagement documents.
- **Weakest areas:** data protection (classification, retention, encryption), vendor management, awareness training, asset and vulnerability management, privacy program documents, and governance oversight (metrics, audit, management review).
- Documents alone are not compliance: auditors also need **implementation evidence** (tickets, logs, access reviews, test results, training records, exercise reports).

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
