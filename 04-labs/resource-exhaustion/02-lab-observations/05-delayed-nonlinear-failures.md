# Lab 05 — Delayed & Non-Linear Failures

**Date:** 2025-12-23  
**System:** Arch Linux, single-node, offline  
**Lab Focus:** Observing delayed and non-linear failure behavior under resource backpressure  

---

## 1. Pressure Applied
- Applied combined memory, CPU, and I/O stress in bursts and sustained waves.
- Introduced intermittent load spikes to observe delayed system responses.
- Monitored process responsiveness, system logs, and latency over extended periods without intervention.

## 2. Observations
- Failures did not always occur immediately; some processes ran seemingly fine, then suddenly stalled.
- Latency spikes appeared suddenly after periods of apparent stability.
- OOM killer and scheduling adjustments occurred after a delay, sometimes long after the actual pressure spike.
- System subsystems exhibited cascading delays — memory, CPU, and I/O interacted in unexpected ways.
- GUI, shells, and background daemons experienced intermittent stalls even when load decreased.

## 3. Surprises
- Two identical stress runs produced different timing and order of failures.
- Some low-priority processes survived multiple bursts while higher-priority tasks failed.
- Kernel heuristics triggered reactions unpredictably, amplifying latent fragility.
- Swap and cache mechanisms masked pressure initially but then amplified failures once thresholds were crossed.

## 4. Fragile Points
- Timing-sensitive scripts and real-time monitoring processes were most fragile.
- Background logging and monitoring daemons lagged unpredictably.
- GUI responsiveness and shell input latency fluctuated sharply, even under moderate pressure.

## 5. Broken Assumptions
- Assumed failures would be immediate and proportional to load — actually non-linear and delayed.
- Assumed system state could be predicted based on current metrics — latent pressure made predictions unreliable.
- Assumed combined resource pressure would behave additively — observed emergent effects and cascading failures.

---

**Operator Notes:**  
- Delayed and non-linear failures are key to understanding AI pipeline bottlenecks, malware persistence, and system resilience.  
- Timing, latent fragility, and backpressure propagation are critical for elite operator thinking.  
- Systems can appear stable while silently accumulating risk — this mirrors real-world operational hazards.

