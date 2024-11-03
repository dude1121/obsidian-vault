---
tags:
  - physics
---
A **conservative force** is a type of [[Force|force]] for which the [[Law of Conservation of Energy|law of conservation of energy]] applies and is therefore path independent. It must satisfy the following condition:
$$
\mathbf{\vec{F}}=-\nabla U
$$
where $U$ is the [[Potential Energy|potential energy]] of the system, and $\nabla$ is the [[Gradient|grad]] operation. If this force were a two-dimensional force, the components would be
$$
\begin{aligned}
F_{x}=-\frac{\partial U}{\partial x}&&F_{y}=-\frac{\partial U}{\partial y}
\end{aligned}
$$
We could state that the change in potential energy is,
$$
\Delta U=\frac{\partial U}{\partial x}dx+\frac{\partial U}{\partial y}dy
$$
which is that same as,
$$
\Delta U=-\mathbf{\vec{F}}\cdot d\mathbf{\vec{r}}
$$
and if we take the [[Summation|sum]] of both sides we get,
$$
-\sum \Delta U=\int_{r_{i}}^{r_{f}}\mathbf{\vec{F}}\cdot d\mathbf{\vec{r}} 
$$
then evaluating the sum on the left side,
$$
U_{1}-U_{2}=\int_{r_{i}}^{r_{f}}\mathbf{\vec{F}}\cdot d\mathbf{\vec{r}}
$$
This means that for a conservative force **the [[Work|work]] done by the force is the same as the object's change in potential energy**. Further, that [[Integral|integral]]'s value is the same as the difference in [[Kinetic Energy|kinetic energy]],
$$
U_{1}-U_{2}=\int_{r_{i}}^{r_{f}}\mathbf{\vec{F}}\cdot d\mathbf{\vec{r}}=K_{2}-K_{1}
$$
When rearranging we get,
$$
K_{1}+U_{1}=K_{2}+U_{2}
$$
thus satisfying the law of conservation of energy.