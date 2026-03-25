# API Specification — [Service / Feature Name]

| | |
|---|---|
| **Project** | [Project Name] |
| **Service** | [Service Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Status** | Draft / Under Review / Approved |
| **Version** | v1 |

---

## Overview

**Base URL:** `https://api.[domain]/v1`

**Authentication:** Bearer token (JWT) — include in `Authorization: Bearer <token>` header

**Content-Type:** `application/json`

---

## Endpoints

### `GET /[resource]`

**Description:** [What this endpoint returns and when it's used]

**Authorization:** [Required role/scope — e.g., `read:resources`]

#### Query Parameters

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `limit` | integer | No | 20 | Max results to return (max: 100) |
| `offset` | integer | No | 0 | Pagination offset |
| `[param]` | [type] | [Yes/No] | [default] | [description] |

#### Response `200 OK`

```json
{
  "data": [
    {
      "id": "cuid_example",
      "name": "Example resource",
      "createdAt": "2026-01-01T00:00:00Z"
    }
  ],
  "pagination": {
    "total": 42,
    "limit": 20,
    "offset": 0
  }
}
```

---

### `POST /[resource]`

**Description:** [What this endpoint creates]

**Authorization:** [Required role/scope]

#### Request Body

```json
{
  "name": "string (required, 1-200 chars)",
  "description": "string (optional)",
  "[field]": "[type and constraints]"
}
```

#### Response `201 Created`

```json
{
  "id": "cuid_example",
  "name": "string",
  "createdAt": "2026-01-01T00:00:00Z"
}
```

---

### `GET /[resource]/:id`

**Description:** [Retrieve a single resource by ID]

#### Response `200 OK`

```json
{
  "id": "cuid_example",
  "name": "string",
  "description": "string or null",
  "createdAt": "2026-01-01T00:00:00Z",
  "updatedAt": "2026-01-01T00:00:00Z"
}
```

---

### `PATCH /[resource]/:id`

**Description:** [Partial update — only provided fields are changed]

#### Request Body

```json
{
  "name": "string (optional)",
  "description": "string or null (optional)"
}
```

#### Response `200 OK`

*Returns the updated resource (same shape as GET)*

---

### `DELETE /[resource]/:id`

**Description:** [What deletion means — hard delete or soft delete?]

#### Response `204 No Content`

---

## Error Responses

| Status | Code | Description |
|--------|------|-------------|
| `400` | `VALIDATION_ERROR` | Request body failed validation |
| `401` | `UNAUTHORIZED` | Missing or invalid authentication token |
| `403` | `FORBIDDEN` | Authenticated but lacks permission |
| `404` | `NOT_FOUND` | Resource does not exist |
| `409` | `CONFLICT` | [e.g., Duplicate slug] |
| `429` | `RATE_LIMITED` | Too many requests |
| `500` | `INTERNAL_ERROR` | Unexpected server error |

**Error shape:**
```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Human-readable description",
    "details": [{ "field": "name", "message": "Required" }]
  }
}
```

---

## Rate Limits

- **Default:** 1000 requests / minute per authenticated user
- **Burst:** Up to 50 requests / second
- Headers: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`

---

## Versioning

- API version is included in the URL path (`/v1/`)
- Breaking changes increment the major version
- Non-breaking additions are deployed in-place with changelog notice
- Current version: `v1` — [deprecation timeline if applicable]
