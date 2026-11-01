# PCI DSS v4.0.1 Mapping

| Field | Value |
|---|---|
| Document ID | MAP-004 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | PCI DSS v4.0.1 (only active version; all requirements mandatory since 31 March 2025) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Maps repository documents to PCI DSS v4.0.1 requirements for organizations that store, process, or transmit account data, or can affect the security of the cardholder data environment (CDE).

## 2. Notes
- PCI DSS v4.0.1 is the current and only active version; the future-dated v4.0 requirements became mandatory on 31 March 2025.
- The PCI Security Standards Council opened a request-for-comments period on the standard in mid-2026. Check pcisecuritystandards.org for any new version before relying on these requirement numbers.
- Applicability depends on your role (merchant or service provider), validation level, and scoping. Confirm with your QSA or acquirer.
- This repo is strongest on Req 7, 8, 12.10 (incident response), 6.5 (change management), and 11.4 (penetration testing).

**Coverage legend**
- **Covered**: a repo document addresses the requirement's intent (still needs tailoring and implementation evidence)
- **Partial**: a repo document addresses part of it, or only the response/recovery side
- **Gap**: no document in this repo yet; see [Gap Analysis](gap-analysis.md)

> Coverage reflects what the **draft documents in this repo** address, not whether controls are implemented or effective. This mapping is indicative, is not legal or audit advice, and should be validated with your compliance owner or auditor.

## 3. Requirement-Level Mapping (Req 1-12)
**Coverage summary (12 items):** Covered 2 | Partial 7 | Gap 3

| Req | Requirement | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 1 | Install and maintain network security controls | Gap | - | Network security standard needed |
| 2 | Apply secure configurations to all system components | Partial | [GOV-003](../01-governance/change-management-policy.md) | Config baselines via change control; hardening standards needed |
| 3 | Protect stored account data | Gap | - | Data retention and cryptography policies needed |
| 4 | Protect cardholder data with strong cryptography during transmission over open, public networks | Gap | - | Cryptography policy needed |
| 5 | Protect all systems and networks from malicious software | Partial | [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md) | Response only; anti-malware standard needed |
| 6 | Develop and maintain secure systems and software | Partial | [GOV-003](../01-governance/change-management-policy.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md) | 6.5 change management covered; secure SDLC and vulnerability management needed |
| 7 | Restrict access to system components and cardholder data by business need to know | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| 8 | Identify users and authenticate access to system components | Covered | [GOV-002](../01-governance/access-control-policy.md) | Password policy referenced but not yet written |
| 9 | Restrict physical access to cardholder data | Partial | [GOV-002](../01-governance/access-control-policy.md) | 9.4 media and 9.5 POI device controls not covered |
| 10 | Log and monitor all access to system components and cardholder data | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Logging standard needed (10.2 audit log content, 10.5 retention) |
| 11 | Test security of systems and networks regularly | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | 11.4 pentest covered; 11.3 scanning, 11.5 IDS/FIM, 11.6 payment-page monitoring not covered |
| 12 | Support information security with organizational policies and programs | Partial | [GOV-001](../01-governance/risk-register-template.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md), [TPL](../templates/document-template.md) | 12.10 incident response covered; 12.1 policy, 12.6 awareness, 12.8 TPSP gaps |

## 4. Sub-Requirement Mapping (selected)
**Coverage summary (24 items):** Covered 8 | Partial 9 | Gap 7

| Ref | Sub-requirement | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 2.2.1 | Configuration standards developed, implemented, maintained | Gap | - | Hardening baselines needed |
| 6.3.1 | Security vulnerabilities identified and managed | Gap | - | Vulnerability management procedure needed |
| 6.4.1/6.4.2 | Public-facing web applications protected (code review/testing, automated technical solution such as WAF) | Partial | [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md) | Response only |
| 6.5.1 | Changes to system components follow documented procedures (reason, impact, approval, testing, back-out) | Covered | [GOV-003](../01-governance/change-management-policy.md) |  |
| 6.5.2 | Upon significant change, applicable PCI DSS requirements confirmed in place | Gap | - | Add PCI re-validation step to change process if in scope |
| 7.2.1-7.2.5 | Access control model defined; appropriate access assigned; access reviewed | Covered | [GOV-002](../01-governance/access-control-policy.md) | Includes 7.2.4 six-month account review |
| 8.2.x | User ID management (unique IDs, lifecycle, inactive accounts) | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| 8.4.x | MFA for CDE access and remote access | Covered | [GOV-002](../01-governance/access-control-policy.md) | Verify MFA scope matches PCI 8.4.1-8.4.3 |
| 8.6.x | System and application account management | Partial | [GOV-002](../01-governance/access-control-policy.md) | Service accounts mentioned; interactive-use and password controls need detail |
| 10.4.1 | Audit logs reviewed at least once daily (or via automated mechanisms) | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) | SOC triage; document review cadence |
| 10.7.x | Failures of critical security control systems detected, alerted, and addressed | Gap | - |  |
| 11.4.1 | Penetration testing methodology defined, documented, and implemented | Covered | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-004](../03-offensive/pentest-report-template.md) | Methodology and scope |
| 11.4.2/11.4.3 | Internal and external penetration testing performed at least every 12 months and after significant change | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Schedule must be set by the organization |
| 11.4.4 | Exploitable vulnerabilities found during testing are corrected and retested | Partial | [OFF-004](../03-offensive/pentest-report-template.md) | Retest section in report template |
| 11.4.5 | Segmentation controls tested (if segmentation used) | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md) | Add explicit segmentation test to SoW when in scope |
| 12.3.1 | Targeted risk analysis for requirements with flexible frequency | Partial | [GOV-001](../01-governance/risk-register-template.md) |  |
| 12.8.x | Risk to information assets associated with third-party service providers managed | Gap | - | TPSP management and responsibility matrix needed |
| 12.10.1 | Incident response plan exists and is ready to be activated | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md) | Includes roles, communications, containment, business recovery |
| 12.10.2 | IR plan reviewed and tested at least every 12 months | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md) | Testing section; keep exercise evidence |
| 12.10.3 | Specific personnel designated to be available 24/7 for incidents | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md) | Add on-call roster |
| 12.10.4 | Personnel responsible for incident response are trained | Gap | - | Training records needed |
| 12.10.5 | IR plan includes monitoring and responding to alerts from security monitoring systems | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md) |  |
| 12.10.6 | IR plan is modified and evolved according to lessons learned and industry developments | Covered | [IR-004](../02-defensive/incident-response/post-incident-review-template.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md) |  |
| 12.10.7 | Incident response procedures upon detection of stored PAN anywhere it is not expected | Gap | - | Add a PAN discovery playbook if in scope |

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
