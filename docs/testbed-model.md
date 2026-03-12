# Testbed Model

This document summarises the mathematical model underlying the entity sandbox.  The framework extends the GCAT (Governance, Constraints, Artefacts, Trust) and BCAT (Byzantine, Constraints, Artefacts, Trust) theories to produce a discrete‑time controlled dynamical system.

## State Vector

The system state at timestep \(n\) is defined as:

\[
x_n = (g_n, c_n, a_n, t_n)
\]

where:

* \(g_n \in [0,1]\) is the level of governance legitimacy.
* \(c_n \in [0,1]\) measures the level of constraints (laws, policies, protocols).
* \(a_n \in [0,1]\) is the pressure of artefacts or execution (how aggressively changes are made).
* \(t_n \in [0,1]\) represents trust continuity and social capital.

## Transition Operator

State transitions are governed by an operator \(F(x_n, u_n)\) such that:

\[
x_{n+1} = F(x_n, u_n)
\]

where \(u_n\) is a vector of control inputs proposed by entities.  For a transition to be valid, it must satisfy three conditions:

1. **Admissibility Bound**:
   \[
   a_{n+1} \le K\, g_{n+1}^{\alpha}\, c_{n+1}^{\beta}\, t_{n+1}^{\gamma}
   \]
   for constants \(K, \alpha, \beta, \gamma > 0\).  This prevents artefact pressure from outpacing the available governance, constraints and trust resources.

2. **Rigel Stability Constraint**: the change \(\Delta x_n = x_{n+1} - x_n\) must lie within a stability margin \(M(x_n)\).  This ensures transitions are gradual enough to remain within the Viability Kernel.

3. **Receipt Continuity**: every transition must produce a cryptographically chained receipt linking \(x_n\) to \(x_{n+1}\), including the control input and evaluation results.  This supports auditability and reproducibility.

Entities in the sandbox exercise this operator under different test scenarios.  The explicit form of \(F\) may vary by experiment; in some cases it could be a simple linear update, while in others it might integrate non‑linear or stochastic effects.

## Example Metrics

Experiments define metrics such as:

* **Rigel Distance** – the Euclidean distance from the current state to the equilibrium point \(x^*\).
* **Recoverability Index** – the degree of recovery after a perturbation, defined as \(1 - D_{\mathrm{rigel}}(x_n)/D_{\mathrm{rigel}}(x_{n_0})\).
* **Synchrony Indicator** – the average cosine similarity between control proposals from different entities, used to detect collusion or monoculture.
* **Throughput vs. Legitimacy** – the ratio \(a_n/(g_n t_n)\) indicating whether artefact production is outpacing governance and trust resources.
* **Viability Score** – the difference between the admissibility bound and the current artefact pressure: \(K\,g_n^{\alpha}\,c_n^{\beta}\,t_n^{\gamma} - a_n\).  Positive values indicate safe operation.

Contributors adding new experiments should reference or extend these definitions to ensure consistency across reports.