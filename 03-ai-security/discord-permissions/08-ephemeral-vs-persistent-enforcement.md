# 08-Ephemeral State vs Persistent Enforcement

## Overview
This section explores how Discord distinguishes between **temporary (ephemeral) state changes** and **persistent permission enforcement**, focusing on:
- Temporary overrides or effects in channels or sessions
- How persistent role/permission changes are stored
- Observing discrepancies between GUI state and actual server enforcement

---

## Practical Objective
- Identify which actions create temporary vs persistent state
- Test behavior after reconnections, bot restarts, or session expirations
- Observe how ephemeral states interact with role hierarchy and channel overrides

---

## Hands-On Actions
- Apply temporary permission changes via API or bots
- Trigger ephemeral effects (like temporary mutes or channel overrides)
- Capture server responses and WebSocket events
- Compare GUI representation vs persistent state in audit logs

---

## Abuse & Failure Thinking
- Can ephemeral states be exploited to bypass enforcement temporarily?
- Are there scenarios where persistent state fails to update correctly?
- How does Discord reconcile ephemeral changes with persistent enforcement?

---

## Why This Matters
- Misunderstanding ephemeral vs persistent states can lead to **privilege escalation or inconsistent enforcement**
- Critical for **bug bounty research and system security intuition**
- Lessons map to **OS session management, distributed system state handling, and SaaS ephemeral policies**

---

## What to Document
- Actions triggering ephemeral vs persistent states
- Observed vs expected enforcement
- API/WebSocket requests and responses
- Audit logs showing persistent changes
- Mental models for ephemeral vs persistent state
- Hypotheses about potential enforcement gaps

---

## Next Steps
- Systematically test ephemeral vs persistent actions across channels and roles
- Record anomalies and failures in `02-failures.md`
- Refine mental models in `03-mental-models.md`
