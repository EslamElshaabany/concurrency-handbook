# Lab NN: Title

<!-- Replace every brace-delimited field and delete comments before publishing. A lab must run independently; multiple language implementations are optional. -->

[Home](../README.md) · [Roadmap](../ROADMAP.md)

## Question and Learning Goals

{One testable question and the concepts the experiment exposes. Link to existing prerequisite chapters.}

## Hypothesis and Predictions

{Predict observable behavior before running. Distinguish correctness invariants from performance expectations. State what evidence would contradict your hypothesis.}

## Prerequisites and Environment

| Requirement | Value |
| --- | --- |
| OS and architecture | {supported environments} |
| Runtime/compiler | {supported version and version command} |
| Tools | {required tools and versions} |
| Hardware and limits | {logical CPUs, affinity/quota, RAM, task/thread limits} |
| External services | {none, or exact local service setup and cleanup} |

{Record actual environment values with results. Describe installation without relying on an earlier lab. Use local dependencies where possible; state any network access and ports required.}

## Files and Independent Setup

{List all code/config files supplied by this lab and their purpose. Give commands from a fresh clone, including the exact working directory and dependency setup. Avoid missing paths and unexplained placeholders in the published lab.}

## Workload and Execution Model

{Define input size, task count, worker count, queue capacity, connection limits, timeout, and duration. Explain who schedules work and what is shared. Keep workloads comparable between language variants.}

## Run

{Provide complete copyable commands for a baseline and one controlled variation. Include a bounded duration and a stopping method. Use resource limits that are safe on a developer machine.}

## Observe

{Capture elapsed time, CPU time/use, throughput and latency where relevant, active task/thread counts, waits, queue depth, and resource utilization. Identify which metrics the tools actually measure.}

| Run | Changed factor | Prediction | Observation | Explanation |
| --- | --- | --- | --- | --- |
| Baseline | {none} | {expected behavior} | {record result} | {reason} |
| Variation | {one factor} | {expected change} | {record result} | {reason} |

{Include a sample result labeled illustrative, with units. Separate warmup from measurement when relevant. Repeat timing runs enough to describe variation; document the method rather than choosing only the best run.}

## Correctness Checks

{Provide an actual invariant, expected completion count, or bounded-resource assertion. State how failure is detected. A race demonstration may need a controlled schedule; one successful run does not prove race freedom.}

## Explain the Result

{Relate observations to the concept. Discuss confounders such as JIT warmup, cache state, logging, GC, OS scheduling, CPU quotas, and external capacity only where relevant. Do not infer general speedups from one environment.}

## Exercises

1. {Change one parameter and predict the effect.}
2. {Explain where the bottleneck moved.}
3. {Choose a design for a concrete backend constraint.}

## Answer Guidance

<details>
<summary>Open after completing the lab</summary>

{Explain each exercise, expected invariants, and machine-dependent variation.}

</details>

## Cleanup and Troubleshooting

{Provide exact commands to stop only lab-owned processes/services and remove lab-generated resources. Explain timeouts, unavailable tools, port conflicts, and relevant permissions. Verify resources are released after cancellation/failure.}

## References

- {Official API/OS/runtime documentation and relevant versions.}
- {Related handbook chapters that already exist.}
