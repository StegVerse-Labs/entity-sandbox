# Entity Sandbox for StegVerse Labs

## Overview

The **entity‑sandbox** repository is a dedicated test bed for exercising and validating AI entity designs, governance control laws and economic feedback mechanisms defined across the StegVerse ecosystem.  It provides a safe and isolated space to run controlled experiments that examine how entities behave under different governance, constraint and trust conditions using the GCAT/BCAT frameworks.  The sandbox is **not** intended for production workloads; instead it focuses on evaluation, monitoring and report generation.

This repository includes:

- A set of standard experiment definitions covering admissibility, stability, synchrony, recoverability and economic‑signal dynamics.
- A small suite of pre‑defined entity roles (Builder, Auditor, Ops, Economic, Theory) designed to interact with sandbox scenarios.
- Scenario definitions that set up baseline conditions, perturbations, collapse entry points, recovery paths and paired governance tests.
- Receipt schemas, validators and examples to ensure every state transition is captured and auditable.
- Report templates and scripts for automatically generating summaries of experiment runs.
- Documentation that explains the lab charter, the underlying testbed model, and metric definitions.

By keeping the experimental apparatus separate from runtime agents, the StegVerse project can iterate on theory without risking stability of production systems.  Public visibility of the sandbox’s logic aids transparency while keys, secrets and live control thresholds remain in private configuration files.

## Repository Visibility

This repository is designed to be **public by default** to encourage peer review and transparency around governance and control models.  No live signing keys or sensitive operational secrets should ever be committed here.  If a test relies on confidential parameters (e.g. actual governance thresholds or private validator logic), those values should live in separate private configuration repositories and be loaded at runtime.  For further guidance, see `docs/lab‑charter.md`.

## Directory Layout

```
experiments/           — Definitions and scaffolding for individual test classes.
  admissibility/       — Tests ensuring proposed actions remain within viability bounds.
  stability/           — Tests for Rigel equilibrium and Lyapunov‑style bounds.
  synchrony/           — Checks that entities remain independent and avoid hidden consensus.
  recoverability/      — Scenarios exploring collapse and recovery phases.
  economic‑signal/     — Simulations of token supply, demand and labour feedback loops.

entities/              — Archetypes for sandbox participants, each with minimal state and clear roles.
  builder/             — Assists with construction tasks and system model updates.
  auditor/             — Performs receipt validation and exposure analysis.
  ops/                 — Handles operational tasks such as scheduling and housekeeping.
  economic/            — Models supply/demand and pricing dynamics for labour markets.
  theory/              — Encodes research logic and proposed updates to control laws.

scenarios/             — High‑level experiment definitions combining entities with test cases.
  baseline/            — Stable starting positions used as control runs.
  perturbation/        — Sudden shocks to governance, constraints or trust.
  collapse‑entry/      — Situations that intentionally lead the system towards attractor basins.
  recovery‑path/       — Sequences designed to lift the system out of collapse basins.
  paired‑governance/   — Tests requiring both human and AI approvals.

receipts/              — Tools and examples for verifying that state transitions are properly chained.
  schemas/             — JSON or YAML schema definitions.
  validators/          — Scripts or modules to check receipt integrity.
  examples/            — Sample receipts illustrating correct chaining and auditing.

reports/               — Report templates and generated outputs from completed runs.
  templates/           — Markdown/HTML templates for summarising results.
  generated/           — Placeholders for automatically produced report files.

docs/                  — Lab charter, testbed model description and metric definitions.
  lab‑charter.md       — Explains the purpose, ethics and contribution guidelines for the sandbox.
  testbed‑model.md     — Details the underlying mathematical model and how experiments map to it.
  metric‑definitions.md— Defines common measures used across experiments.
```

## Contributing

1. Fork the repository and create a feature branch.
2. Develop your experiment or entity inside the appropriate folder.  Keep each experiment self contained.
3. Ensure that your code does not embed any sensitive secrets or production keys.  Configuration that must remain private should be loaded from environment variables or secrets during runtime.
4. Document your additions clearly and update the relevant `docs` if you introduce new metrics or control laws.
5. Run tests locally and provide sample receipts and reports for your experiment.
6. Open a pull request describing the motivation, design and expected outcomes of your contribution.

For questions or support, please contact the StegVerse Labs maintainers.
