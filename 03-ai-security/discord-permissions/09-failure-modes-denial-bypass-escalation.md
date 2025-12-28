# 09-Failure Modes: Denial, Bypass, Escalation

## Overview
This section examines **how Discord permissions can fail**, focusing on:
- Denial: actions incorrectly blocked
- Bypass: actions allowed despite restrictions
- Escalation: privilege increases beyond intended scope
- Understanding failure patterns and their causes

---

## Practical Objective
- Identify specific scenarios where denial, bypass, or escalation occurs
- Observe patterns in role, channel, and bot permission failures
- Capture reproducible examples for bug bounty-style reporting

---

## Hands-On Actions
- Combine multiple roles, channel overrides, and bot scopes
- Attempt actions at the edge of permission rules
- Monitor API/WebSocket responses and audit logs
- Record deviations from expected enforcement

---

## Abuse & Failure Thinking
- Which assumptions about permission evaluation fail?
- Can conflicts be exploited to escalate privileges?
- Are there gaps in bot or cross-guild enforcement that enable bypass?

---

## Why This Matters
- Understanding failure modes is crucial for **security testing and SaaS hardening**
- Provides insight for **bug bounty reports and real-world exploits**
- Lessons transfer to **OS access control, cloud IAM, and distributed systems**

---

## What to Document
- Specific actions causing denial, bypass, or escalation
- Observed vs expected outcomes
- API/WebSocket requests and responses
- Audit log evidence
- Mental models for failure modes
- Hypotheses for potential enforcement gaps

---

## Next Steps
- Systematically test combinations of roles, overrides, and bots for failures
- Record anomalies in `02-failures.md`
- Refine mental models in `03-mental-models.md`
