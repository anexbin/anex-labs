# 10-Observable Behavior vs Internal Enforcement

## Overview
This section explores the **discrepancy between what users see in the GUI and what is actually enforced server-side**, focusing on:
- GUI representation of roles, permissions, and actions
- Internal enforcement logic as observed via API/WebSocket
- Detecting mismatches between client display and backend behavior

---

## Practical Objective
- Identify actions that appear allowed in the GUI but are blocked server-side
- Detect permissions that appear denied but succeed when executed
- Capture discrepancies systematically for analysis

---

## Hands-On Actions
- Compare GUI-perceived permissions with actual API enforcement
- Trigger actions via bots, scripts, or API calls
- Capture responses, WebSocket events, and audit logs
- Document differences in behavior and enforcement

---

## Abuse & Failure Thinking
- Can GUI misrepresentation be exploited for privilege escalation or bypass?
- Are there patterns in how ephemeral vs persistent state affects GUI accuracy?
- How reliable are visual cues for enforcement assumptions?

---

## Why This Matters
- GUI vs backend discrepancies are a **common source of SaaS vulnerabilities**
- Understanding this gap is critical for **bug bounty research**
- Insights map to **desktop software, cloud dashboards, and distributed system monitoring**

---

## What to Document
- Observed GUI behavior vs actual server enforcement
- API/WebSocket requests and responses
- Audit log evidence
- Mental models for enforcement vs representation
- Hypotheses about potential gaps and inconsistencies

---

## Next Steps
- Systematically test GUI vs API/WebSocket behavior across all roles, channels, and bots
- Record anomalies in `02-failures.md`
- Refine mental models in `03-mental-models.md`
