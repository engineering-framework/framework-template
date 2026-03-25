# Downstream Service Impacts Assessed

## What this means
Downstream services are services that depend on or consume from this initiative — they call your APIs, subscribe to your events, or read from your data stores. Assessing downstream impacts means evaluating how changes in behavior, schema, or interfaces will affect your consumers.

## Why it matters
Downstream consumers are often overlooked in design because they're not blocking your work — but they're the ones who break when you ship. API contract changes, event schema changes, or data model changes can silently break downstream consumers if not coordinated in advance. The more downstream consumers you have, the higher the risk of uncoordinated change.

## How to complete this
- Identify all services, teams, or clients that consume your APIs, events, or data
- Review planned changes for anything that would break consumers: removed fields, renamed endpoints, changed semantics
- For breaking changes, plan a migration path: dual-write period, versioning, advance notice
- Communicate with downstream consumers before making interface changes
- Understand the deployment cadences of downstream consumers — some may need weeks of lead time to update

## Definition of done
- [ ] All downstream consumers identified
- [ ] Breaking changes identified and migration paths planned
- [ ] Downstream teams notified with adequate advance notice
- [ ] Dual-write or versioning strategy in place for any breaking API or schema changes
