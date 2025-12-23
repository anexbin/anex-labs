# Lab 01 — Memory Pressure

**Date:** 2025-12-23  
**System:** Arch Linux, single-node, offline  
**Lab Focus:** Observing system behavior under high memory pressure  

---

## 1. Pressure Applied
- Continuously allocated large memory blocks in parallel processes.
- Simulated high memory demand without swapping to disk immediately.
- Stress tested with both predictable (fixed-size allocations) and unpredictable (randomized) allocations.

## 2. Observations
- System slowed down progressively as memory usage increased.
- OOM killer invoked selectively; some processes survived longer than expected.
- Swap usage increased, but latency spikes occurred before swap fully engaged.
- GUI and shell responsiveness degraded unevenly; some apps froze while others continued.
- Backpressure manifested as sudden blocking of memory allocations rather than gradual slowdown.

## 3. Surprises
- Processes allocated memory but sometimes didn't immediately trigger OOM or swap usage.
- Fragmentation led to failure even when total free memory appeared sufficient.
- Timing of failures was non-deterministic: repeated the same allocation pattern and observed different processes killed each time.
- Kernel heuristics seemed to prioritize system responsiveness over fairness to all processes.

## 4. Fragile Points
- Large allocations in quick succession caused immediate unresponsiveness.
- Memory-mapped files and lazy allocations amplified instability.
- Shell and GUI commands became unresponsive even though swap was technically available.

## 5. Broken Assumptions
- Assumed that swap would prevent any immediate failure — not always true.
- Assumed that memory allocation order was deterministic — kernel scheduling and lazy allocation broke this.
- Assumed system load would degrade uniformly — in reality, fragility appeared in specific subsystems first.

---

**Operator Notes:**  
- Memory pressure exposes non-uniform fragility across subsystems.  
- Timing and lazy allocation patterns are critical — two identical allocations may behave differently.  
- These behaviors mirror real-world scenarios in AI pipelines and malware running on constrained systems.

