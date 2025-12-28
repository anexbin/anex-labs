# 01-Role Hierarchy & Inheritance

## Overview
This section explores **how Discord evaluates roles across users and channels**, focusing on:
- The order of precedence in role enforcement
- Inherited permissions
- Implicit vs explicit grants or denials

---

## Practical Objective
- Observe how multiple roles assigned to a user interact
- Determine which role “wins” when conflicts exist
- Identify gaps or inconsistencies in enforcement

---

## Hands-On Actions
- Assign multiple roles with overlapping permissions
- Use API or bots to attempt actions allowed by only some roles
- Capture server responses, audit logs, and WebSocket events
- Trigger state changes using GUI minimally

---

## Abuse & Failure Thinking
- What assumptions does Discord make about role evaluation?
- Where might conflicts be exploitable?
- Can a lower-priority role override a higher-priority one in edge cases?

---

## Why This Matters
- Role hierarchy mistakes can lead to **privilege escalation**
- Understanding inheritance is critical for **bug bounty reporting**
- Concepts map to **OS permission models, cloud IAM, and SaaS enforcement logic**

---

## What to Document
- Assigned roles and their permissions
- Observed vs expected outcomes
- API/WebSocket requests and responses
- Audit log entries
- Mental models for role precedence
- Hypotheses about potential enforcement gaps

---

## Next Steps
- Systematically test all combinations of roles in a controlled server
- Record anomalies and failures in `02-failures.md`
- Refine mental models in `03-mental-models.md`
