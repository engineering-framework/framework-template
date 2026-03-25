# User Story — [Short Title]

| | |
|---|---|
| **Project** | [Project Name] |
| **Story ID** | [e.g., ENG-1234] |
| **Author** | [Name] |
| **Date** | [YYYY-MM-DD] |
| **Priority** | P0 / P1 / P2 |
| **Points** | [story points] |

---

## Story Summary

**As a** [type of user / persona],
**I want** [to perform some action / achieve some goal],
**so that** [I can achieve some benefit / outcome].

---

## Background & Context

*Why does this story exist? What problem does the user have today? Include any relevant research, user feedback, or data.*

[2-4 sentences describing the current state and why this story matters]

---

## Acceptance Criteria

*Use Given/When/Then format. Each criterion should be independently testable.*

### Scenario 1: [Happy path]
- **Given** [some initial context / state]
- **When** [an action is taken]
- **Then** [the expected outcome occurs]
- **And** [additional expected outcome]

### Scenario 2: [Error / edge case]
- **Given** [some initial context]
- **When** [an error condition occurs]
- **Then** [the system handles it gracefully by...]

### Scenario 3: [Additional scenario]
- **Given** [context]
- **When** [action]
- **Then** [outcome]

---

## Edge Cases

*List edge cases and how they should be handled. These inform test case design.*

- [ ] [e.g., User has no data — show empty state with CTA]
- [ ] [e.g., Request times out — show error with retry option]
- [ ] [e.g., Concurrent edits — last write wins / optimistic locking]
- [ ] [e.g., Pagination boundary — behavior at first/last page]

---

## Out of Scope

*Explicitly state what this story does NOT cover to prevent scope creep.*

- [e.g., Mobile optimization is handled in a separate story]
- [e.g., Admin-facing view is out of scope for this iteration]

---

## Technical Notes

*Implementation hints, constraints, or decisions relevant to engineering.*

- [e.g., Must use the existing `UserPreferences` service — do not create a new one]
- [e.g., API response must stay under 200ms at p95]
- [e.g., Feature is behind `new-feature-flag` flag — see feature flag strategy doc]

---

## Dependencies

- [ ] [e.g., Depends on ENG-1230: API endpoint for user preferences]
- [ ] [e.g., Requires design sign-off on empty state component]
