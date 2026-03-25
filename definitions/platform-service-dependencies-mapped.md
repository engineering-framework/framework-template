# Platform Service Dependencies Mapped

## What this means
Platform service dependencies are the shared internal services, libraries, or infrastructure components maintained by your platform or infrastructure team that this initiative will use or affect — things like authentication services, API gateways, service meshes, logging infrastructure, CI/CD pipelines, or shared databases.

## Why it matters
Platform services are shared by many teams. Changes to how they're used, or increased load placed on them, can have cascading effects across the organization. Mapping these dependencies ensures the platform team has visibility into upcoming changes, can help design the right integration, and can plan capacity for increased usage.

## How to complete this
- List all internal platform services this initiative will integrate with or depend on
- Identify any platform services that will be affected by increased load or behavioral changes
- Flag any platform limitations that might constrain the design (e.g., the API gateway doesn't support streaming)
- Engage the platform team early — especially for any integrations that require platform-side changes or new capabilities
- Clarify who is responsible for each dependency in an incident scenario

## Definition of done
- [ ] All internal platform service dependencies listed
- [ ] Platform team informed of new/changed usage patterns
- [ ] Platform limitations that affect the design documented
- [ ] Ownership and escalation path for each dependency confirmed
