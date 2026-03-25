# Rollback Procedures — [Feature / Service Name]

| | |
|---|---|
| **Service / Feature** | [Name] |
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Last Tested** | [YYYY-MM-DD or "Untested"] |

---

## Overview

**What can be rolled back:** [Describe what is being deployed — application code, DB migration, config change, infrastructure]

**Rollback mechanism:** [e.g., Feature flag off / Git revert + redeploy / DB migration revert / Terraform destroy]

**Estimated rollback time:** [e.g., 5-10 minutes for code rollback; 30+ minutes for DB rollback]

**Data risk:** [None / Low / High — describe if data may be affected]

---

## Rollback Triggers

*Initiate rollback if ANY of these conditions are met:*

- [ ] Error rate exceeds [X%] for more than [Y] minutes after deploy
- [ ] p99 latency exceeds [Xms] sustained for [Y] minutes
- [ ] Critical business functionality is broken (as verified by smoke tests)
- [ ] Data corruption or inconsistency detected
- [ ] Security vulnerability discovered in newly deployed code
- [ ] On-call engineer judgment — "something is clearly wrong"

**Decision authority:** Any on-call engineer can initiate rollback without waiting for approval during P0/P1.

---

## Pre-Rollback Checklist

Before executing rollback:

- [ ] Confirm the deployed version is the cause (check recent deploy times vs incident start time)
- [ ] Alert the team in [#incident-channel]: "Initiating rollback of [feature/service] deployed at [time]"
- [ ] Note the current version: `[command to check current version]`
- [ ] Capture current metrics snapshot for post-mortem

---

## Rollback Steps

### Option A: Feature Flag Rollback (fastest — 2 minutes)

*Use when feature is behind a flag and the change only affects flagged users.*

1. Log in to [flag provider: URL]
2. Find flag `[flag-name]`
3. Set flag to `OFF` / `false` for all environments
4. Verify error rate drops within 2 minutes
5. Proceed to [Verification section]

---

### Option B: Application Code Rollback (5-10 minutes)

*Use when a code deploy is causing the issue and no DB schema changes were made.*

1. Identify the previous stable version/tag:
   ```
   [command — e.g., git log --oneline -10]
   ```
2. Trigger rollback in your deployment system:
   ```
   [command — e.g., fly deploy --image [previous-image]]
   [or: kubectl rollout undo deployment/[name]]
   [or: vercel rollback [deployment-id]]
   ```
3. Monitor deployment progress:
   ```
   [command to watch rollout status]
   ```
4. Verify deployment completed:
   ```
   [command to check running version]
   ```

---

### Option C: Database Migration Rollback (30+ minutes, HIGH RISK)

*Use only when a DB migration is causing data issues. Get senior engineer sign-off first.*

**⚠️ WARNING: DB rollbacks can cause data loss. Proceed only if the alternative is worse.**

1. **Stop write traffic** to affected service to prevent data during rollback:
   ```
   [command to scale down writers / set maintenance mode]
   ```
2. **Backup current state** before any changes:
   ```
   [backup command]
   ```
3. **Run down migration:**
   ```
   [migration rollback command]
   ```
4. **Verify schema** matches expected previous state
5. **Restore write traffic:**
   ```
   [command to restore]
   ```

---

## Verification Steps

After rollback, confirm recovery:

- [ ] Error rate returned to baseline (check [dashboard link])
- [ ] p99 latency back within SLO
- [ ] Smoke test passes: `[command or URL to test]`
- [ ] Key user flows work as expected: [list 2-3 critical paths to verify manually]

---

## Post-Rollback Communication

Post in [#incident-channel]:
> "Rollback of [feature/deployment] completed at [time]. Error rate is back to [X%]. Root cause investigation ongoing. ETA for fix: [estimate or TBD]."

Update status page if customer-facing impact occurred.

---

## Post-Mortem Requirements

- Required for: All P0 incidents; P1 incidents lasting > 30 minutes
- Template: [Link to post-mortem template]
- Due: Within 48 hours of resolution
- Owners: [Name of incident commander]
