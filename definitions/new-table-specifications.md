# New Table Specifications

## What this means
When a new database table is required, a table specification document captures the complete definition before the migration is written: column names, types, constraints, indexes, foreign keys, estimated data volume, and expected query patterns. This serves as the design contract between the developer and the database.

## Why it matters
Writing migrations without a reviewed spec leads to inconsistent naming conventions, missing indexes, poor constraint definitions, and data model decisions that don't scale. A table spec forces you to think through access patterns before writing code, and provides a document to review before making irreversible changes to the production schema.

## How to complete this
- Use the New Table Specification template for each new table
- Define every column with its type, nullability, default, and description
- List all indexes and explain which query pattern each one supports
- Document foreign key relationships and cascade behaviors
- Estimate the data volume (initial rows, growth rate, row size) to inform storage planning
- Have the spec reviewed by a tech lead or DBA before writing the migration

## Definition of done
- [ ] Specification created for each new table using the standard template
- [ ] All columns defined with types and constraints
- [ ] Index strategy documented with query pattern justifications
- [ ] Spec reviewed and approved by tech lead
- [ ] Migration written against the approved spec (not ad-hoc)
