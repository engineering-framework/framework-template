# Operational Runbooks Written

## What this means
Operational runbooks are step-by-step procedures for the most common operational tasks and incidents involving this system — how to deploy, how to scale, how to investigate alerts, how to perform common maintenance tasks, and how to respond to specific failure scenarios.

## Why it matters
On-call engineers respond to alerts in the middle of the night, under stress, often without access to the people who built the system. A runbook turns a stressful unknown into a structured process. Runbooks are also how operational knowledge is preserved and shared across the team — they prevent the "only one person knows how to restart this service" problem.

## How to complete this
- Use the Operational Runbook template to structure the content
- Write runbook entries for every alert that the system will generate
- Include common operational procedures: deployments, rollbacks, DB migrations, certificate renewals
- Write for an audience that doesn't know the system deeply — include sufficient context and exact commands
- Test each runbook procedure by having a team member follow it without guidance
- Keep runbooks in a location accessible during incidents (not just in the codebase)

## Definition of done
- [ ] Runbook written covering all configured alerts and their resolution steps
- [ ] Common operational procedures documented with exact commands
- [ ] Runbook tested by a team member following it without guidance
- [ ] Runbook location communicated to all team members and the on-call rotation
