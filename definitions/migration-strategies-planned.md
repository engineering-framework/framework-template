# Migration Strategies Planned

## What this means
When this initiative requires migrating data, users, or systems from an old state to a new one, migration strategies define the approach: how data will be transformed and moved, how the cutover will happen, how backwards compatibility will be maintained during transition, and how to roll back if migration fails.

## Why it matters
Migrations are one of the highest-risk operations in software engineering. Data migrations in production affect real user data with no ability to undo if something goes wrong. A well-planned migration has a test run, a validation step, a clear rollback procedure, and is reversible for as long as feasible. Unplanned migrations cause data loss, extended downtime, and cascading failures.

## How to complete this
- Define the migration scope: what data or systems are being migrated and from/to where
- Choose a migration pattern: big-bang cutover, expand-contract (dual-write), or incremental/phased migration
- Plan validation: how will you verify migration correctness before, during, and after?
- Define the rollback plan: at what point does rollback become impossible, and what's the plan until then?
- Test the migration on a copy of production data in staging
- Plan for communication: who needs to know about downtime or behavior changes during migration?

## Definition of done
- [ ] Migration scope and approach documented
- [ ] Migration pattern chosen with rationale
- [ ] Validation approach defined
- [ ] Rollback procedure documented and tested in staging
- [ ] Migration rehearsal completed on staging before production
