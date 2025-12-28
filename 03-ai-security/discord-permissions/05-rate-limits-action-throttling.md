# 05-Rate Limits & Action Throttling

## Overview
This section examines how Discord **controls the frequency of actions** to prevent abuse, focusing on:
- Global vs endpoint-specific rate limits
- How the system throttles users, bots, and webhooks
- Observable behaviors when limits are exceeded

---

## Practical Objective
- Determine rate limits for various actions (messages, role changes, API requests)
- Observe system responses when limits are exceeded
- Capture throttling behavior via API, bots, and WebSocket events

---

## Hands-On Actions
- Automate rapid actions using API or bots
- Monitor responses and error codes when limits are hit
- Compare GUI feedback with actual server-side enforcement
- Test different roles or token types to see variations in throttling

---

## Abuse & Failure Thinking
- Can rate limits be bypassed or circumvented in edge cases?
- Are there actions that are inconsistently throttled?
- How does Discord handle simultaneous multi-channel actions?

---

## Why This Matters
- Rate-limiting flaws can enable **spam, DoS, or privilege escalation**
- Understanding throttling is essential for **bug bounty research**
- Patterns map to **API security, cloud service abuse, and distributed system defenses**

---

## What to Document
- Actions performed and timestamps
- Observed rate-limit responses and codes
- Differences between GUI and API/WebSocket feedback
- Mental models for throttling and enforcement
- Hypotheses for potential bypasses or enforcement gaps

---

## Next Steps
- Systematically test all relevant endpoints under heavy load
- Record anomalies and failures in `02-failures.md`
- Refine mental models in `03-mental-models.md`
