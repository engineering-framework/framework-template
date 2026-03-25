# Upstream Service Impacts Assessed

## What this means
Upstream services are the services that provide data or functionality to this initiative — services you call, queues you consume from, or databases you read from. Assessing upstream impacts means evaluating whether your usage will change in ways that affect those services' performance, behavior, or operational burden.

## Why it matters
Increased traffic to upstream services can trigger cascading failures — you hit their rate limits, exhaust their connection pools, or degrade their performance for other consumers. Upstream service owners deserve advance notice of significant changes in how their service will be used so they can prepare, adjust rate limits, or help design the integration correctly.

## How to complete this
- List all services that this initiative will call or depend on
- Estimate the expected request volume and compare to current usage
- Identify any new query patterns that might be expensive for upstream services (e.g., full table scans, unindexed queries)
- Communicate with upstream service owners about expected changes in usage
- Design appropriate buffering, caching, and backoff strategies to avoid overwhelming upstream services

## Definition of done
- [ ] All upstream dependencies identified with current and projected usage estimates
- [ ] Upstream service owners notified of significant changes
- [ ] Rate limit and backoff strategies designed for all upstream calls
- [ ] No upstream integration that could cause data correctness issues under load
