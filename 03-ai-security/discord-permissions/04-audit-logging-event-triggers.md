# 04-Audit Logging & Event Triggers

## Overview
This section explores how Discord **records and signals actions** in the system, focusing on:
- Audit logs: what is captured, how, and when
- Event triggers: WebSocket events, API callbacks, and bots
- Understanding the difference between observable and hidden enforcement actions

---

## Practical Objective
- Observe what actions generate audit log entries
- Capture WebSocket events for role and permission changes
- Identify gaps where actions occur but are not logged or triggered

---

## Hands-On Actions
- Perform role assignments, permission changes, and message actions
- Monitor audit logs via API or bots
- Subscribe to WebSocket events for real-time state observation
- Compare GUI log display vs actual server-side logging

---

## Abuse & Failure Thinking
- Are there actions that bypass logging or trigger incomplete events?
- Can an attacker manipulate the system without leaving a trace?
- Are there delays or inconsistencies in event propagation?

---

## Why This Matters
- Audit logs are critical for **forensic analysis and bug bounty reporting**
- Understanding event triggers helps identify **race conditions and enforcement gaps**
- Lessons map to **cloud infrastructure monitoring, OS auditing, and distributed system observability**

---

## What to Document
- Actions performed and the resulting logs/events
- API/WebSocket requests and responses
- GUI vs terminal/API discrepancies
- Mental models for log generation and event handling
- Hypotheses about potential enforcement gaps

---

## Next Steps
- Systematically test audit logging for all permission changes and role actions
- Record anomalies and failures in `02-failures.md`
- Refine mental models in `03-mental-models.md`
