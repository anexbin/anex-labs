# 02-Channel-Specific Permission Overrides

## Overview
This section explores how **Discord resolves permission conflicts at the channel level**, focusing on:
- How server-level permissions interact with channel-specific overrides
- Explicit allow/deny settings per role or user
- Resolution order when multiple overrides exist

---

## Practical Objective
- Observe how channel overrides affect user actions
- Identify which overrides take precedence
- Detect any inconsistencies between GUI representation and actual enforcement

---

## Hands-On Actions
- Create multiple channels with different overrides for the same roles/users
- Use API or bots to attempt actions allowed in some channels but denied in others
- Capture server responses, WebSocket events, and audit logs
- Minimize GUI usage, only trigger state changes if needed

---

## Abuse & Failure Thinking
- What assumptions does Discord make about override precedence?
- Are there edge cases where a denial can be bypassed?
- Can overlapping overrides create exploitable gaps?

---

## Why This Matters
- Mismanaged overrides can lead to **unauthorized access or privilege escalation**
- Critical for **bug bounty research** and security reporting
- Lessons apply to **OS ACLs, cloud IAM policies, and other SaaS permission systems**

---

## What to Document
- Channel names and specific overrides
- Expected vs observed behavior
- API/WebSocket requests and responses
- Audit log entries
- Mental models for override resolution
- Hypotheses about potential enforcement gaps

---

## Next Steps
- Systematically test all combinations of overrides across channels
- Record anomalies and failures in `02-failures.md`
- Refine mental models in `03-mental-models.md`
