# New Table Specification — [table_name]

| | |
|---|---|
| **Project** | [Project Name] |
| **Table Name** | `[schema.table_name]` |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Status** | Draft / Under Review / Approved |

---

## Table Overview

**Purpose:** [One sentence describing what this table stores and why it exists]

**Service / Owner:** [Which service owns this table and which team is responsible]

**Retention Policy:** [e.g., Indefinite / 90-day rolling / archive after 1 year]

---

## Column Definitions

| Column | Type | Nullable | Default | Description |
|--------|------|----------|---------|-------------|
| `id` | `uuid` | No | `gen_random_uuid()` | Primary key |
| `created_at` | `timestamptz` | No | `now()` | Record creation timestamp |
| `updated_at` | `timestamptz` | No | `now()` | Last modification timestamp |
| `[column_name]` | `[type]` | [Yes/No] | [value or —] | [description] |
| `[column_name]` | `[type]` | [Yes/No] | [value or —] | [description] |

---

## Indexes

| Index Name | Columns | Type | Purpose |
|------------|---------|------|---------|
| `[table]_pkey` | `id` | Primary | Primary key lookup |
| `[table]_[col]_idx` | `[column]` | BTree | [describe query pattern this supports] |
| `[table]_[col1]_[col2]_idx` | `[col1, col2]` | BTree | [compound index for...] |

---

## Foreign Keys

| Column | References | On Delete |
|--------|-----------|-----------|
| `[column]` | `[other_table.id]` | CASCADE / SET NULL / RESTRICT |

---

## Constraints & Validation

- **Check constraints:** [e.g., `status IN ('active', 'archived', 'deleted')`]
- **Unique constraints:** [e.g., `UNIQUE(organization_id, slug)`]
- **Not null beyond schema:** [additional application-level constraints]

---

## Migration Notes

*How will this table be created and populated? Any data migration needed?*

- **Creation:** New table — no existing data to migrate
  *OR*
- **Migration from:** [describe source table/data and transformation needed]
- **Backfill strategy:** [e.g., Background job, sync migration, manual one-time script]
- **Downtime required:** Yes / No — [reasoning]
- **Estimated migration time:** [rough estimate for production dataset]

---

## Query Patterns

*Document the primary read/write patterns to validate index design.*

```sql
-- Pattern 1: [description]
SELECT ... FROM [table] WHERE [condition];

-- Pattern 2: [description]
SELECT ... FROM [table] WHERE [condition] ORDER BY [column] LIMIT [n];
```

---

## Estimated Data Volume

| Metric | Estimate |
|--------|----------|
| Initial rows | [count] |
| Growth rate | [e.g., ~50K rows/month] |
| Row size (avg) | [e.g., ~500 bytes] |
| 1-year projected size | [e.g., ~3GB] |
