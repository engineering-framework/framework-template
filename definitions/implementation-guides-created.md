# Implementation Guides Created

## What this means
Implementation guides are the internal technical documentation that explains how to work with the system that was built — how to extend it, configure it, integrate with it, and operate it. These are distinct from user documentation: they're written for engineers who will maintain or build on this work.

## Why it matters
Without implementation guides, every new engineer on the team requires extensive mentoring to contribute effectively. Knowledge becomes siloed in the few engineers who built the system. Implementation guides are the multiplier that allows the whole team to work on a system, not just the ones who built it. They also dramatically reduce the cost of onboarding.

## How to complete this
- Write a "how to get started" guide: how to run the service locally, how to run tests, how to deploy
- Document the key concepts and abstractions that the system introduces
- Provide code examples for common tasks (adding a new endpoint, extending the data model, adding a new test)
- Document configuration options and what each controls
- Include a troubleshooting section for known issues and how to diagnose them
- Store guides in version control alongside the code, not in a wiki that will diverge

## Definition of done
- [ ] Getting-started guide written (local setup, testing, deployment)
- [ ] Key concepts and abstractions documented with examples
- [ ] Configuration options documented
- [ ] Guides stored in version control
- [ ] Reviewed by a team member who wasn't involved in building the system
