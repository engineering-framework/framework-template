# Security Requirements Identified

## What this means
Security requirements are the specific controls, behaviors, and constraints the system must implement to protect assets and users. These are derived from the threat model, organizational security policies, and applicable compliance frameworks — not assumed to be covered by default.

## Why it matters
Security requirements that aren't specified won't be implemented. Engineers who aren't given explicit security requirements make assumptions that may be wrong. Identifying security requirements early ensures they're included in the technical design and development scope, rather than discovered as gaps during a security review that requires rework.

## How to complete this
- Review the threat model to identify the controls required to mitigate each threat
- Check applicable compliance frameworks for mandatory controls (SOC 2, GDPR, HIPAA, PCI-DSS)
- Define authentication and authorization requirements for each operation
- Specify data encryption requirements (in transit and at rest)
- Document input validation and injection prevention requirements
- Identify audit logging requirements for sensitive operations

## Definition of done
- [ ] Security requirements documented based on threat model analysis
- [ ] Compliance-mandated controls identified and included
- [ ] Authentication/authorization requirements specified per operation
- [ ] Data handling (encryption, retention, deletion) requirements documented
- [ ] Security requirements included in the development scope and acceptance criteria
