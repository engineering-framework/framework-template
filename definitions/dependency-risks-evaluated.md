# Dependency Risks Evaluated

## What this means
Dependency risks are risks that arise from relying on things outside your control: other teams' deliverables, third-party services, external APIs, open-source libraries, or vendor platforms. Evaluating these risks means identifying what could go wrong with each dependency and planning accordingly.

## Why it matters
Dependencies are where most unexpected blockers come from. Another team ships late, a vendor API changes without notice, a library has a breaking update. When dependency risks are evaluated upfront, the team can build in contingency, identify alternative approaches, or negotiate earlier delivery from dependent teams — rather than discovering the problem when it's already blocking work.

## How to complete this
- List all external dependencies (other teams, third parties, vendors, libraries)
- For each, evaluate: what's the probability they deliver on time? What's the impact if they don't?
- For high-risk dependencies, create a contingency plan: can the feature be built with a stub first and integrated later? Is there an alternative?
- Establish early integration milestones for high-risk dependencies — don't wait until the end to find out if an integration works
- Track dependency commitments the same way you track internal commitments

## Definition of done
- [ ] All dependencies listed and risk-assessed
- [ ] Contingency plans created for high-risk dependencies
- [ ] Early integration milestones established for critical external dependencies
- [ ] Dependency risks documented in the risk register
