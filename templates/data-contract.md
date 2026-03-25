# Data Contract — [Contract Name]

| | |
|---|---|
| **Contract Name** | [Descriptive name, e.g., "Order Events from Commerce to Analytics"] |
| **Producer** | [Team / Service producing the data] |
| **Consumer(s)** | [Team / Service(s) consuming the data] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Version** | 1.0.0 |
| **Status** | Draft / Active / Deprecated |

---

## Contract Overview

**Purpose:** [One paragraph explaining what data is being shared, why, and the business value it enables]

**Data source:** [e.g., Postgres `orders` table, Kafka topic `commerce.order.events`, REST API response]

**Delivery mechanism:** [e.g., Kafka event stream, REST API polling, S3 file drop, direct DB read replica]

**Frequency / Latency:** [e.g., Real-time stream, batch daily at 02:00 UTC, on-demand API]

---

## Data Schema

### [Entity / Event Name]

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `id` | `string (uuid)` | Yes | Unique identifier |
| `createdAt` | `string (ISO 8601)` | Yes | When the record was created |
| `[field]` | `[type]` | [Yes/No] | [description] |
| `[field]` | `[type]` | [Yes/No] | [description] |

**Example payload:**
```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "createdAt": "2026-01-01T12:00:00Z",
  "[field]": "[example value]"
}
```

---

## Validation Rules

*Rules enforced by the producer before data is published:*

- `[field]` must be a valid UUID
- `[field]` must be one of: `[value1]`, `[value2]`, `[value3]`
- `[field]` must be non-null when `[other_field]` is `[condition]`
- All timestamps are UTC, formatted as ISO 8601

*Consumers should treat any data not conforming to these rules as invalid and handle accordingly.*

---

## SLA / Freshness Requirements

| Requirement | Value |
|-------------|-------|
| Maximum latency (event to availability) | [e.g., < 5 minutes] |
| Availability | [e.g., 99.9% during business hours] |
| Backfill support | [Yes / No — and how far back] |
| Data retention | [e.g., 90 days in stream, indefinite in data warehouse] |

---

## Change Management Process

Breaking changes require:
1. 30-day advance notice to all consumers
2. Updated contract version (major version bump)
3. Migration guide provided by producer
4. Dual-write period of [X weeks] during transition

Non-breaking additions (new optional fields):
1. 7-day advance notice
2. Minor version bump
3. Consumers must handle unknown fields gracefully

**Change log:**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0.0 | [date] | [name] | Initial version |

---

## Parties & Contacts

| Role | Team | Contact |
|------|------|---------|
| Producer owner | [team] | [slack channel or person] |
| Consumer owner | [team] | [slack channel or person] |
| Contract arbitrator | [team] | [slack channel or person] |

---

## Compliance & PII

- **Contains PII:** Yes / No
- **PII fields:** [list fields, or "none"]
- **Data classification:** Public / Internal / Confidential / Restricted
- **Encryption in transit:** Required / Not required
- **Encryption at rest:** Required / Not required
