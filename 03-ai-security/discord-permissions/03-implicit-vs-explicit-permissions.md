# 03-Implicit vs Explicit Permissions

## Overview
This section investigates how Discord distinguishes between **explicitly granted/denied permissions** and **implicitly inherited or default permissions**, focusing on:
- How actions are allowed or denied without direct configuration
- Interaction between role hierarchy, channel overrides, and defaults
- Cases where implicit permissions can cause unexpected behavior

---

## Practical Objective
- Observe which permissions are inherited vs explicitly set
- Identify edge cases where implicit permissions override or conflict with explicit ones
- Detect discrepancies between GUI display and actual enforcement

---

## Hands-On Actions
- Assign users roles with overlapping explicit permissions
- Remove explicit permissions to rely on defaults/implicit grants
- Test actions via API or bots and capture responses
- Compare GUI representation with terminal/API observations

---

## Abuse & Failure Thinking
- What assumptions does Discord make about implicit permissions?
- Can implicit permissions lead to **unintended privilege escalation**?
- Are there scenarios where default allowances bypass explicit denials?

---

## Why This Matters
- Implicit permission flaws are a **common source of SaaS security issues**
- Understanding them is critical for **bug bounty reports**
- Knowledge is transferable to **OS access control, cloud IAM, and distributed systems**

---

## What to Document
- Users, roles, and their permissions (explicit vs implicit)
- Expected vs observed actions
- API/WebSocket requests and responses
- Audit log entries
- Mental models for permission resolution
- Hypotheses about potential enforcement gaps

---

## Next Steps
- Systematically test all combinations of explicit and implicit permissions
- Record anomalies and failures in `02-failures.md`
- Update mental models in `03-mental-models.md`
