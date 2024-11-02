---
tags:
  - physics
  - kinematics
---
The **work-kinetic energy theorem** is a theorem that links the concept of [[Work|work]] to [[Kinetic Energy|kinetic energy]].

Consider the integral definition of work:
$$
W=\int_{\mathbf{r}_{i}}^{\mathbf{r}_{f}}\sum \mathbf{\vec{F}}\cdot d\mathbf{\vec{r}}
$$
Recalling [[Newton's Laws|Newton's second law]],
$$
\sum \mathbf{\vec{F}}=m\mathbf{\vec{a}}
$$
Substituting,
$$
W=\int_{\mathbf{r}_i}^{\mathbf{r}_{f}}m\mathbf{\vec{a}}\cdot d\mathbf{\vec{r}}
$$
Recall that [[Acceleration|acceleration]] is the [[Time|time]] [[Derivative|derivative]] of [[Velocity|velocity]] (and velocity is the time derivative of [[Position|position]]),
$$
W=\int_{\mathbf{r}_{i}}^{\mathbf{r}_{f}}m\frac{d\mathbf{\vec{v}}}{d\mathbf{\vec{r}}}\frac{d\mathbf{\vec{r}}}{dt}d\mathbf{\vec{r}}
$$
$$
W=\int_{\mathbf{v}_{i}}^{\mathbf{v}_{f}}mv\ dv
$$
Evaluating the definite integral,
$$
W=\frac{1}{2}mv_{f}^2-\frac{1}{2}mv_{i}^2
$$
The quantity $\frac{1}{2}mv^2$ represents the energy associated with the [[Motion|motion]] of the particle. This is therefore known as the particle's *kinetic energy*. 
$$
K=\frac{1}{2}m\mathbf{\vec{v}}^2
$$
The work-kinetic energy theorem therefore states:

>[!quote] Work-Kinetic Energy Theorem
>When work is done on a system and the only change in the system is in its [[Speed|speed]], the net work done on the system equals the change in kinetic energy of the system.

Note though that this theorem only holds for [[Conservative Force|conservative forces]] since the work done by conservative forces is the same regardless of the path taken. [[Nonconservative Force|Nonconservative forces]] on the other hand are path-dependent, and the work done will vary on the path. 