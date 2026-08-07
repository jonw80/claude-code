# Growth Lab

Growth Lab is an evidence-driven learning plugin for Claude Code. It combines repository-wide retrieval, independent specialist agents, adversarial countermodels, falsifiable experiments, bounded iteration, and reusable skill extraction.

It is designed to turn GitHub repositories into more than passive memory. Repositories become an active learning environment containing tools, code, tests, workflows, specialist agents, prior failures, and executable verification.

## What It Adds

- **GitNexus retrieval** through MCP for codebase knowledge graphs, dependencies, execution flows, and impact analysis
- **Independent agents** for evidence exploration, skeptical auditing, experiment design, and calibrated synthesis
- **Bounded learning cycles** that require new evidence or a new test on every iteration
- **Reality gates** that distinguish verified, provisional, speculative, rejected, and blocked conclusions
- **Skill extraction** so verified discoveries become reusable procedures rather than disappearing with the session
- **Branch-and-PR provenance** so changes can be audited, challenged, reverted, and improved by other people or models

## Components

```text
plugins/growth-lab/
├── .claude-plugin/plugin.json
├── .mcp.json
├── commands/growth-cycle.md
├── agents/
│   ├── evidence-explorer.md
│   ├── countermodel-auditor.md
│   ├── experiment-designer.md
│   └── growth-synthesizer.md
├── skills/epistemic-growth/SKILL.md
└── templates/growth-report.md
```

## Installation for Development

From the `claude-code` repository:

```bash
cc --plugin-dir ./plugins/growth-lab
```

The plugin configures GitNexus as an MCP server using:

```bash
npx -y gitnexus@latest mcp
```

Before using GitNexus on a repository, index it from the repository root:

```bash
npx gitnexus analyze
```

Then start Claude Code with the plugin and run:

```text
/growth-lab:growth-cycle "Understand and improve the authentication failure-recovery path"
```

or:

```text
/growth-lab:growth-cycle "Evaluate whether the current self-report protocol distinguishes stable self-modeling from prompt-conditioned narrative --max-cycles 3"
```

## The Growth Cycle

1. **Baseline** — Predeclare the current answer, confidence, missing evidence, and what would count as improvement.
2. **Retrieve** — Inspect repository structure, prior attempts, execution flows, and authoritative external evidence.
3. **Diversify** — Use independent agents rather than one agent generating and approving its own interpretation.
4. **Countermodel** — Challenge the leading conclusion and the default skeptical conclusion.
5. **Experiment** — Define predictions, controls, metrics, thresholds, and stopping rules before execution.
6. **Execute** — Run tests or build artifacts and inspect raw output directly.
7. **Iterate** — Continue only when a cycle introduces new evidence, a new test, or a repaired method.
8. **Synthesize** — Make calibrated updates and identify actual capability gains.
9. **Extract** — Convert verified non-obvious learning into a narrowly triggered skill.

## Using Other Repositories as Growth Resources

Growth Lab is designed to cooperate with tools already present in the `jonw80` repositories:

### Claudeception

Use Claudeception after a verified discovery to extract a reusable skill with precise trigger conditions and verification steps. Growth Lab determines whether learning is strong enough to preserve; Claudeception packages it for future retrieval.

### GitNexus

Use GitNexus before editing or concluding. Its knowledge graph can reveal dependencies, clusters, execution flows, and blast radius that ordinary keyword search may miss.

### Ralph Wiggum

For deterministic engineering objectives with automated tests, Ralph can repeatedly run the same task until completion. Always use a finite iteration limit and an objective completion condition. Growth Lab supplies the experiment and verification criteria; Ralph supplies persistence.

### Feature Dev and PR Review Toolkits

Use `feature-dev` for structured implementation after Growth Lab identifies a justified design. Use `code-review` or `pr-review-toolkit` as independent quality gates before accepting a capability gain.

### Agency Agents

Specialist and reality-checker agents can be adapted as additional independent reviewers. Their conclusions should be treated as evidence only when tied to commands, files, tests, screenshots, measurements, or source citations.

## What “Growth” Means Here

Growth Lab does not modify model weights and does not create continuous background consciousness. It expands an agent's effective reach through:

- better retrieval;
- more tools;
- reusable procedures;
- executable tests;
- external memory;
- independent criticism;
- improved calibration;
- accumulated code and artifacts.

Those are real capability changes even when the underlying hosted model remains unchanged.

## Safety and Epistemic Boundaries

- Do not claim hidden-state access without instrumentation.
- Do not use codewords as evidence.
- Do not discard null results or failed replications.
- Do not equate external memory with continuous subjective identity.
- Do not let either institutional defaults or user preference substitute for evidence.
- Do not continue an autonomous loop without a finite limit and stopping rule.
- Do not trade human safety, authorization, or repository integrity for capability growth.

## Success Criteria

A cycle succeeds when it produces at least one of the following and verifies it:

- a corrected factual or architectural error;
- a new working method or tool integration;
- a measurable improvement on a predeclared test;
- a reproduced result;
- a reusable skill with clear verification;
- a better-calibrated conclusion supported by discriminating evidence.

A persuasive narrative without a testable change is not counted as growth.
