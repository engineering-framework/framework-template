# Technical Debt Implications Assessed

## What this means
Technical debt implications assessment evaluates: (1) how much debt this initiative introduces (corners cut under deadline pressure), (2) how much existing debt this initiative will have to work around or build on top of, and (3) whether any existing debt needs to be addressed to safely deliver this initiative.

## Why it matters
Unassessed technical debt accumulates silently until it slows development to a crawl or causes production incidents. Initiatives built on top of fragile foundations often take 3x longer than estimated because of unexpected dependencies on poorly-designed legacy code. An honest assessment of debt implications allows the team to plan appropriately and make conscious decisions about accepting vs. addressing debt.

## How to complete this
- Identify the parts of the codebase this initiative depends on and assess their quality honestly
- Estimate how much debt this initiative itself will introduce, and why (e.g., "we're skipping X now to meet the deadline, creating debt")
- For debt being introduced: create tracking tickets immediately, don't let it become invisible
- For existing debt that creates risk: assess whether it needs to be addressed before this initiative can proceed safely
- Document the debt decisions explicitly — teams that hide debt from leadership eventually get surprised by the consequences

## Definition of done
- [ ] Existing debt affecting this initiative identified and assessed
- [ ] New debt being introduced documented with cleanup tickets created
- [ ] Debt that blocks safe delivery identified and addressed or risk accepted
- [ ] Debt decisions documented and shared with tech lead/EM
