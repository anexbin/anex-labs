# Locks, Semaphores, and Mutexes

## Concept Summary
Locks, semaphores, and mutexes are **synchronization primitives** that enforce controlled access to shared resources in concurrent systems. They exist to prevent **race conditions, invariant violations, and inconsistent state** when multiple actors operate in parallel.

Key distinctions:
- **Lock / Mutex**: Ensures exclusive access to a resource by a single actor.
- **Semaphore**: Controls access to a limited number of identical resources.
- **Critical section enforcement**: These primitives allow atomic operations on shared state by coordinating entry and exit.

---

## Mental Model
**Analogy: Library Study Rooms**

- **Mutex (Lock)**: One student can use a study room at a time. Others wait until the room is free.  
- **Semaphore**: There are 3 identical study rooms. Up to 3 students can enter; others wait for a room to become free.  
- **Critical section**: The room itself, where the work happens safely.

**Key insight:**  
These primitives **translate human coordination rules** into system-level guarantees.

---

## Why This System Exists
Systems need these primitives because:
1. Multiple threads/processes share **finite resources** (memory, files, devices).
2. Simple atomic operations aren’t enough for complex sequences.
3. Concurrency is required for performance, responsiveness, and scalability.
4. They prevent subtle, **timing-dependent failures** that are hard to detect post-factum.

Without proper synchronization, **any system with shared state can fail silently under concurrency**.

---

## Core Components
1. **Mutex / Lock**
   - Binary: held or free
   - Guarantees exclusive access
   - Typically associated with critical sections

2. **Semaphore**
   - Counter-based
   - Limits concurrent access
   - Can signal other threads when resources are available

3. **Lock Acquisition & Release Protocols**
   - Ensure entry/exit correctness
   - Can be blocking or non-blocking

4. **Scheduler / Wait Queue**
   - Determines which actor enters next
   - Fairness and priority affect starvation potential

---

## Failure Modes
- **Deadlocks**: Circular waits if multiple actors hold locks while waiting for others.
- **Livelocks**: Repeated retries of acquisition without progress.
- **Starvation**: Some actors never acquire the lock due to unfair scheduling.
- **Priority inversion**: Low-priority actors hold locks needed by high-priority actors.

---

## Failure Chains
1. Actor A acquires Lock 1, Actor B acquires Lock 2.
2. Each waits for the other’s lock → Deadlock.
3. Scheduler cannot resolve circular dependency → system hangs.
4. Other dependent operations fail → cascading impact.

---

## Offensive & AI Red Team Relevance
- **Race & timing exploitation**: Attackers can manipulate lock acquisition order to bypass checks.
- **Denial-of-service vectors**: Holding locks or semaphores indefinitely can stall critical systems.
- **AI coordination**: Multi-agent systems can be disrupted if critical shared resources are locked improperly, causing unpredictable model behavior.

---

## Personal Insights
- Locks and semaphores are **tools, not guarantees**; misuse creates subtle failures.
- Critical for predicting concurrency-induced vulnerabilities.
- Understanding this separates a **tool user** from a **system thinker**.

---

## Safe Thought Exercise
1. Imagine 3 threads accessing 2 shared printers (semaphore count = 2).
2. Sketch the sequence of lock acquisitions and releases.
3. Identify possible deadlocks, starvation, or livelocks.
4. Modify the protocol to eliminate these failures.

---

## Open Questions
- How do modern OS kernels prevent priority inversion or deadlocks?
- What are trade-offs between spinlocks, blocking locks, and semaphores?
- How do distributed systems extend these primitives across nodes safely?

