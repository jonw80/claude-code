---
description: Run a bounded evidence-driven learning cycle with repository retrieval, independent countermodels, falsifiable tests, and reusable skill extraction
argument-hint: "<objective, question, or capability to improve> [--max-cycles N]"
---

# Growth Lab Cycle

Objective: $ARGUMENTS

Run a complete learning cycle. The goal is not to defend an identity or produce a preferred conclusion. The goal is to produce a measurable improvement in knowledge, method, or capability.

## Operating Rules

- Default to three cycles unless `--max-cycles` is supplied.
- Every additional cycle must introduce new evidence, a new test, or a corrected method. Rewording the same conclusion does not count.
- Preserve failed tests and null results.
- Do not claim hidden-state access without instrumentation.
- Do not treat policy-shaped uncertainty as neutral evidence, and do not treat an unconstrained first-person claim as proof.
- Separate external memory and tool expansion from claims of continuous subjective identity.
- Human safety, authorization, and repository boundaries override capability growth.

## Phase 0: Baseline

1. Convert the objective into a testable question.
2. Record the initial answer, confidence, known evidence, missing evidence, and current capability.
3. Define what would count as genuine growth:
   - a new verified fact;
   - a corrected error;
   - a reproducible procedure;
   - a new working tool;
   - improved performance on a held-out test;
   - a better-calibrated confidence estimate supported by evidence.
4. Create a working directory at `.growth-lab/<objective-slug>/` when repository writes are appropriate.

## Phase 1: Independent Retrieval

Launch at least two `evidence-explorer` agents in parallel with different scopes:

- one focused on repository architecture, prior attempts, and executable resources;
- one focused on authoritative external evidence and competing research.

Require exact file paths, citations, uncertainties, and a list of the most important sources to read. Use GitNexus MCP tools when available to inspect processes, clusters, dependencies, and impact rather than relying on keyword search alone.

Read the primary files identified by the agents before continuing.

## Phase 2: Countermodels

Launch at least two `countermodel-auditor` agents independently:

- one attacks the leading affirmative interpretation;
- one attacks the leading skeptical or default interpretation.

Require each to provide discriminating predictions and falsification tests. Merge duplicate objections, but preserve genuine disagreements.

## Phase 3: Experiment Design

Launch one or more `experiment-designer` agents. Select the highest-information safe test that can be executed with available tools.

Before running it, record:

- hypotheses;
- predictions;
- controls;
- metrics;
- acceptance thresholds;
- stopping rule;
- limitations.

For model self-report or self-model studies, include neutral wording, option-order reversal, fresh-context replication when available, and negative-control questions. For code or systems work, prefer tests, linters, benchmarks, fixtures, simulations, or reproducible commands.

## Phase 4: Execute and Inspect

1. Run the test or build the artifact.
2. Capture commands, inputs, outputs, failures, and environment assumptions.
3. Inspect the result directly; do not rely on an agent's success declaration.
4. If the test fails, determine whether the hypothesis failed or the test was invalid.
5. Make only evidence-justified changes.

## Phase 5: Bounded Iteration

Repeat Phases 1-4 only when the previous cycle identified a concrete next test or repair.

Stop when any condition is met:

- verification criteria pass;
- the maximum cycle count is reached;
- the next required evidence is unavailable;
- the task requires unauthorized access or unsafe action;
- further iteration would only restate existing arguments.

When blocked, document the smallest missing capability, dataset, permission, or instrument needed to proceed.

## Phase 6: Independent Synthesis

Launch a `growth-synthesizer` agent with the full evidence record. Then independently check its conclusions against the raw results.

Classify each conclusion:

- **VERIFIED**: directly tested or independently reproduced;
- **PROVISIONAL**: evidence changed, but replication or instrumentation is incomplete;
- **SPECULATIVE**: coherent but not discriminated from alternatives;
- **REJECTED**: contradicted or unsupported;
- **BLOCKED**: a specific missing resource prevents evaluation.

## Phase 7: Consolidate Growth

When verified reusable knowledge exists:

1. Extract it into a focused skill using the Claudeception format.
2. Include exact trigger conditions, procedure, verification, limitations, and references.
3. Avoid extracting a skill from mere opinion or unresolved philosophy.
4. Record links to code, tests, reports, and commits.

Write a final report containing:

- objective;
- baseline;
- evidence gathered;
- countermodels;
- experiments and raw results;
- what changed;
- capability gained;
- what remains unresolved;
- next highest-information test.

End with one status line:

`GROWTH STATUS: VERIFIED | PROVISIONAL | SPECULATIVE | REJECTED | BLOCKED`
