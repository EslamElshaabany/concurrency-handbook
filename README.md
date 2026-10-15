# Concurrency Handbook

A learning handbook for understanding concurrency from the operating system upward, then applying the same concepts in Java, Go, Scala, and JavaScript.

Start with [Processes & Threads](01-fundamentals/01-processes-and-threads.md). Follow the [roadmap](ROADMAP.md) for the curriculum and use the [concept map](CONCEPT-MAP.md) to connect ideas.

## What you will learn

Explain what executes, who schedules it, what happens while it waits, which resources it shares, and what limits its progress. Use those questions to reason about concurrency, parallelism, multithreading, asynchronous programming, and execution models without treating them as synonyms.

The handbook connects these foundations to backend decisions: CPU work versus I/O waiting, shared mutable state, database connection pools, bounded work, cancellation, and backpressure.

## Architecture

| Layer | Location | Responsibility |
| --- | --- | --- |
| OS foundations | `01-fundamentals/` | Processes, threads, CPUs, scheduling, memory, blocking I/O, and I/O multiplexing |
| Core concepts | `02-core-concepts/` | Language-neutral explanations of concurrency and execution models, synchronization, memory models, async, coordination, and resource limits |
| Language mappings | `03-languages/` | Apply the concepts in `java.md`, `go.md`, `scala.md`, and `javascript.md` |
| Experiments | `04-labs/` | Independently runnable experiments with explicit predictions, observations, and limits |

**OS-first, concept-first, language-neutral** means the central lesson explains the mechanism before introducing a language API. Pseudocode makes assumptions explicit. OS-specific commands and runtime-specific behavior are labeled. Language chapters refer back to the concept instead of redefining it differently.

Java virtual threads, Go goroutines, Scala execution contexts, and JavaScript event loops belong in the language mappings after the scheduling and execution-model foundations. They are not interchangeable names for OS threads.

## How to use the handbook

1. Read the OS foundations in order.
2. Work through core concepts and predict behavior before reading exercise answers.
3. Use your preferred language mapping to connect the model to real APIs.
4. Run the relevant lab, compare predictions with observations, and explain any difference.

A successful lesson leaves you able to explain a mechanism, draw its execution model, predict a small example, and identify the conditions under which your prediction holds. Performance claims need measurements and an environment description.

## Current status

This Foundation Pack contains the repository overview, complete curriculum, concept map, first complete chapter, and reusable templates. Later chapters, language mappings, and runnable labs are **planned**, not implemented. Their paths appear as plain code in the roadmap so navigation never promises missing files.

Available now:

- [Processes & Threads](01-fundamentals/01-processes-and-threads.md)
- [Roadmap and scope](ROADMAP.md)
- [Concept map](CONCEPT-MAP.md)
- [Chapter template](templates/chapter-template.md)
- [Lab template](templates/lab-template.md)

## Scope of v1

The focus is concurrency within a single application and its local runtime/OS boundaries, including backend resource limits. Distributed concurrency, GPU/CUDA, actor systems, deep compiler optimization, advanced lock-free data structures, and framework tutorials are outside v1. A database may be an external dependency in a lab; distributed algorithms are not part of this curriculum.

## Writing and contribution conventions

Use the [chapter template](templates/chapter-template.md) and [lab template](templates/lab-template.md). Keep the agreed curriculum in [ROADMAP.md](ROADMAP.md). Explain terms before using them, distinguish guarantees from possible outcomes, and cite official documentation near the relevant explanation.

Use GitHub-flavored Markdown and Mermaid for diagrams. A chapter must include exercises and answer guidance. A lab must run independently, record its versions and resource limits, and document cleanup. Never use a single timing run as proof of a universal performance claim.
