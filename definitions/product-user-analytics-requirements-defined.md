# Product User Analytics Requirements Defined

## What this means
Product analytics requirements define what user behavioral data needs to be captured to understand how the feature is being used, whether it's achieving its goals, and where users are struggling. This covers events to track, properties to capture, funnels to instrument, and which analytics tools to use.

## Why it matters
You can't improve what you don't measure. Without analytics instrumentation, product decisions after launch are based on assumptions rather than data. Getting analytics requirements defined before development means the instrumentation is built in from the start, not retrofitted — and the team agrees on what signals are needed to evaluate success before they're needed.

## How to complete this
- Work with the PM to identify the key user actions and funnels that need to be tracked
- Define the specific events to instrument (event names, trigger conditions, required properties)
- Ensure event naming follows your organization's taxonomy and naming conventions
- Identify any user segments or cohorts that need to be tracked separately
- Confirm the analytics tool and SDK being used and that it's already integrated
- Validate that PII is not included in analytics events, or that it's appropriately handled

## Definition of done
- [ ] Analytics events identified and specified with PM
- [ ] Event names and properties defined following the organization's taxonomy
- [ ] PII handling reviewed and confirmed compliant
- [ ] Analytics implementation plan included in development scope
