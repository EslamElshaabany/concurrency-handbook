# Roadmap

[Home](README.md) · [Concept map](CONCEPT-MAP.md)

## Agreed structure and reading order

The four layers are fixed for v1: OS foundations, language-neutral concepts, language mappings, and runnable labs. Learn OS behavior before runtime abstractions. Backend applications and performance are threaded through examples and labs rather than added as competing top-level tracks.

Only the first chapter is complete in this Foundation Pack. Every unchecked entry below is planned. Code-formatted paths describe the intended structure, not existing navigation targets.

## 01-fundamentals

- [x] [01-processes-and-threads.md](01-fundamentals/01-processes-and-threads.md): processes, address spaces, threads, resource sharing, execution state, and observation.
- [ ] `01-fundamentals/02-cpu-and-scheduling.md`: cores, logical CPUs, runnable versus running, preemption, concurrency versus simultaneous execution.
- [ ] `01-fundamentals/03-memory-and-context-switching.md`: stacks, shared memory, virtual memory, execution context, and switching costs.
- [ ] `01-fundamentals/04-blocking-and-nonblocking-io.md`: waiting, readiness, blocking calls, and why nonblocking is not synonymous with asynchronous.
- [ ] `01-fundamentals/05-io-multiplexing.md`: readiness notification, event loops, and the relationship between many connections and few executing threads.

## CPU & Scheduling: planned coverage

The OS-course notes expand the existing `01-fundamentals/02-cpu-and-scheduling.md` lesson; they do not add a new architectural layer.

- **Selection and dispatch:** short-term scheduling chooses eligible execution work; dispatch gives it CPU time. Use “process” for a single-threaded teaching model and identify threads as the schedulable execution contexts where applicable. A ready queue is a conceptual model; real systems may use multiple per-CPU or policy-specific structures.
- **Criteria:** CPU utilization and throughput; turnaround from arrival to completion; waiting time spent ready but not running; response time from arrival to first service in the scheduling model. Distinguish that last metric from a backend request's end-to-end response latency.
- **FCFS:** arrival order, nonpreemptive behavior, and the convoy effect.
- **SJF / SRTF:** shortest next CPU burst versus shortest remaining burst; explain their idealized average-waiting benefits under explicit assumptions and why future burst lengths need estimation. Do not describe them as universally optimal schedulers.
- **Priority:** preemptive/nonpreemptive variants, starvation, and aging as a mitigation whose effectiveness depends on policy.
- **Round Robin:** time quantum, responsiveness, and context-switch overhead.
- **Multilevel queue:** classification into queues and the policy for scheduling across them.
- **Multilevel feedback queue (MLFQ):** movement between queues using observed behavior; explain boosts and starvation tradeoffs. Present it as one influential design, not “the most realistic” or the universal scheduler of modern OSes.
- **Multiprocessor scheduling:** load balancing, CPU affinity and migration tradeoffs, shared versus per-CPU queues, and symmetric (SMP) versus asymmetric (AMP) processor roles. Avoid reducing either term to a single load-balancing algorithm.

Use small timelines and compare policies on the same declared workload before introducing implementation-specific details. Scheduling asks who gets CPU time; the following memory chapter asks how addresses, memory ownership, and saved execution context relate.

## 02-core-concepts

- [ ] `02-core-concepts/01-concurrency-vs-parallelism.md`: overlapping progress, simultaneous execution, CPU-bound and I/O-bound workloads.
- [ ] `02-core-concepts/02-execution-and-scheduling-models.md`: thread-per-task, pools, runtime-managed tasks, event-driven and reactive models; identify who schedules what.
- [ ] `02-core-concepts/03-synchronization.md`: races, critical sections, locks, atomics, deadlocks, and choosing ownership boundaries.
- [ ] `02-core-concepts/04-memory-models.md`: visibility, ordering, atomicity, safe publication, and happens-before reasoning.
- [ ] `02-core-concepts/05-asynchronous-programming.md`: completion, futures/promises, callbacks, async/await, and blocking boundaries.
- [ ] `02-core-concepts/06-coordination-and-cancellation.md`: task lifetimes, joining, cancellation propagation, timeouts, and cleanup.
- [ ] `02-core-concepts/07-backpressure-and-resource-limits.md`: bounded queues, admission limits, connection pools, overload, and throughput/latency tradeoffs.

## 03-languages

Write these mappings after their prerequisites. Each compares the same workloads and refers back to core concepts. Language features require explicit version notes; avoid framework tutorials.

- [ ] `03-languages/java.md`: platform threads, executors, virtual threads and carriers, futures, event-driven and reactive approaches, and resource limits.
- [ ] `03-languages/go.md`: goroutines, runtime scheduling, channels, synchronization, contexts, and bounded concurrency.
- [ ] `03-languages/scala.md`: JVM threads, execution contexts, futures/promises, blocking boundaries, and cancellation limitations of the chosen APIs.
- [ ] `03-languages/javascript.md`: event loops, promises, async/await, workers, blocking callbacks, and browser versus Node.js differences.

## 04-labs

Every lab must be independently runnable. A lab may offer multiple language implementations, but implementations must preserve the workload and assumptions so the comparison is useful. Follow the [lab template](templates/lab-template.md).

- [ ] `04-labs/01-cpu-vs-io/`: contrast compute work with waiting; measure elapsed time and CPU use.
- [ ] `04-labs/02-race-conditions/`: expose a controlled lost-update schedule and compare safe designs.
- [ ] `04-labs/03-synchronization/`: protect an invariant and observe contention.
- [ ] `04-labs/04-scheduling-and-starvation/`: demonstrate progress limits and separate runtime scheduling from OS scheduling.
- [ ] `04-labs/05-connection-pool-saturation/`: separate task count, executing threads, checked-out connections, and in-flight queries.
- [ ] `04-labs/06-event-loop-blocking/`: observe how CPU-heavy callbacks delay unrelated work.
- [ ] `04-labs/07-cancellation-and-backpressure/`: bound admitted work, cancel tasks, and verify resource release.

## Foundation Pack acceptance criteria

- [x] Repository overview and reading instructions.
- [x] Agreed architecture, complete v1 curriculum, and explicit exclusions.
- [x] Concept map distinguishing related but different terms.
- [x] Complete Processes & Threads lesson with diagrams, worked examples, misconceptions, exercises, answer guidance, and official references.
- [x] [Reusable chapter template](templates/chapter-template.md).
- [x] [Reusable lab template](templates/lab-template.md).

## Out of scope for v1

Distributed concurrency and consensus, GPU/CUDA, actors, deep compiler optimization, advanced lock-free structures, and framework tutorials. New top-level tracks or changes to these boundaries require an explicit scope decision.

## Completion criteria for future work

A chapter follows the [chapter template](templates/chapter-template.md), labels its assumptions, cites official sources, and includes answer guidance. A language mapping separates runtime behavior from OS behavior and records relevant versions. A lab includes prerequisites, commands, predictions, observations, reproducible checks, and cleanup. Publish measured results with workload and environment details, not universal speedup promises.
