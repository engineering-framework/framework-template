# Data Models Designed

## What this means
Data model design defines the structure of the persistent data required by the system — tables, entities, relationships, field types, constraints, and indexes. It establishes the "shape" of the data before code is written and serves as the source of truth for both application developers and DBAs.

## Why it matters
A poorly designed data model is expensive to fix post-launch. Renaming columns, changing data types, or restructuring relationships in a production database requires careful migrations and often causes downtime risk. Investing time in data model design upfront prevents these costly changes and ensures the schema can support the access patterns the application requires.

## How to complete this
- List all new entities/tables required and their purpose
- Define fields for each entity: name, type, nullability, default values, and description
- Map relationships: one-to-many, many-to-many, and self-referential
- Design indexes based on the query patterns identified in the application design
- Review for normalization — avoid storing the same data in multiple places without good reason
- Have the data model reviewed by a DBA or senior engineer before writing migrations

## Definition of done
- [ ] All new tables/entities defined with fields and types
- [ ] Relationships and foreign keys documented
- [ ] Index strategy defined based on query patterns
- [ ] Data model reviewed by tech lead or DBA
- [ ] Migration plan for any changes to existing tables documented
