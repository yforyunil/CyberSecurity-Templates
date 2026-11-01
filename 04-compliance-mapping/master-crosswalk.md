# Master Crosswalk: Repo Documents to Frameworks

| Field | Value |
|---|---|
| Document ID | MAP-000 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | ISO 27001:2022, NIST CSF 2.0, SOC 2 TSC, PCI DSS v4.0.1, GDPR, HIPAA |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
One-page view of which framework requirements each repository document supports. Use it to answer "what does this document help us prove?" during audits and readiness reviews.

## 2. Crosswalk
| ID | Document | ISO 27001:2022 | NIST CSF 2.0 | SOC 2 | PCI DSS 4.0.1 | GDPR | HIPAA |
|---|---|---|---|---|---|---|---|
| [GOV-001](../01-governance/risk-register-template.md) | Risk Register Template | 6.1.2, 6.1.3, 8.2 | GV.RM, ID.RA | CC3.2, CC3.4, CC9.1 | 12.3.1 | Art. 24 | 164.308(a)(1)(ii)(A)-(B) |
| [GOV-002](../01-governance/access-control-policy.md) | Access Control Policy | 5.15-5.18, 8.2, 8.3, 8.5 | PR.AA | CC6.1-CC6.3 | Req 7, Req 8 | Art. 32(1)(b) | 164.308(a)(3)-(4), 164.312(a), (d) |
| [GOV-003](../01-governance/change-management-policy.md) | Change Management Policy | 8.32, 8.9 | PR.PS-01, ID.RA-07 | CC8.1, CC3.4 | 6.5.1-6.5.6 | Art. 32(1)(b) | 164.308(a)(1) |
| [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) | Alert Triage Runbooks | 5.24-5.25, 8.15, 8.16, 5.37 | DE.CM, DE.AE, RS.MA-02 | CC7.2, CC7.3 | 10.4, 12.10.5 | Art. 32(1)(d) | 164.308(a)(1)(ii)(D), 164.312(b) |
| [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Threat Hunting Playbook | 5.7, 8.16 | DE.AE, ID.RA-03 | CC7.1, CC7.2 | 10.4, 11.5 | Art. 32(1)(d) | 164.308(a)(1)(ii)(D) |
| [IR-001](../02-defensive/incident-response/incident-response-plan.md) | Incident Response Plan | 5.24-5.28, 6.8 | RS.MA, RS.AN, RS.CO, RS.MI, ID.IM-04 | CC7.3, CC7.4, CC2.3 | 12.10.1-12.10.6 | Art. 33, Art. 34 | 164.308(a)(6), 164.404-408 |
| [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md) | IR Playbooks (outline and 11 playbooks) | 5.26, 5.37, 8.7, 5.23, 5.21 | RS.MA, RS.MI, RC.RP | CC7.4, CC7.5 | 12.10.1, 12.10.5 | Art. 33, Art. 34 | 164.308(a)(6) |
| [IR-003](../02-defensive/incident-response/incident-report-template.md) | Incident Report Template | 5.25-5.27, 5.28 | RS.AN-03, RS.AN-08, RC.RP-06 | CC7.4, CC7.5 | 12.10.1 | Art. 33(3), 33(5) | 164.308(a)(6), 164.414 |
| [IR-004](../02-defensive/incident-response/post-incident-review-template.md) | Post-Incident Review Template | 5.27 | ID.IM-03, RC.RP-06 | CC7.5, CC4.2 | 12.10.6 | Art. 33(5) | 164.308(a)(6) |
| [IR-005](../02-defensive/incident-response/chain-of-custody-form.md) | Chain of Custody Form | 5.28 | RS.AN-06, RS.AN-07 | CC7.4 | 12.10.1 | Art. 33(5) | 164.308(a)(6) |
| [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Disaster Recovery Plan | 5.29, 5.30, 8.13, 8.14 | PR.DS-11, PR.IR, RC.RP | CC9.1, A1.2, A1.3 | 12.10.1 (business recovery) | Art. 32(1)(c) | 164.308(a)(7)(ii)(A)-(E) |
| [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) | Business Continuity Plan | 5.29, 5.30 | GV.OC, RC.RP | CC9.1, A1.3 | 12.10.1 | Art. 32(1)(b)-(c) | 164.308(a)(7)(ii)(C), (E) |
| [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Crisis Management Plan | 5.5, 5.29 | RS.CO, RC.CO | CC2.3 | 12.10.1 (communications) | Art. 33, Art. 34 | 164.404-164.408 |
| [OFF-001](../03-offensive/rules-of-engagement.md) | Rules of Engagement | 5.35, 8.34 | ID.RA-01, ID.IM-02 | CC4.1, CC7.1 | 11.4.1-11.4.5 | Art. 32(1)(d) | 164.308(a)(8) |
| [OFF-002](../03-offensive/statement-of-work.md) | Statement of Work (pentest) | 5.35, 6.6 | ID.RA-01, ID.IM-02 | CC4.1 | 11.4.1 | Art. 32(1)(d) | 164.308(a)(8) |
| [OFF-003](../03-offensive/scope-and-authorization-letter.md) | Scope and Authorization Letter | 5.35 | ID.RA-01 | CC4.1 | 11.4.1 | Art. 32(1)(d) | 164.308(a)(8) |
| [OFF-004](../03-offensive/pentest-report-template.md) | Pentest Report Template | 5.35, 8.8 | ID.RA-01, ID.IM-02 | CC4.1, CC4.2 | 11.4.1, 11.4.4 | Art. 32(1)(d) | 164.308(a)(8) |
| [TPL](../templates/document-template.md) | Document Template | 7.5 (clause), 5.37 | GV.PO | CC5.3 | 12.1 | Art. 5(2) | 164.316(b) |

## 3. Detailed Framework Mappings
- [ISO/IEC 27001:2022](iso-27001-2022-mapping.md)
- [NIST CSF 2.0](nist-csf-2.0-mapping.md)
- [SOC 2](soc2-mapping.md)
- [PCI DSS v4.0.1](pci-dss-4.0.1-mapping.md)
- [GDPR](gdpr-mapping.md)
- [HIPAA](hipaa-mapping.md)
- [Gap Analysis](gap-analysis.md)

## 4. Maintenance
When you add or change a document, update this table and the affected framework files in the same pull request.

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
