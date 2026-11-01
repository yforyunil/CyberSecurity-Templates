# Disaster Recovery Plan (DRP)

| Field | Value |
|---|---|
| Document ID | BC-001 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Purpose & Scope
## 2. Objectives
RTO and RPO targets per system tier.

## 3. System Tiering
| Tier | Description | RTO | RPO | Example Systems |
|---|---|---|---|---|
| 0 | Mission critical | < 1 h | ~0 | |
| 1 | Business critical | < 4 h | < 1 h | |
| 2 | Important | < 24 h | < 24 h | |
| 3 | Non-critical | < 72 h | < 1 wk | |

## 4. Disaster Scenarios
Data center loss, cloud region outage, ransomware, power/network failure, pandemic, natural disaster.

## 5. DR Organization
| Role | Name | Responsibilities | Contact |
|---|---|---|---|
| DR Coordinator | | | |
| Infrastructure Lead | | | |
| Application Lead | | | |
| Communications Lead | | | |

## 6. Activation Criteria & Declaration Process
## 7. Recovery Strategy
Backup/restore, replication, hot/warm/cold sites, cloud failover, immutable and offline backups.

## 8. Recovery Procedures (per system)
- Dependencies, prerequisites
- Step-by-step restore
- Validation and acceptance tests
- Rollback / failback

## 9. Backup Management
Schedule, retention, encryption, offsite/offline copies, restore testing.

## 10. Communications
## 11. Testing & Maintenance
Test types: walkthrough, tabletop, failover, full simulation. Annual minimum.

## 12. Appendices
Asset inventory, vendor contacts, network diagrams, credentials escrow (break-glass) references.

## 13. Revision History
