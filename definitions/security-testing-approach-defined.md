# Security Testing Approach Defined

## What this means
Security testing encompasses the automated and manual techniques used to verify that security controls are correctly implemented and that known vulnerability classes are not present. The security testing approach defines what tests will be run, with what tools, at what stages of development, and who is responsible.

## Why it matters
Security requirements without security testing create a false sense of security. Automated security testing (SAST, dependency scanning, secret scanning) catches the most common vulnerability classes continuously without human effort. More targeted testing (penetration testing, security code review) provides depth for the highest-risk components. Defining the approach upfront ensures security testing is built into the process, not bolted on at the end.

## How to complete this
- Implement SAST (Static Application Security Testing) in the CI pipeline
- Configure dependency vulnerability scanning (e.g., Dependabot, Snyk, `npm audit`)
- Set up secret scanning to prevent credentials being committed to version control
- Define which components require manual security code review or penetration testing
- Schedule any external penetration testing well in advance of launch
- Define how security findings are triaged and remediated

## Definition of done
- [ ] SAST tool configured and running in CI
- [ ] Dependency scanning configured
- [ ] Secret scanning enabled on the repository
- [ ] Manual security review scope defined for high-risk components
- [ ] Security finding triage and remediation process documented
