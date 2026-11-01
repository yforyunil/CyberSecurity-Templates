# HIPAA Mapping

| Field | Value |
|---|---|
| Document ID | MAP-006 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | HIPAA Security Rule (45 CFR 164 Subpart C) and Breach Notification Rule (Subpart D), as currently in force |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Maps repository documents to the HIPAA Security Rule safeguards and the Breach Notification Rule for covered entities and business associates handling ePHI.

## 2. Important Note: Pending Security Rule Overhaul (not in force)
HHS proposed a significant update to the Security Rule in an NPRM (announced late December 2024, published January 2025). Final action was originally targeted for May 2026; the regulatory agenda now lists **July 2027** and the rulemaking has moved to "long-term actions." **The existing Security Rule remains in force and enforceable.** This mapping uses the current rule. If a final rule is published, re-map, particularly for encryption, MFA, asset inventory, network segmentation, and recovery timelines that the proposal would make mandatory.

## 3. Notes
- **(R)** = required, **(A)** = addressable. Addressable does not mean optional: implement, or document why not and what equivalent measure is used.
- The Privacy Rule is out of scope for this mapping.
- Penalty amounts and enforcement priorities change; consult HHS OCR guidance.

**Coverage legend**
- **Covered**: a repo document addresses the requirement's intent (still needs tailoring and implementation evidence)
- **Partial**: a repo document addresses part of it, or only the response/recovery side
- **Gap**: no document in this repo yet; see [Gap Analysis](gap-analysis.md)

> Coverage reflects what the **draft documents in this repo** address, not whether controls are implemented or effective. This mapping is indicative, is not legal or audit advice, and should be validated with your compliance owner or auditor.

## 4. Security Rule
**Coverage summary (25 items):** Covered 7 | Partial 13 | Gap 5

| Citation | Standard / Implementation Specification | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 164.308(a)(1)(ii)(A) | Risk analysis (R) | Partial | [GOV-001](../01-governance/risk-register-template.md) | Register and scoring; needs an asset-level ePHI risk analysis |
| 164.308(a)(1)(ii)(B) | Risk management (R) | Partial | [GOV-001](../01-governance/risk-register-template.md) | Treatment tracking |
| 164.308(a)(1)(ii)(C) | Sanction policy (R) | Partial | [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md) | HR-led; dedicated sanction policy needed |
| 164.308(a)(1)(ii)(D) | Information system activity review (R) | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Log review practices |
| 164.308(a)(2) | Assigned security responsibility (R) | Partial | [IR-001](../02-defensive/incident-response/incident-response-plan.md) | Name a Security Official |
| 164.308(a)(3) | Workforce security: authorization/supervision (A), clearance (A), termination (A) | Covered | [GOV-002](../01-governance/access-control-policy.md) | Joiner/mover/leaver |
| 164.308(a)(4) | Information access management: access authorization (A), establishment and modification (A) | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| 164.308(a)(5) | Security awareness and training: reminders, malware protection, log-in monitoring, password management (A) | Gap | - | Awareness program needed |
| 164.308(a)(6) | Security incident procedures: response and reporting (R) | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-002](../02-defensive/incident-response/incident-response-playbooks-outline.md), [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-005](../02-defensive/incident-response/chain-of-custody-form.md), [IR-PB-01](../02-defensive/incident-response/playbooks/pb-01-ransomware.md), [IR-PB-02](../02-defensive/incident-response/playbooks/pb-02-phishing-bec.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [IR-PB-04](../02-defensive/incident-response/playbooks/pb-04-insider-threat.md), [IR-PB-05](../02-defensive/incident-response/playbooks/pb-05-ddos.md), [IR-PB-06](../02-defensive/incident-response/playbooks/pb-06-account-compromise.md), [IR-PB-07](../02-defensive/incident-response/playbooks/pb-07-malware-outbreak.md), [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-PB-09](../02-defensive/incident-response/playbooks/pb-09-web-app-compromise.md), [IR-PB-10](../02-defensive/incident-response/playbooks/pb-10-cloud-account-compromise.md), [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) |  |
| 164.308(a)(7)(ii)(A) | Data backup plan (R) | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Backup management section |
| 164.308(a)(7)(ii)(B) | Disaster recovery plan (R) | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) |  |
| 164.308(a)(7)(ii)(C) | Emergency mode operation plan (R) | Covered | [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) |  |
| 164.308(a)(7)(ii)(D) | Testing and revision procedures (A) | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) |  |
| 164.308(a)(7)(ii)(E) | Applications and data criticality analysis (A) | Partial | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) | Tiering and BIA summary |
| 164.308(a)(8) | Evaluation (R) | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md) | Technical evaluation via pentest; periodic non-technical evaluation needed |
| 164.308(b) | Business associate contracts and other arrangements (R) | Gap | - | BAA template and vendor policy needed |
| 164.310(a) | Facility access controls | Partial | [GOV-002](../01-governance/access-control-policy.md) | Physical access section only |
| 164.310(b)-(c) | Workstation use and workstation security (R) | Gap | - | Endpoint standard needed |
| 164.310(d)(1) | Device and media controls: disposal (R), re-use (R), accountability (A), backup and storage (A) | Partial | [IR-PB-08](../02-defensive/incident-response/playbooks/pb-08-lost-stolen-device.md), [IR-005](../02-defensive/incident-response/chain-of-custody-form.md) | Lost device and evidence media only |
| 164.312(a)(1) | Access control: unique user ID (R), emergency access procedure (R), automatic logoff (A), encryption/decryption (A) | Partial | [GOV-002](../01-governance/access-control-policy.md) | Encryption not addressed |
| 164.312(b) | Audit controls (R) | Partial | [DEF-001](../02-defensive/detection-and-monitoring/alert-triage-runbooks.md), [DEF-002](../02-defensive/detection-and-monitoring/threat-hunting-playbook.md) | Logging standard needed |
| 164.312(c) | Integrity of ePHI | Gap | - |  |
| 164.312(d) | Person or entity authentication (R) | Covered | [GOV-002](../01-governance/access-control-policy.md) |  |
| 164.312(e) | Transmission security: integrity controls (A), encryption (A) | Gap | - | Cryptography policy needed |
| 164.316(a)-(b) | Policies and procedures; documentation, retention (6 years), availability, updates | Partial | [TPL](../templates/document-template.md) | Versioned templates; define retention |

## 5. Breach Notification Rule
**Coverage summary (5 items):** Covered 0 | Partial 4 | Gap 1

| Citation | Requirement | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| 164.404 | Notification to individuals (without unreasonable delay, no later than 60 days after discovery) | Partial | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Legal-led; templates needed |
| 164.406 | Notification to the media (breaches affecting more than 500 residents of a state or jurisdiction) | Partial | [BC-003](../02-defensive/business-continuity/crisis-management-plan.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) |  |
| 164.408 | Notification to the HHS Secretary | Partial | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Contemporaneous for 500+; annual log for fewer than 500 |
| 164.410 | Business associate notification to the covered entity | Gap | - | Include in BAA |
| 164.414 | Burden of proof; documentation of risk assessment | Partial | [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Four-factor risk assessment and decision records |

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
