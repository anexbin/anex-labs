# Failure Pattern 04 — Burst Sensitivity & Threshold Collapse

## Pattern Summary
Systems tolerate sustained pressure better than short, intense bursts.
Brief spikes push internal mechanisms past thresholds,
triggering failures that outlast the burst itself.

Damage is caused by crossing thresholds — not duration.

---

## Observed Signals Across Labs
- Short load spikes caused immediate interaction freezes
- Processes failed during bursts but not under steady load
- OOM killer or scheduler actions triggered mid-spike
- Post-burst latency spikes and instability persisted
- Repeated bursts caused progressively faster collapse

---

## Burst vs Sustained Pressure
- Sustained load allows gradual adaptation
- Bursts overwhelm queues, caches, and schedulers instantly
- Threshold-based mechanisms activate abruptly
- Recovery paths lag far behind pressure onset

The system reacts too late and too hard.

---

## Timing & Trust Breakdown
- Monitoring averages hide short but lethal spikes
- Operators underestimate burst impact
- Health checks miss threshold crossings
- Recovery logic assumes bursts are harmless

Trust fails at millisecond scale.

---

## Why This Pattern Exists
- Internal buffers are finite and invisible
- Thresholds are hard-coded or heuristic-driven
- Burst handling prioritizes survival over stability
- Cleanup and rollback are deferred

Thresholds are crossed before humans can react.

---

## Relevance to Malware Behavior
- Malware may survive steady execution but fail on spikes
- Short-lived payloads trigger detection via collapse
- Burst behavior exposes timing-based fragility
- Watchdogs activate unexpectedly during spikes

Bursts reveal what persistence hides.

---

## Relevance to AI Pipelines
- Inference bursts violate latency guarantees
- Short data ingestion spikes stall entire pipelines
- Autoscaling reacts after thresholds are crossed
- Retries amplify burst damage

AI systems break on spikes, not averages.

---

## Relevance to Cloud-Scale Thinking
- Traffic surges cause regional instability
- Rate limits activate too late
- Cascading failures follow synchronized bursts
- Post-spike recovery hides long-term damage

Most outages begin with a spike.

---

## Operator Takeaway
Never evaluate systems by averages.

Watch for:
- Short spikes
- Threshold crossings
- Sudden scheduler or OOM reactions
- Instability *after* the burst ends

Bursts are how systems confess their real limits.

