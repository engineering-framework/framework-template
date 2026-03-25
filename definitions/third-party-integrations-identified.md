# Third-party Integrations Identified

## What this means
Third-party integrations are connections with external vendors, SaaS platforms, or partner APIs that are outside your organization's control. This item ensures all such integrations are identified, their contracts and terms reviewed, and the integration approach designed appropriately.

## Why it matters
Third-party dependencies introduce risk you can't fully control: API changes, rate limits, outages, pricing changes, and data residency concerns. Many compliance and security requirements impose obligations on how you use third-party services. Identifying these integrations early allows the team to design proper fallbacks, negotiate appropriate SLAs with vendors, and get legal/security reviews done before launch.

## How to complete this
- List every third-party service or API this initiative will integrate with
- For each, document: what it does, what data is shared with it, authentication mechanism, and rate limits
- Review data sharing implications — is any PII or sensitive data being sent to the vendor?
- Confirm vendor contracts are in place or initiate procurement if needed
- Design error handling and fallback behavior for each third-party dependency
- Get security team review for any new third-party data sharing

## Definition of done
- [ ] All third-party integrations listed with purpose and data shared
- [ ] Security and privacy review completed for each integration involving customer data
- [ ] Vendor contracts confirmed in place
- [ ] Error handling and fallback designed for each integration
