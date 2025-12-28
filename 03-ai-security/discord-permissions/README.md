# Discord Permissions & Role Enforcement

## Overview
This repository documents a deep, hands-on exploration of **Discord's permission system**.  
The goal is NOT to learn Discord as a chat platform, but to **understand it as a real-world SaaS enforcement system**.  
We study how permissions are structured, enforced, and potentially bypassed, focusing on **observable behavior, failure modes, and system assumptions**.

---

## Purpose
- Understand **who can do what, when, and where** in Discord.  
- Identify **implicit assumptions** in distributed permission enforcement.  
- Detect **logic flaws and edge cases** in role and channel permission management.  
- Build **engineer-level mental models** applicable to bug bounty research and broader SaaS security.

---

## Research Goals
1. **Role Hierarchy & Inheritance**  
   - How roles are evaluated and inherited across users and channels.
2. **Channel-Specific Permission Overrides**  
   - How Discord resolves conflicts between server-level and channel-level permissions.
3. **Implicit vs Explicit Permissions**  
   - Understanding when a permission is granted or denied without explicit configuration.
4. **Audit Logging & Event Triggers**  
   - Capturing events to understand enforcement and triggers.
5. **Rate Limits & Action Throttling**  
   - Observing how Discord throttles actions to prevent abuse.
6. **Cross-Guild Permission Conflicts**  
   - Evaluating interactions across multiple servers.
7. **Bot & Webhook Permission Scoping**  
   - How automated agents are limited by the permission system.
8. **Ephemeral State vs Persistent Enforcement**  
   - Understanding what is temporary vs persisted in Discord’s enforcement.
9. **Failure Modes: Denial, Bypass, Escalation**  
   - Identifying potential abuse scenarios or enforcement gaps.
10. **Observable Behavior vs Internal Enforcement**  
    - Comparing GUI representation vs actual server-side enforcement.

---

## Methodology
- **Terminal-first investigation:** API, WebSocket, bots, and automation scripts are the primary tools.  
- **Minimal GUI usage:** GUI only for triggering state changes or observing client-only behavior (<5% of session time).  
- **Progressive depth:** Start with simple mental models, then harden to engineering-level precision.  
- **Documentation focus:** Requests, responses, logs, failure hypotheses, and mental models are captured for each subtopic.

---

## Why This Matters
- **SaaS Vulnerability Class:** Understanding distributed permission enforcement teaches general principles applicable to other platforms and services.  
- **Bug Bounty Impact:** Detecting logic flaws in permissions can lead to critical escalation and abuse vulnerabilities.  
- **Transferable Security Intuition:** Concepts learned here apply to operating systems, desktop software, cloud infrastructure, web apps, and AI/automation platforms.

---

## Folder Structure
```text
03-ai-security/discord-permissions/
├─ README.md
├─ 00-subtopics.md
├─ 01-hands-on.md
├─ 02-failures.md
├─ 03-mental-models.md
└─ 04-logs-and-requests.md
