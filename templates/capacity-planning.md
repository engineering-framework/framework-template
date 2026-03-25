# Capacity Planning — [Service / Feature Name]

| | |
|---|---|
| **Service** | [Service Name] |
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Planning Horizon** | [e.g., 12 months] |

---

## Current State

*Baseline measurements at the time of this document:*

| Resource | Current Usage | Current Capacity | Utilization |
|----------|---------------|-----------------|-------------|
| Web servers | [X] instances | [Y] max instances | [Z%] |
| Database (CPU) | [X]% avg | 100% | [Z%] |
| Database (Storage) | [X] GB | [Y] GB | [Z%] |
| Cache (Memory) | [X] GB | [Y] GB | [Z%] |
| Background workers | [X] instances | [Y] max | [Z%] |
| CDN / bandwidth | [X] GB/month | [Y] GB/month | [Z%] |

**Current peak load:** [requests/second or other relevant metric]

**Current p99 latency:** [Xms]

---

## Growth Projections

*Assumptions: [describe growth model — e.g., linear based on sales pipeline, historical 20% MoM]*

| Metric | Current | 3 Months | 6 Months | 12 Months |
|--------|---------|----------|----------|-----------|
| Monthly active users | [X] | [Y] | [Y] | [Y] |
| Requests / second (peak) | [X] | [Y] | [Y] | [Y] |
| Data volume (GB) | [X] | [Y] | [Y] | [Y] |
| Database rows ([table]) | [X] | [Y] | [Y] | [Y] |

---

## Resource Requirements

### Compute

| Scenario | Instance Type | Count | Estimated Cost/month |
|----------|--------------|-------|----------------------|
| Current | [type] | [n] | $[X] |
| 3-month projection | [type] | [n] | $[X] |
| 6-month projection | [type] | [n] | $[X] |
| 12-month projection | [type] | [n] | $[X] |

### Database

| Scenario | Instance | Storage | Read Replicas | Estimated Cost/month |
|----------|----------|---------|---------------|----------------------|
| Current | [class] | [X] GB | [n] | $[X] |
| 12-month projection | [class] | [X] GB | [n] | $[X] |

### Other Resources

| Resource | Current Cost | 12-month Projection | Notes |
|----------|-------------|---------------------|-------|
| CDN | $[X]/mo | $[X]/mo | [notes] |
| Cache | $[X]/mo | $[X]/mo | [notes] |
| Monitoring/observability | $[X]/mo | $[X]/mo | [notes] |

---

## Scaling Triggers

*Thresholds that should trigger scaling actions:*

| Resource | Metric | Scale-up Trigger | Scale-down Trigger | Action |
|----------|--------|------------------|--------------------|--------|
| Web servers | CPU | > 70% for 5 min | < 30% for 15 min | Auto-scale ±[n] instances |
| Database | CPU | > 80% | N/A | Manual upgrade — alert team |
| Queue depth | Messages | > [X] | < [Y] | Scale workers |

---

## Bottlenecks Identified

*Known constraints that will limit scaling before other resources:*

1. **[Bottleneck 1]:** [Description and approximate when it becomes a problem]
   - *Mitigation:* [Plan to address it]

2. **[Bottleneck 2]:** [Description]
   - *Mitigation:* [Plan]

---

## Scaling Strategy

- **Horizontal scaling:** [Services that scale horizontally — describe approach]
- **Vertical scaling:** [Services where vertical scaling applies — describe approach]
- **Auto-scaling:** [What is auto-scaled and under what policy]
- **Database scaling:** [Sharding, read replicas, caching strategy]

---

## Assumptions & Risks

- **Assumption:** [e.g., Growth follows historical 15% MoM pattern]
- **Risk:** [e.g., A viral event could cause 10x spike — runbook exists for burst capacity]
- **Risk:** [e.g., Database migration required before hitting 6-month projection — 4-week lead time]
