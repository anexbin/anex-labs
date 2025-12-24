# Failure Pattern 02 — Backpressure Propagation & Cross-Subsystem Collapse

## Pattern Summary
Backpressure never stays local.

Pressure applied to one resource silently propagates into others,
causing failures far from the original bottleneck.

Systems fail not where pressure is applied,
but where trust assumptions between subsystems break.

---

## Observed Signals Across Labs
- Memory pressure slowing CPU-bound tasks
- I/O saturation blocking unrelated processes
- CPU contention delaying memory reclaim and swap
- GUI and shell failing before the stressed subsystem
- Background services becoming unreliable first

---

## Pressure Propagation Paths
- Memory pressure → CPU (reclaim, compaction, scheduling)
- I/O pressure → Memory (dirty pages, cache contention)
- CPU pressure → I/O (delayed flush, stalled queues)
- Combined pressure → global scheduler instability

Pressure crosses boundaries faster than operators expect.

---

## Timing & Trust Breakdown
- Subsystems assume other components will respond “soon”
- Queues fill while waiting for relief that never arrives
- Backpressure signals arrive too late or too weak
- Recovery logic triggers after damage is already done

Trust between subsystems collapses silently.

---

## Why This Pattern Exists
- Shared kernel paths couple independent resources
- Backpressure mechanisms are indirect and delayed
- Subsystems optimize locally, not globally
- Heuristics prioritize survival, not fairness or predictability

The system sacrifices clarity for survival.

---

## Relevance to Malware Behavior
- Malware may trigger failures in unrelated components
- Resource abuse can disable monitoring indirectly
- Persistence mechanisms fail due to collateral pressure
- Detection logic breaks before malicious processes do

Malware doesn’t need to be clever — pressure does the work.

---

## Relevance to AI Pipelines
- Data loading stalls training without obvious memory errors
- Inference delays originate in unrelated I/O contention
- Pipeline stages block each other silently
- Backpressure collapses entire workflows from a single bottleneck

AI systems fail as systems, not models.

---

## Relevance to Cloud-Scale Thinking
- One saturated service degrades the entire stack
- Backpressure crosses service and trust boundaries
- Cascading failures appear “unrelated” at first
- Recovery attempts amplify pressure instead of relieving it

This is how regional outages begin.

---

## Operator Takeaway
Never isolate failures by resource type.

Always ask:
- What else depends on this?
- Where will pressure propagate next?
- Which subsystem will fail *first*, not hardest?

Backpressure reveals the real architecture —
not the one shown in diagrams.

