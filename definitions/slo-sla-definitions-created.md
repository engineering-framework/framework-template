# SLO / SLA Definitions Created

## What this means
Service Level Objectives (SLOs) are internal targets for system reliability (availability, latency, error rate). Service Level Agreements (SLAs) are commitments made to external customers, often with contractual consequences. Creating these definitions means translating performance expectations into formal, measurable targets with defined measurement windows and error budgets.

## Why it matters
SLOs give reliability work a quantitative foundation. Without them, reliability improvements compete with features with no objective way to prioritize. The error budget concept — how much unreliability is acceptable — allows teams to make data-driven decisions about when to slow feature development in favor of reliability work. SLAs protect customers and create accountability.

## How to complete this
- Define SLOs for availability, latency, and error rate using the SLO/SLA definitions template
- Calculate error budgets for each SLO (the acceptable window of non-compliance)
- Define what happens when error budgets are exhausted (reliability work prioritized over features)
- Determine which SLOs translate into customer-facing SLAs and at what tier
- Configure measurement dashboards so SLOs are visible and tracked continuously
- Schedule a quarterly SLO review to adjust targets based on operational experience

## Definition of done
- [ ] SLOs defined for availability, latency, and error rate
- [ ] Error budgets calculated and documented
- [ ] Error budget policy defined (what triggers reliability prioritization)
- [ ] SLO measurement configured in monitoring tooling
- [ ] Customer-facing SLAs defined if applicable
