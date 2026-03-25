# Operational Runbook — [Service Name]

| | |
|---|---|
| **Service** | [Service Name] |
| **Team** | [Owning team] |
| **Last Updated** | [YYYY-MM-DD] |
| **On-call Rotation** | [Link to PagerDuty / oncall schedule] |
| **Slack Channel** | [#channel-name] |

---

## Service Overview

**What it does:** [1-2 sentences describing the service and its role in the system]

**Users / dependents:** [Who uses this service and what depends on it]

**Architecture summary:** [Brief description — e.g., Node.js API behind load balancer, reading from Postgres, writing to Kafka]

**Deployment:** [Where and how it runs — e.g., Kubernetes on EKS, Fly.io, Vercel]

---

## Key Links

| Resource | Link |
|----------|------|
| Dashboard / Monitoring | [URL] |
| Logs | [URL] |
| Deployment pipeline | [URL] |
| Repository | [URL] |
| Architecture diagram | [URL] |
| Incident history | [URL] |

---

## Common Alerts & Resolution Steps

### Alert: [High Error Rate]

**Trigger:** Error rate > 1% for 5 minutes

**Severity:** P1

**Investigation:**
1. Check logs for the most frequent error messages: `[log query or command]`
2. Check recent deployments — was there a deploy in the last 30 minutes?
3. Check database connectivity: `[command or dashboard link]`
4. Check upstream dependencies for issues

**Resolution:**
- If caused by bad deploy: roll back using `[rollback command]`
- If database issue: see [Database section below]
- If upstream: notify [team] and update status page

---

### Alert: [High Latency]

**Trigger:** p99 latency > [X]ms for 5 minutes

**Severity:** P2

**Investigation:**
1. Check database query performance: `[slow query log link]`
2. Check cache hit rate: `[metric link]`
3. Check for traffic spike: `[dashboard link]`
4. Check for N+1 queries or missing indexes in recent code changes

**Resolution:**
- If traffic spike: trigger auto-scaling or add capacity manually
- If slow query: identify query, check for lock contention, consider query optimization

---

### Alert: [Service Down / No Healthy Instances]

**Trigger:** 0 healthy instances for 2 minutes

**Severity:** P0

**Investigation:**
1. Check deployment status: `[command]`
2. Check pod/instance logs for crash errors: `[command]`
3. Check infrastructure health: `[cloud console link]`
4. Check for OOM kills or disk pressure

**Resolution:**
1. Restart service: `[command]`
2. If restart fails, check resource limits and adjust: `[command]`
3. If infrastructure issue, escalate to platform team

---

## Incident Response Steps

1. **Acknowledge** the alert in PagerDuty within 5 minutes
2. **Assess** severity and update the incident channel with initial findings
3. **Communicate** status to stakeholders: post in [#channel] every 15 minutes during P0/P1
4. **Mitigate** using procedures above; escalate if unresolved within 20 minutes
5. **Resolve** and mark incident resolved in PagerDuty
6. **Post-mortem** required for all P0/P1 incidents within 48 hours

---

## Escalation Contacts

| Role | Contact | When to Escalate |
|------|---------|-----------------|
| On-call engineer | [PagerDuty rotation] | First contact |
| Engineering lead | [Name / Slack] | Unresolved after 20 min |
| Platform team | [#platform-oncall] | Infrastructure issues |
| Database admin | [Name / Slack] | DB performance / corruption |

---

## Maintenance Procedures

### Deploying a New Version

1. Ensure all tests pass in CI
2. Deploy to staging: `[command]`
3. Verify staging with smoke tests: `[command]`
4. Deploy to production: `[command]`
5. Monitor error rate and latency for 10 minutes post-deploy
6. If issues arise: `[rollback command]`

### Database Migrations

1. Verify migration is backwards-compatible (old code works with new schema)
2. Run migration on staging: `[command]`
3. Verify no data anomalies
4. Run migration on production during low-traffic window: `[command]`
5. Monitor for 30 minutes

### Disaster Recovery

**RTO (Recovery Time Objective):** [e.g., 2 hours]
**RPO (Recovery Point Objective):** [e.g., 1 hour — last backup]

1. [Step-by-step recovery procedure]
2. [Restore from backup: command]
3. [Verify data integrity]
4. [Notify stakeholders]
