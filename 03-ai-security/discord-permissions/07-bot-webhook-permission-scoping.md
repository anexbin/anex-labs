# 07-Bot & Webhook Permission Scoping

## Overview
This section investigates how Discord **limits the actions of bots and webhooks** based on roles and scopes, focusing on:
- Permissions granted via OAuth2 scopes
- Role-based restrictions applied to bots
- Channel-level and guild-level restrictions for automated agents

---

## Practical Objective
- Observe which actions a bot or webhook can perform with given scopes
- Test whether channel or role restrictions override bot privileges
- Detect inconsistencies between API enforcement and GUI representation

---

## Hands-On Actions
- Create bots with different OAuth2 scopes and assign roles
- Trigger actions such as message posting, role assignment, or channel management
- Capture API/WebSocket responses and audit logs
- Test multiple channels and guilds to see scope enforcement in practice

---

## Abuse & Failure Thinking
- Can bots exceed their intended privileges due to scope misconfigurations?
- Are there edge cases where channel overrides fail?
- How does Discord handle multiple bots with overlapping scopes?

---

## Why This Matters
- Bot and webhook misconfigurations are a **common source of SaaS vulnerabilities**
- Understanding scope enforcement is critical for **bug bounty research**
- Concepts transfer to **cloud service API keys, automation platforms, and SaaS integration security**

---

## What to Document
- Bot/webhook scopes and roles
- Observed vs expected behavior for actions
- API/WebSocket requests and responses
- Audit logs and discrepancies
- Mental models for automated agent enforcement
- Hypotheses about potential enforcement gaps

---

## Next Steps
- Systematically test bots with all relevant scopes across channels and guilds
- Record anomalies and failures in `02-failures.md`
- Update mental models in `03-mental-models.md`

