# 06-Cross-Guild Permission Conflicts

## Overview
This section explores how Discord handles **permissions across multiple servers (guilds)**, focusing on:
- Users with roles in multiple guilds
- Bot or webhook permissions spanning multiple servers
- Conflicts arising when the same account has different privileges across guilds

---

## Practical Objective
- Observe how actions in one guild affect or do not affect another
- Detect inconsistencies when the same user performs similar actions in multiple guilds
- Identify edge cases in cross-guild permission resolution

---

## Hands-On Actions
- Assign a user multiple roles across different guilds
- Attempt similar actions (e.g., message deletion, role assignment) in each guild
- Capture API/WebSocket responses and audit logs
- Minimize GUI usage; only trigger state changes as necessary

---

## Abuse & Failure Thinking
- Can cross-guild discrepancies be exploited to escalate privileges?
- Are there actions allowed in one guild that should be denied in another?
- How does Discord reconcile role precedence across servers for bots or integrations?

---

## Why This Matters
- Cross-guild permission gaps can lead to **multi-server exploitation**
- Critical for **bug bounty research and SaaS enforcement understanding**
- Lessons transfer to **cloud multi-tenant environments and distributed systems**

---

## What to Document
- User roles and permissions across guilds
- Observed vs expected action outcomes
- API/WebSocket requests and responses
- Audit log entries and discrepancies
- Mental models for cross-guild resolution
- Hypotheses for potential enforcement gaps

---

## Next Steps
- Systematically test actions for the same users across multiple guilds
- Record anomalies and failures in `02-failures.md`
- Refine mental models in `03-mental-models.md`
