# Metric Definitions

This document provides detailed definitions for the common metrics used across experiments in the entity‑sandbox. Each metric quantifies a specific aspect of system behaviour under the GCAT/BCAT model. By standardising these measures, experimenters can compare results across different scenarios and ensure that reports remain consistent.

## Rigel Distance

**Definition:** The Euclidean distance from the current state \(x_n = (g_n,c_n,a_n,t_n)\) to a predefined equilibrium point \(x^* = (g^*,c^*,a^*,t^*)\):

\[
D_{\mathrm{rigel}}(x_n) = \sqrt{(g_n - g^*)^2 + (c_n - c^*)^2 + (a_n - a^*)^2 + (t_n - t^*)^2}
\]

**Purpose:** Measures how far the system has drifted from its stable operating point (the **Rigel equilibrium**). Smaller distances indicate closer adherence to desired governance, constraint, artefact and trust levels.

**Usage:** Useful for monitoring recovery after perturbations and for comparing how different control strategies maintain proximity to the equilibrium.

## Recoverability Index

**Definition:** Quantifies the degree of recovery after a disturbance. Given an initial perturbation state \(x_{n_0}\) and a later state \(x_n\), the recoverability index is:

\[
R_{\mathrm{rec}}(n) = 1 - \frac{D_{\mathrm{rigel}}(x_n)}{D_{\mathrm{rigel}}(x_{n_0})}
\]

**Purpose:** Captures how effectively the system returns toward equilibrium following a shock. Values approach 1 as the state recovers and approach 0 when no recovery occurs. Negative values indicate further divergence.

**Usage:** Employed in recovery‑path experiments to evaluate different intervention strategies or control parameters.

## Synchrony Indicator

**Definition:** The average pairwise cosine similarity between proposed control inputs from multiple entities. Given a set of proposals \(\{u^1, u^2, \ldots, u^m\}\) each normalised to unit length, the synchrony indicator is:

\[
S = \frac{2}{m(m-1)} \sum_{i<j} \frac{u^i \cdot u^j}{\|u^i\|\,\|u^j\|}
\]

**Purpose:** Detects hidden consensus or collusion among entities. Values close to 1 indicate high synchrony (agents are proposing nearly identical actions), while values near 0 suggest diverse or orthogonal proposals.

**Usage:** Used in synchrony experiments to enforce diversity and spot potential monocultures. High synchrony may trigger additional governance review.

## Throughput vs. Legitimacy

**Definition:** The ratio of artefact pressure to the product of governance and trust:

\[
T_{\mathrm{legit}}(n) = \frac{a_n}{g_n \cdot t_n}
\]

**Purpose:** Indicates whether artefact production is outpacing the system’s governance legitimacy and social capital. High values mean the system is executing changes faster than its legitimacy or trust can support, increasing risk of collapse.

**Usage:** Serves as a quick diagnostic metric; can be plotted over time to visualise sustainability of execution rates.

## Viability Score

**Definition:** The margin between the admissibility bound and the current artefact pressure:

\[
V(x_n) = K\,g_n^{\alpha}\,c_n^{\beta}\,t_n^{\gamma} - a_n
\]

where \(K,\alpha,\beta,\gamma\) are constants defined in the admissibility inequality.

**Purpose:** Measures how much headroom remains before the system violates the admissibility constraint. Positive values imply the state is within safe bounds; zero means the system sits exactly on the boundary; negative values signal a violation and should trigger rollback or rejection of proposed actions.

**Usage:** Critical for admissibility tests and for real‑time monitoring of artefact pressures relative to governance, constraints and trust.

## Additional Notes

These metrics should be computed and recorded for every relevant experiment. When designing new metrics, contributors should document them in this file and update any report templates accordingly. Clear and consistent definitions enable reliable comparisons across runs and help identify which interventions most effectively maintain system stability and recovery.