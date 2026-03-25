# Design Rationale and Trade-offs Documented

## What this means
Design rationale captures the reasoning behind technical choices — particularly the trade-offs accepted. Every design decision involves choosing one set of properties over another (e.g., consistency vs. availability, simplicity vs. flexibility, speed to ship vs. long-term maintainability). Documenting the reasoning preserves context for future engineers.

## Why it matters
Code communicates what was built; documentation communicates why it was built that way. When the "why" is missing, future engineers can't distinguish between "this was a deliberate choice" and "this is an accident waiting to be cleaned up." Well-documented rationale prevents well-intentioned refactors that break things that were working correctly for non-obvious reasons.

## How to complete this
- For each significant design choice, write a brief explanation of the trade-off considered
- Use ADRs for formal decisions; inline code comments or design doc sections for smaller choices
- Be explicit about what was sacrificed: "We chose X over Y, accepting the trade-off of Z"
- Document assumptions that were true when the decision was made — these help future maintainers evaluate whether the decision still holds
- Include links to any relevant benchmarks, research, or prior art that informed the decision

## Definition of done
- [ ] Trade-offs documented for all major design decisions
- [ ] Assumptions documented alongside each trade-off
- [ ] Documentation is accessible to engineers who weren't in the original design discussions
- [ ] Rationale is linked from the relevant code or component where practical
