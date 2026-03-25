# Threat Model — [Feature / System Name]

| | |
|---|---|
| **System** | [Feature or system being modeled] |
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Reviewed by** | [Security team / name] |
| **Status** | Draft / Under Review / Accepted |

---

## System Overview

**Description:** [Brief description of the feature or system, including its purpose and user population]

**Technology stack:** [e.g., React frontend, Node.js API, PostgreSQL, AWS S3]

**Trust boundary summary:** [Who interacts with the system and from where — e.g., authenticated users over HTTPS, internal services over mTLS]

---

## Assets

*What are we protecting? List valuable data, services, and capabilities.*

| Asset | Description | Sensitivity |
|-------|-------------|-------------|
| [e.g., User PII] | Names, emails, phone numbers | High |
| [e.g., API keys / credentials] | Third-party service credentials | High |
| [e.g., Financial data] | Payment / billing records | High |
| [e.g., Service availability] | Uptime for end users | Medium |
| [e.g., Internal config] | Environment variables, feature flags | Medium |

---

## Trust Boundaries

*Define where trust levels change in the system:*

1. **External users → Load balancer:** All traffic treated as untrusted; TLS required
2. **Load balancer → API:** Trusted internal network; JWT validation required
3. **API → Database:** Trusted internal VPC; service account credentials required
4. **[Service A] → [Service B]:** [Trust model]

---

## Data Flow

*Describe or diagram how sensitive data moves through the system:*

1. User submits [data] via [interface]
2. Request passes through [component], authenticated by [mechanism]
3. Data is written to [storage], encrypted at rest using [method]
4. Data is returned to user via [response], filtered to [scope]
5. [Any third-party data sharing]

---

## STRIDE Analysis

| # | Threat Category | Description | Affected Component | Likelihood (1-5) | Impact (1-5) | Risk Score | Mitigation |
|---|----------------|-------------|-------------------|-------------------|--------------|------------|------------|
| T-01 | **Spoofing** | [e.g., Attacker forges JWT to impersonate user] | Auth middleware | 2 | 5 | 10 | JWT signature validation; short expiry |
| T-02 | **Tampering** | [e.g., User modifies request body to change another user's data] | API layer | 3 | 4 | 12 | Authorization checks on all mutations |
| T-03 | **Repudiation** | [e.g., User denies performing a sensitive action] | [Component] | 2 | 3 | 6 | Audit logging with user ID and timestamp |
| T-04 | **Information Disclosure** | [e.g., Error messages expose internal stack traces] | API error handler | 3 | 2 | 6 | Sanitize error responses in production |
| T-05 | **Denial of Service** | [e.g., Unauthenticated endpoint called at high rate] | API | 4 | 3 | 12 | Rate limiting; WAF rules |
| T-06 | **Elevation of Privilege** | [e.g., Regular user accesses admin endpoint] | RBAC layer | 2 | 5 | 10 | Role checks enforced at middleware level |
| T-07 | **[Category]** | [description] | [component] | | | | [mitigation] |

*Risk Score = Likelihood × Impact. Scores ≥ 10 require mitigation before launch.*

---

## Security Requirements

*Controls that must be implemented based on the threat analysis:*

- [ ] All API endpoints require authentication unless explicitly public
- [ ] Authorization checks applied at the controller layer — not just UI
- [ ] User input validated and sanitized before use in queries (prevent injection)
- [ ] PII encrypted at rest; encryption key management via [KMS/secret manager]
- [ ] Audit log written for: [list sensitive operations]
- [ ] Rate limiting on: [list endpoints]
- [ ] HTTPS enforced with HSTS header; no HTTP fallback
- [ ] [Additional requirement from threat analysis]

---

## Security Testing Approach

- **SAST:** [Tool — e.g., CodeQL, Snyk] — run in CI on every PR
- **Dependency scanning:** [Tool — e.g., Dependabot, `npm audit`] — weekly
- **Penetration test:** [Planned date or "on request"] — [scope]
- **Security review:** Architecture review with security team before launch
- **Bug bounty:** [In scope / out of scope]
