---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - network-theorems
---
**Norton's Theorem** (named after American engineer Edward L. Norton) is a network analysis tool that, similar to [[Thévenin's Theorem]], allows us to analyze circuits and represent them with a small amount of components that produce the same effect as the original circuit. Norton's Theorem states:

> [!quote] Norton's Theorem
> Any two-terminal bilateral network can be replaced by an equivalent circuit consisting of a current source and a parallel [[Impedance|impedance]].
# Procedure

1. *Identify the load and remove it from the circuit. Replace the load with a short. Label the terminals of the remaining two-terminal network.*
2. *Set all sources to zero and find the Norton-equivalent impedance. ($R_N$ or $Z_{N}$)*
3. *Solve the circuit to find $I_N$. I.e. the [[Current|current]] through the two terminals.*
4. *Redraw the Norton circuit and re-insert the load.*

