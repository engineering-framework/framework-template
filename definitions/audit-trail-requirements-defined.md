# Audit Trail Requirements Defined

## What this means
Audit trail requirements define which actions must be recorded for accountability, compliance, or security purposes — who did what, to which resource, when, and from where. This covers both user-facing actions and system-level operations that require a durable record.

## Why it matters
Audit trails serve multiple purposes: compliance mandates often require them, security investigations depend on them, and customer disputes are resolved with them. Audit requirements are often discovered too late, when customers ask "who deleted this record?" and the answer is "we don't know." Defining requirements upfront ensures the right events are captured from day one.

## How to complete this
- Identify operations that require an audit trail: sensitive mutations (deletes, role changes, financial operations), data exports, admin actions, and compliance-mandated events
- Define what each audit record must contain: timestamp, actor (user ID), action, resource, before/after state where applicable, and source IP
- Determine how long audit records must be retained (often 1–7 years depending on regulation)
- Decide where audit logs are stored — must they be immutable? Separate from operational logs?
- Confirm audit logging requirements with legal and compliance teams

## Definition of done
- [ ] Operations requiring audit trails identified
- [ ] Audit record schema defined (required fields per event)
- [ ] Retention requirements documented
- [ ] Storage and immutability requirements defined
- [ ] Audit requirements confirmed with legal/compliance
