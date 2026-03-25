# Alternative Approaches Considered and Rejected

## What this means
This item ensures the team has genuinely evaluated multiple approaches before committing to a design, and has documented why the alternatives were rejected. It's not enough to pick a good solution — you need to demonstrate the solution is better than the alternatives given the constraints.

## Why it matters
Documenting rejected alternatives prevents two failure modes: (1) revisiting already-considered options when new team members join or priorities change, wasting time re-evaluating dead ends; and (2) the "we only considered one approach" problem, where teams ship the first solution that came to mind without considering whether a better option exists. This item also creates accountability for the decision.

## How to complete this
- For each major design decision, enumerate at least 2 alternative approaches that were seriously considered
- Document the key reason each alternative was rejected — not just "we didn't like it" but specific technical, operational, or business reasons
- Be honest about the weaknesses of the chosen approach too — no solution is perfect
- Store in ADRs or design documents alongside the chosen approach
- If an alternative was rejected due to current constraints that might change, note this explicitly

## Definition of done
- [ ] At least 2 alternatives documented for each major design decision
- [ ] Specific reasons for rejection documented for each alternative
- [ ] Weaknesses of the chosen approach also acknowledged
- [ ] Documentation stored where the team can reference it
