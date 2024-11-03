---
tags:
  - physics
  - kinematics
---
**Impulse** is the change in [[Linear Momentum|linear momentum]] of an object. It is a [[Vector|vector]] quantity, denoted by $\mathbf{\vec{I}}$ or $\mathbf{\vec{J}}$, and it is measured in [[Newton|newton]]-[[Second|seconds]] $[\pu{ N\cdot s}]$. It can be defined as
$$
\Delta \mathbf{\vec{p}}=\mathbf{\vec{I}}
$$
which is derived as follows. Recall that [[Force|force]] is equal to the time [[Derivative|derivative]] of momentum. Expressing this as a differential,
$$
d\mathbf{\vec{p}}=\sum \mathbf{\vec{F}}\ dt
$$
[[Integral|Integrating]] both sides results in
$$
\Delta \mathbf{\vec{p}}=\mathbf{\vec{p}}_{f}-\mathbf{\vec{p}}_{i}=\int_{t_{i}}^{t_{f}}\sum \mathbf{\vec{F}}\ dt
$$
This integral from $t_{i}$ to $t_{f}$ is the actual definition of impulse.
$$
\mathbf{\vec{I}}=\int_{t_{i}}^{t_{f}}\sum \mathbf{\vec{F}}\ dt
$$
In some cases where the time varying force becomes difficult to model, we can [[Mean Value Theorem|average]] the integral, and assume that the average force applied is a constant net force, $\left(\sum \mathbf{\vec{F}}\right)_{avg}=\sum \mathbf{\vec{F}}$. This makes the impulse calculation much easier,
$$
\mathbf{\vec{I}}=\left(\sum \mathbf{\vec{F}}\right)_{avg}\ \Delta t
$$
