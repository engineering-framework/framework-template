# Test Cases — [Feature / Component Name]

| | |
|---|---|
| **Project** | [Project Name] |
| **Feature** | [Feature being tested] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Status** | Draft / Under Review / Approved |
| **Environment** | [Staging / QA / Production] |

---

## Test Scope

**In scope:**
- [What is being tested]
- [Component, service, or workflow covered]

**Out of scope:**
- [What is explicitly not tested here]
- [e.g., Third-party services are mocked]

---

## Test Environment

- **URL / endpoint:** [test environment URL]
- **Test data setup:** [describe any seed data or fixtures required]
- **Dependencies:** [any external services, feature flags, or configurations needed]
- **Reset procedure:** [how to reset test data between runs]

---

## Functional Test Cases

| ID | Description | Preconditions | Steps | Expected Result | Priority |
|----|-------------|---------------|-------|-----------------|----------|
| TC-001 | [Happy path description] | [State needed] | 1. [Step] 2. [Step] 3. [Step] | [Expected outcome] | P0 |
| TC-002 | [Second happy path] | [State needed] | 1. [Step] 2. [Step] | [Expected outcome] | P0 |
| TC-003 | [Validation error case] | [State needed] | 1. [Step] 2. [Step] | [Error message shown] | P1 |
| TC-004 | [Permission denied case] | User lacks permission | 1. Attempt [action] | 403 / access denied | P1 |
| TC-005 | [Empty state case] | No data exists | 1. Navigate to [page] | [Empty state shown] | P1 |
| TC-006 | [Boundary / edge case] | [State needed] | 1. [Step] | [Boundary behavior] | P2 |

---

## Edge Cases

| Scenario | Expected Behavior |
|----------|-------------------|
| [Input at maximum length limit] | [Truncated / rejected with validation error] |
| [Concurrent modification by two users] | [Last write wins / conflict error shown] |
| [Network timeout during operation] | [Retry prompt / graceful error message] |
| [Session expires mid-flow] | [Redirect to login, return to original page after auth] |
| [Empty / null inputs for optional fields] | [Accepted, stored as null, rendered as empty state] |

---

## Regression Tests

*Tests that verify existing functionality is not broken by this change:*

| ID | Area | Test | Expected |
|----|------|------|----------|
| REG-001 | [Affected area] | [What to verify] | [Unchanged behavior] |
| REG-002 | [Affected area] | [What to verify] | [Unchanged behavior] |

---

## Performance Acceptance Criteria

| Metric | Threshold | Measurement Method |
|--------|-----------|-------------------|
| Page load time (p95) | < [Xms] | [Tool/method] |
| API response time (p99) | < [Xms] | [Tool/method] |
| Throughput under load | [X req/s] with < [Y%] error rate | [Load test tool] |

---

## Test Data Requirements

*Describe what data needs to exist for these tests to run:*

- [e.g., At least 1 organization with PRO plan]
- [e.g., User with admin role in that organization]
- [e.g., 3+ projects in different phases]
