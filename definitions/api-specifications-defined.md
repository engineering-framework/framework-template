# API Specifications Defined

## What this means
API specifications define the contract for every HTTP endpoint, RPC method, event schema, or other interface that will be created. Specs include method, path, request/response shapes, authentication requirements, error codes, and versioning strategy — before implementation begins.

## Why it matters
API contracts are among the hardest things to change post-launch because consumers (other services, clients, partners) depend on them. A spec-first approach allows multiple teams to develop against the same interface in parallel, enables early consumer feedback, and prevents the common pattern of discovering design problems only when integration begins.

## How to complete this
- Use an API specification format (OpenAPI/Swagger, AsyncAPI for events, or the team's standard format)
- Define all endpoints: method, path, request parameters, request body schema, response schemas, and error codes
- Specify authentication and authorization requirements per endpoint
- Document rate limits and any special headers
- Share the spec draft with consumer teams for feedback before implementation begins
- Version the API from the start — define the versioning strategy even if only v1 exists

## Definition of done
- [ ] All new endpoints/interfaces specified using the standard format
- [ ] Request/response schemas fully defined with types and constraints
- [ ] Authentication and authorization documented per endpoint
- [ ] Spec shared with and reviewed by at least one consumer team
- [ ] Versioning strategy defined
