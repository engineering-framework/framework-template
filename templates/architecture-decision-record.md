# ADR-[NNN]: [Short Decision Title]

| | |
|---|---|
| **ADR Number** | ADR-[NNN] |
| **Project** | [Project Name] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Status** | Proposed / Accepted / Deprecated / Superseded by [ADR-NNN] |
| **Deciders** | [Names of people who made the decision] |

---

## Context

*Describe the situation and the forces at play that make this decision necessary. What is the problem? What constraints exist? What are the requirements driving this decision?*

[2-4 paragraphs of context. Be specific about the technical and business constraints. Mention relevant scale, team size, existing systems, or deadlines that shaped the options available.]

---

## Decision Drivers

*The most important factors that should influence the decision:*

- [e.g., Must integrate with existing auth system without a rewrite]
- [e.g., Team has limited experience with distributed systems — operational simplicity is critical]
- [e.g., Must support 10x current load within 6 months]
- [e.g., Must be deployable by a team of 2 without dedicated infrastructure expertise]

---

## Considered Options

1. [Option A — short name]
2. [Option B — short name]
3. [Option C — short name]

---

## Decision Outcome

**Chosen option:** [Option X], because [brief justification — 1-2 sentences].

**Consequences:**
- **Good:** [positive outcome of this decision]
- **Good:** [positive outcome]
- **Bad:** [accepted trade-off or downside]
- **Neutral:** [something that will change as a result, neither good nor bad]

---

## Option Analysis

### Option A: [Name]

**Description:** [Describe the option in enough detail that a new team member understands it]

**Pros:**
- [pro 1]
- [pro 2]

**Cons:**
- [con 1]
- [con 2]

---

### Option B: [Name]

**Description:** [Describe the option]

**Pros:**
- [pro 1]
- [pro 2]

**Cons:**
- [con 1]
- [con 2]

---

### Option C: [Name]

**Description:** [Describe the option]

**Pros:**
- [pro 1]

**Cons:**
- [con 1]
- [con 2]

---

## Implementation Notes

*Any important details about how to implement the chosen option:*

- [e.g., This requires updating the config schema — see PR #123]
- [e.g., Gradual rollout recommended — do not switch all traffic at once]

---

## Links & References

- [Link to design doc, RFC, or related ticket]
- [Link to prior art or external reference]
- [Link to any superseded ADR]
