# SLO / SLA Definitions — [Service Name]

| | |
|---|---|
| **Service** | [Service Name] |
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Review Date** | [Next scheduled review — e.g., quarterly] |
| **Owner** | [Team responsible for maintaining these SLOs] |

---

## Service Overview

**Description:** [What this service does and who depends on it]

**Criticality:** Tier 1 (business-critical) / Tier 2 (important) / Tier 3 (best-effort)

**Users:** [Internal teams / external customers / both]

---

## Service Level Objectives (SLOs)

*SLOs are internal targets. Breaching them triggers investigation but does not constitute a customer commitment.*

| SLO | Metric | Target | Measurement Window | Alerting Threshold |
|-----|--------|--------|-------------------|--------------------|
| Availability | Successful requests / total requests | 99.9% | 30-day rolling | < 99.5% |
| Latency (p50) | Median response time | < [X]ms | 7-day rolling | > [Y]ms |
| Latency (p99) | 99th percentile response time | < [X]ms | 7-day rolling | > [Y]ms |
| Error rate | 5xx errors / total requests | < 0.1% | 24-hour rolling | > 0.5% |
| [Custom SLO] | [Metric description] | [Target] | [Window] | [Threshold] |

---

## Service Level Agreements (SLAs)

*SLAs are external commitments to customers. Breaching them may trigger credits or contractual obligations.*

| Tier | Availability | Response Time (p95) | Support Response Time | Remediation |
|------|-------------|---------------------|----------------------|-------------|
| Enterprise | 99.9% | < [X]ms | < 1 hour (P1) | Service credits per contract |
| Pro | 99.5% | < [X]ms | < 4 hours (P1) | Service credits per contract |
| Free | 99.0% | < [X]ms | < 24 hours | Best effort |

---

## Error Budget

*Error budget = 1 - SLO target. It defines how much unreliability is acceptable.*

| SLO | Target | Error Budget (30-day) | Current Burn Rate |
|-----|--------|----------------------|-------------------|
| Availability (99.9%) | 99.9% | 43.8 min/month | [current] |
| [Other SLO] | [target] | [budget] | [current] |

**Error budget policy:**
- If error budget is < 50%: new feature work pauses; reliability improvements prioritized
- If error budget is < 10%: incident response required; change freeze in effect

---

## Measurement

- **Tooling:** [e.g., Datadog SLO dashboards, Prometheus, CloudWatch]
- **Dashboard:** [Link to live dashboard]
- **Alert routing:** [e.g., PagerDuty policy name]
- **Incident threshold:** [e.g., SLO breach sustained for 5 minutes triggers P1 page]

---

## Exclusions

*Events that are excluded from SLO calculations:*

- Planned maintenance windows (announced 48h in advance)
- Incidents caused by customer-side infrastructure (outside our control)
- Force majeure events (regional cloud provider outages)
- [Other exclusion]

---

## Review Process

- SLOs are reviewed quarterly by [team]
- SLA terms are reviewed annually with legal and business stakeholders
- Significant architecture changes trigger an ad-hoc SLO review
