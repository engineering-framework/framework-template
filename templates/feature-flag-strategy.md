# Feature Flag Strategy — [Feature Name]

| | |
|---|---|
| **Feature** | [Feature Name] |
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Flag Provider** | [e.g., LaunchDarkly, Unleash, in-house] |
| **Expected Cleanup Date** | [YYYY-MM-DD] |

---

## Feature Overview

**Description:** [What this feature does and why it's being flag-guarded]

**Reason for flag:** [e.g., Gradual rollout to reduce risk / A/B test / Kill switch for risky migration]

---

## Flag Definitions

| Flag Name | Type | Default (prod) | Default (dev) | Description |
|-----------|------|---------------|---------------|-------------|
| `[feature-name-enabled]` | Boolean | `false` | `true` | Main feature gate |
| `[feature-name-new-ui]` | Boolean | `false` | `true` | New UI variant |
| `[feature-name-limit]` | Number | `100` | `1000` | [Config value controlled by flag] |

**Flag naming convention:** `[team]-[feature]-[aspect]` using kebab-case, all lowercase.

---

## Rollout Plan

| Phase | Audience | Start Date | Success Criteria Before Proceeding |
|-------|----------|-----------|-------------------------------------|
| 1 — Internal | Engineering team members only | [date] | No P0/P1 bugs; metrics baseline established |
| 2 — Alpha | [X% of internal users / named users] | [date] | Error rate < 0.1%; latency within SLO |
| 3 — Beta | [X% of paid customers] | [date] | Satisfaction signal positive; no data issues |
| 4 — GA | 100% of eligible users | [date] | All success criteria met |

**Rollout owner:** [Name] — responsible for monitoring each phase and approving progression.

---

## Targeting Rules

*Define who gets each flag value and how targeting is determined:*

- **Phase 1:** Email matches `*@[yourdomain].com`
- **Phase 2:** User ID in `[named list or beta cohort]` OR organization has `beta_access: true` attribute
- **Phase 3:** Organization plan = `PRO` OR `ENTERPRISE` — random 20% sample
- **Phase 4:** All users

**Exclusions:**
- [e.g., Organizations in the EU excluded until data residency confirmed]

---

## Observability & Metrics

*How will we monitor the rollout? What signals indicate a problem?*

| Metric | Baseline | Alert Threshold | Dashboard |
|--------|----------|-----------------|-----------|
| Error rate for flagged endpoint | [X%] | > 1% | [link] |
| p99 latency | [Xms] | > [Yms] | [link] |
| [Feature-specific metric] | [baseline] | [threshold] | [link] |

**Comparison:** Flag-on vs flag-off cohorts should be compared for all metrics.

---

## Rollback Procedure

If a problem is detected:

1. **Immediate:** Set flag to `false` for affected cohort in [flag provider dashboard] — [estimated time: < 2 minutes]
2. **Verify:** Monitor error rate for 5 minutes to confirm recovery
3. **Communicate:** Post in [#incident-channel] with flag state change and impact summary
4. **Investigate:** Keep flag off until root cause identified
5. **Re-enable:** Only with explicit sign-off from [lead/manager]

---

## Cleanup Plan

*Long-lived flags become technical debt. This flag must be removed.*

- **Target removal date:** [YYYY-MM-DD] (after GA rollout is stable for 2+ weeks)
- **Cleanup task:** [Link to ticket]
- **Cleanup involves:**
  - Remove flag check from `[file path]`
  - Delete flag from [flag provider]
  - Remove flag from test fixtures
  - Update documentation
- **Blocker for removal:** [e.g., Flag must remain until v1 is deprecated]
