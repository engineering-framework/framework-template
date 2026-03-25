# External Service Interfaces Documented

## What this means
External service interfaces are the integration points with systems outside your control — third-party APIs, partner systems, SaaS platforms, or other internal teams' services that you depend on but don't own. Documenting these interfaces includes authentication, API contracts, rate limits, SLAs, and error handling behavior.

## Why it matters
External dependencies are a primary source of production incidents. Services have outages, change their APIs without notice, throttle requests, and return unexpected errors. Documenting these interfaces upfront forces the team to design for failure (timeouts, retries, fallbacks) and establishes the monitoring required to detect when an external dependency is degraded.

## How to complete this
- List every external service this initiative will depend on
- Document the integration method (REST, SDK, webhook, file transfer, etc.) and authentication mechanism
- Note any known rate limits, quotas, or SLA constraints
- Design error handling: what happens when the service is unavailable or slow? Is a fallback needed?
- Identify if a sandbox or test environment is available for integration testing
- Establish monitoring: how will you know if an external service is degraded?

## Definition of done
- [ ] All external dependencies listed with integration method and auth
- [ ] Rate limits and SLA constraints documented
- [ ] Error handling strategy defined for each dependency (timeout, retry, fallback)
- [ ] Test/sandbox environments identified for integration testing
