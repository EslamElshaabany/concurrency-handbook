# NN. Chapter Title

<!-- Author instructions: replace every brace-delimited field and delete these comments before publishing. Keep the nine main sections. Adjust navigation links for the new chapter location; link only to existing files. -->

[Home](../README.md) · [Roadmap](../ROADMAP.md)

**Layer:** {OS foundation or core concept}

**Estimated study time:** {time including exercises}

**Status:** {draft or complete}

## Learning Objectives

By the end, you can:

- {Explain a mechanism using concrete terms.}
- {Predict a small example under explicit assumptions.}
- {Identify a limit or failure mode and justify a response.}

## Prerequisites

{Required knowledge and links to existing prerequisite chapters. Mark optional material clearly.}

## The Problem

{A concrete situation that motivates the concept. Ask a question the lesson will answer. State the workload and environment assumptions.}

## How It Works

{Define terms, then explain the mechanism in causal order. Separate OS guarantees, runtime behavior, and application policy. Label platform/version-dependent behavior and cite official sources near claims.}

{Explain costs and limits. Distinguish what is possible from what is guaranteed.}

## Visual Model

{Add a focused Mermaid diagram. Name what the nodes and arrows mean. Include what the diagram deliberately simplifies. Prefer several small diagrams over one crowded diagram.}

## Practical Examples

### Worked example

{Use language-neutral pseudocode first. Declare whether spawn creates an OS thread or runtime task, whether state is shared, whether operations are atomic, and whether join establishes completion/visibility.}

{Walk through a specific valid schedule and explain why other schedules may be valid. Label pseudocode as non-executable.}

### Observation or application

{Give an OS observation or backend scenario. Label OS/tool requirements. If code is runnable, include complete commands, expected invariants, variable observations, cleanup, and relevant versions. Put substantial runnable experiments in 04-labs.}

## Common Misconceptions

| Claim | Correction | Reason or counterexample |
| --- | --- | --- |
| {Common mistaken claim} | {Accurate model} | {Concrete explanation} |

## Exercises

### Conceptual Questions

1. {Explain the mechanism in your own words.}
2. {Choose between two designs and justify the tradeoff.}

### Predict the Output

{Provide pseudocode and assumptions. Ask for guaranteed properties, possible outcomes, and an impossible outcome. Do not invent deterministic output for an unspecified data race.}

### Hands-on Tasks

1. {Observe a small reproducible behavior.}
2. {Change one factor, predict the effect, and compare evidence.}

### Answer Guidance

<details>
<summary>Open after attempting the exercises</summary>

{Explain the reasoning for every exercise. For observations, give expected invariants and acceptable variation instead of fixed machine-specific numbers.}

</details>

## References

- {Official source title and URL}: {Which mechanism or guarantee it supports.}
- {Versioned runtime or OS documentation}: {Relevant assumptions and limitations.}

{End with a short connection to the next concept. Link only if the target exists; otherwise point to its roadmap entry.}
