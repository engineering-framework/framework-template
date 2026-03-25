# Deployment Approach Selected

## What this means
The deployment approach defines the strategy for releasing this initiative to production — whether it's a big-bang release, a blue/green deployment, a canary release to a percentage of users, a feature-flag-gated rollout, or a phased geographic or user-segment rollout.

## Why it matters
The wrong deployment approach can turn a good feature into a major incident. Releasing to all users simultaneously with no rollback plan maximizes blast radius if something goes wrong. Selecting the right approach based on the risk profile of the change reduces the impact of unexpected issues and allows the team to catch problems with a small percentage of users before they affect everyone.

## How to complete this
- Assess the risk level of this change: how much does it touch? How reversible is it?
- For high-risk changes, use a canary or feature-flag approach that allows targeted rollout and fast rollback
- For database schema changes, ensure the migration is backwards-compatible so a rollback doesn't require a DB migration revert
- Define the deployment sequence: which services deploy first? What's the coordination plan?
- Confirm the rollback procedure before deploying — everyone should know how to revert before they start
- Document the monitoring and success criteria used to decide when to proceed to the next rollout phase

## Definition of done
- [ ] Deployment approach documented and justified based on risk assessment
- [ ] Deployment sequence defined for multi-service changes
- [ ] Rollback procedure confirmed and accessible to the team
- [ ] Monitoring and go/no-go criteria defined for phased rollouts
