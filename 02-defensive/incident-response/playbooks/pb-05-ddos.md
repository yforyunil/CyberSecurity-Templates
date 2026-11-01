# PB-05 Distributed Denial of Service (DDoS) Playbook

| Field | Value |
|---|---|
| Document ID | IR-PB-05 |
| Version | 0.1 |
| Status | Draft |
| Owner | <role/team> |
| Classification | Internal |
| Parent Document | [Incident Response Plan](../incident-response-plan.md) |
| Last Reviewed | YYYY-MM-DD |
| Next Review | YYYY-MM-DD |

---

## 1. Overview
**Purpose:** Maintain availability and restore service during volumetric, protocol, or application-layer denial-of-service attacks.
**ATT&CK:** T1498 Network Denial of Service, T1499 Endpoint Denial of Service.

## 2. Triggers / Detection
- [ ] Sudden traffic spike, bandwidth saturation, or connection exhaustion
- [ ] Monitoring/synthetic checks failing; elevated latency or 5xx errors
- [ ] WAF/CDN/ISP alerts; firewall resource exhaustion
- [ ] Extortion/ransom DDoS threat received
- [ ] Attack used as smokescreen: check for concurrent intrusion activity

## 3. Severity Guidance
| Condition | Severity |
|---|---|
| Minor degradation, auto-mitigated | SEV4 |
| Partial service impact on non-critical service | SEV3 |
| Major customer-facing service degraded | SEV2 |
| Complete outage of critical service or prolonged attack | SEV1 |

## 4. Roles
| Role | Responsibility in this playbook |
|---|---|
| Incident Commander | Owns decisions, escalation, and status updates |
| IR Analyst(s) | Investigation, containment, evidence collection |
| IT / Infrastructure | Execute isolation, rebuild, restore |
| Communications Lead | Internal and external messaging |
| Legal / Privacy | Regulatory and contractual obligations |
| Network / Infrastructure | Traffic engineering, filtering |
| ISP / CDN / Scrubbing provider | Upstream mitigation |

## 5. Investigation
- [ ] Confirm it is an attack, not a legitimate surge (campaign, outage, misconfiguration)
- [ ] Classify: volumetric (UDP/ICMP flood, amplification), protocol (SYN flood), application (HTTP flood, slow-rate)
- [ ] Identify targets (IPs, services, URLs), peak bps/pps/rps, and source patterns
- [ ] Capture sample traffic (pcap/NetFlow) and request signatures (user agents, paths, headers)
- [ ] Look for secondary activity (scans, intrusion attempts, data access)

## 6. Containment / Mitigation
- [ ] Engage ISP/CDN/DDoS scrubbing service; activate always-on or on-demand protection
- [ ] Enable rate limiting, geo/ASN filtering, challenge pages (CAPTCHA/JS), bot management
- [ ] Apply WAF rules for identified request signatures
- [ ] Blackhole/RTBH or reroute only as last resort (it completes the DoS for the target)
- [ ] Scale out or shift traffic (autoscaling, secondary region, static fallback page)
- [ ] Protect origin IPs; ensure origin accepts traffic only from CDN/scrubber ranges
- [ ] Disable non-essential, resource-heavy features temporarily

## 7. Eradication
- [ ] Close amplification vectors on own infrastructure (open resolvers, NTP, memcached)
- [ ] Harden origin exposure; review DNS to avoid leaking origin IPs
- [ ] If own hosts were abused as botnet nodes, treat as malware incident (PB-07)

## 8. Recovery
- [ ] Gradually relax emergency controls while monitoring
- [ ] Verify service health, capacity, and data integrity
- [ ] Keep elevated monitoring for repeat waves (attackers often return)

## 9. Communications
- [ ] Status page and customer updates; internal updates every defined interval
- [ ] Do not engage or pay extortion demands without Legal/executive decision; report to law enforcement
- [ ] SLA/contract implications reviewed with business owners

## 10. Evidence to Collect
Traffic captures/NetFlow, provider reports, WAF/CDN logs, timeline of impact, extortion message.

### 10.1 Closure Criteria & Metrics
- Traffic normalized, service stable, mitigation tuned
- Metrics: attack duration, peak bandwidth/rps, downtime, time to mitigate

## 11. Related Documents
- [Incident Response Plan](../incident-response-plan.md)
- [Incident Report Template](../incident-report-template.md)
- [Chain of Custody Form](../chain-of-custody-form.md)
- [Post-Incident Review Template](../post-incident-review-template.md)

## 12. Revision History
| Version | Date | Author | Change |
|---|---|---|---|
| 0.1 | YYYY-MM-DD | | Initial draft |
