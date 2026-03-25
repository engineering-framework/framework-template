# Success Criteria and KPIs — [Project Name]

| | |
|---|---|
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Status** | Draft / Under Review / Approved |

---

## Primary Success Metrics

*Define the 2-4 metrics that will determine whether this initiative is a success. These should be directly tied to the problem being solved.*

| Metric | Baseline | Target | Timeline |
|--------|----------|--------|----------|
| [e.g., API p99 latency] | [current value] | [target value] | [date] |
| [e.g., User activation rate] | [current value] | [target value] | [date] |
| [e.g., Error rate] | [current value] | [target value] | [date] |

---

## Secondary Metrics

*Supporting metrics that indicate health and provide leading indicators. These help diagnose issues but are not the primary measure of success.*

| Metric | Baseline | Target | Notes |
|--------|----------|--------|-------|
| [e.g., Daily active users] | | | |
| [e.g., Support ticket volume] | | | |
| [e.g., Feature adoption rate] | | | |

---

## Baseline Measurements

*Document how baseline values were measured, when, and any caveats.*

- **Measurement period:** [date range]
- **Data source:** [e.g., Datadog, Mixpanel, internal analytics]
- **Sampling methodology:** [e.g., 7-day rolling average, p95 over 30 days]
- **Caveats / known limitations:** [e.g., seasonal variance, incomplete data before X date]

---

## Measurement Methodology

*How will we measure success post-launch? Define tools, queries, and ownership.*

- **Tooling:** [e.g., Grafana dashboard, Amplitude funnel, SQL query in data warehouse]
- **Measurement frequency:** [e.g., daily, weekly]
- **Dashboard / report location:** [link or description]
- **Owner:** [team or person responsible for tracking]

---

## Review Cadence

- **Launch + 1 week:** Initial health check — [who reviews, what threshold triggers concern]
- **Launch + 1 month:** Full metric review — [who reviews, success/failure decision criteria]
- **Launch + 3 months:** Long-term impact assessment

---

## Anti-Metrics

*Things we explicitly are NOT optimizing for — helps prevent gaming metrics or unintended consequences.*

- We will not optimize for [metric] at the expense of [other metric]
- [e.g., We are not targeting raw traffic volume if it degrades conversion quality]

---

## Definition of Success

*Write a plain-English statement of what success looks like 3 months after launch.*

> [e.g., "Three months after launch, we have reduced customer churn attributed to X by 20%, without increasing support ticket volume or degrading p99 latency below our SLO."]
