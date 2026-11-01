# GDPR Mapping

| Field | Value |
|---|---|
| Document ID | MAP-005 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Framework / Version | Regulation (EU) 2016/679 (GDPR) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose
Maps repository documents to GDPR obligations that are relevant to security and incident management, and shows where privacy documents are still needed.

## 2. Important Note: Proposed Breach Deadline Change (not in force)
The European Commission's Digital Omnibus proposal (19 November 2025) would extend the Art. 33 supervisory-authority deadline from 72 to 96 hours, raise the threshold to high-risk breaches, and add a single-entry reporting point. As of the latest status checked (October 2026), the proposal had not been adopted. **Keep 72-hour procedures in place until legislation is in force.** The EDPB has also been consulting on a common breach notification template. Re-check status before relying on either.

## 3. Other Notes
- GDPR is principle-based; Art. 32 requires "appropriate" measures based on risk. Mapping shows where documents support those measures.
- Member-state laws, the NIS2 Directive, and sector rules may add separate reporting duties; coordinate them with Legal.

**Coverage legend**
- **Covered**: a repo document addresses the requirement's intent (still needs tailoring and implementation evidence)
- **Partial**: a repo document addresses part of it, or only the response/recovery side
- **Gap**: no document in this repo yet; see [Gap Analysis](gap-analysis.md)

> Coverage reflects what the **draft documents in this repo** address, not whether controls are implemented or effective. This mapping is indicative, is not legal or audit advice, and should be validated with your compliance owner or auditor.

## 4. Article Mapping
**Coverage summary (20 items):** Covered 4 | Partial 8 | Gap 8

| Article | Obligation | Coverage | Repo Documents | Notes |
|---|---|---|---|---|
| Art. 5(1)(f), 5(2) | Integrity and confidentiality; accountability | Partial | [GOV-002](../01-governance/access-control-policy.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md), [TPL](../templates/document-template.md) | Security principle supported; accountability needs records and policies |
| Art. 6-9 | Lawful basis, consent, special categories | Gap | - | Privacy policy and lawful basis register needed |
| Art. 12-23 | Transparency and data subject rights | Gap | - | DSAR procedure needed |
| Art. 24 | Responsibility of the controller | Partial | [GOV-001](../01-governance/risk-register-template.md) |  |
| Art. 25 | Data protection by design and by default | Gap | - | Secure SDLC / privacy-by-design guidance needed |
| Art. 28 | Processor obligations and contracts | Gap | - | DPA template and vendor policy needed |
| Art. 30 | Records of processing activities | Gap | - | RoPA template needed |
| Art. 32(1)(a) | Pseudonymisation and encryption | Gap | - | Cryptography policy needed |
| Art. 32(1)(b) | Ongoing confidentiality, integrity, availability, and resilience | Partial | [GOV-002](../01-governance/access-control-policy.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) |  |
| Art. 32(1)(c) | Ability to restore availability and access to personal data in a timely manner | Covered | [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md), [BC-002](../02-defensive/business-continuity/business-continuity-plan.md) | RTO/RPO, backups, recovery procedures |
| Art. 32(1)(d) | Regular testing, assessing, and evaluating effectiveness of measures | Partial | [OFF-001](../03-offensive/rules-of-engagement.md), [OFF-002](../03-offensive/statement-of-work.md), [OFF-003](../03-offensive/scope-and-authorization-letter.md), [OFF-004](../03-offensive/pentest-report-template.md), [IR-001](../02-defensive/incident-response/incident-response-plan.md), [BC-001](../02-defensive/business-continuity/disaster-recovery-plan.md) | Pentests and exercises |
| Art. 32(4) | Persons acting under authority process data only on instructions | Partial | [GOV-002](../01-governance/access-control-policy.md) | Access control; awareness needed |
| Art. 33(1) | Notify supervisory authority without undue delay and, where feasible, within 72 hours of awareness (unless unlikely to result in risk) | Covered | [IR-001](../02-defensive/incident-response/incident-response-plan.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | 72 h in force; see note on proposed 96 h |
| Art. 33(2) | Processor notifies controller without undue delay | Partial | [IR-PB-11](../02-defensive/incident-response/playbooks/pb-11-supply-chain-compromise.md) | Contractual flow-down needed in DPA |
| Art. 33(3) | Content of the notification | Partial | [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | Report template covers nature, scope, impact, measures; add DPO contact |
| Art. 33(5) | Document all breaches (facts, effects, remedial action) | Covered | [IR-003](../02-defensive/incident-response/incident-report-template.md), [IR-004](../02-defensive/incident-response/post-incident-review-template.md) | Maintain a breach register |
| Art. 34 | Communicate high-risk breaches to data subjects | Covered | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md), [BC-003](../02-defensive/business-continuity/crisis-management-plan.md) | Message templates in crisis plan to be drafted |
| Art. 35-36 | Data protection impact assessment and prior consultation | Gap | - | DPIA template needed |
| Art. 37-39 | Data protection officer | Partial | [IR-PB-03](../02-defensive/incident-response/playbooks/pb-03-data-breach.md) | DPO role referenced in breach playbook |
| Art. 44-49 | International transfers | Gap | - | Transfer impact assessment needed |

## Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
