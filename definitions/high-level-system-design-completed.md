# High-level System Design Completed

## What this means
The high-level system design defines the overall architecture of the solution: the major components, how they interact, where data lives, how the system integrates with existing infrastructure, and what the key technical trade-offs are. It provides enough detail to validate the approach without prescribing every implementation decision.

## Why it matters
Skipping high-level design and jumping into implementation is one of the most common causes of large-scale rework. A design review early in the process catches fundamental architectural mistakes when they're cheap to fix — before code has been written. It also creates a shared mental model across the team and enables parallel development of components.

## How to complete this
- Create a system diagram showing the major components (services, data stores, queues, external systems) and the data flows between them
- Document the key architectural decisions and their rationale (use ADRs for significant decisions)
- Identify the critical path through the system — where are performance and reliability most at risk?
- Review the design with the broader team and collect feedback before proceeding
- Document what is NOT included in this design (explicit out-of-scope is as important as what's in scope)

## Definition of done
- [ ] System diagram created showing components and data flows
- [ ] Key architectural decisions documented with rationale
- [ ] Design reviewed by at least two senior engineers or architects
- [ ] Critical path and risk areas identified
- [ ] Design is linked in the project documentation
