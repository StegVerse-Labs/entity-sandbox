# StegVerse Entity Sandbox Charter

## Purpose

The entity sandbox exists to provide a safe environment for experimentation with AI entities, control laws, governance rules and economic feedback mechanisms defined by the StegVerse project.  Its objectives are:

* **Validate theoretical models** in a controlled setting before deployment to production.
* **Generate auditable histories** of every state transition, supporting transparency and reproducibility.
* **Detect synchrony, collusion or instability** in autonomous entities before those behaviours can impact live systems.
* **Enable community review** of governance and constraint designs, aligning with StegVerse’s commitment to open science.

## Principles

1. **Safety first** – all experiments must respect the Viability Kernel and Admissibility Bounds defined by GCAT/BCAT.  The sandbox must not execute unbounded or autonomous code that can mutate systems outside its scope.
2. **Transparency** – experiment logic, control laws, metrics and results should be public wherever possible.  Sensitive material (e.g. keys, thresholds) must be abstracted into private config.
3. **Modularity** – each experiment should be self‑contained and not depend on hidden global state.  Entities should have explicit roles and bounded capabilities.
4. **Auditability** – every state transition must produce a receipt with enough information to reconstruct the decision path.
5. **Ethics and human oversight** – no experiment should degrade the rights of human participants or harm living systems.  Experiments that simulate scarcity or collapse must clearly mark their purpose and boundaries.

## Contribution Guidelines

Contributors are encouraged to propose new experiments, entity roles or control‑law adjustments.  Please open a discussion or draft pull request with your design.  Include:

* The hypothesis you want to test and how it maps to the GCAT/BCAT model.
* The entities and scenarios involved.
* The expected outcomes and metrics to measure.
* Any potential risks or ethical considerations.

All contributions must adhere to the StegVerse community code of conduct.