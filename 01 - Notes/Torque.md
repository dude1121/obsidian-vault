---
tags:
  - physics
  - kinematics
  - dynamics
---
**Torque** is rotational [[Force|force]]. Torque is a [[Vector|vector]] quantity but its directional nature is different than the force vector. It is measured in [[Newton|newton]]-[[Metre|metres]] $[\text{N}\cdot \text{m}]$ and is often designated with either $T$ or $\tau$. 

Consider a wrench as in the diagram below.
![[torque-wrench-example.png]]
If some force $\mathbf{\vec{F}}$ is applied to the end of the wrench, the force makes an angle $\phi$ to the horizontal. The magnitude of the torque applied to the wrench is given by,
$$
\tau=rF\sin \phi=Fd
$$
where $r$ is the length of the wrench, put generally, this is the distance from the pivot point $O$ to the point of applied force, $F$ is the magnitude of the applied force, and $d$ is the imaginary line created by $r\sin \phi$ called the *moment arm* of $\mathbf{\vec{F}}$.  

The *line of action* is an imaginary line that extends the force vector that forms the right triangle that defines the moment arm.

From this definition of torque we see that maximum torque occurs when the force is applied perfectly perpendicular to the wrench, i.e., when $\phi=90\degree$. No torque is applied if this angle is $0\degree$. Torque is generally considered to be positive if the turning tendency of the force is counterclockwise and negative if the turning tendency is clockwise.

Torque, however, is ultimately a vector, not a [[Scalar|scalar]]. This means that the equation defined above is sufficient only to provide the *magnitude* of the applied torque, not its direction. To factor in the direction, torque is defined as,
$$
\mathbf{\vec{\tau}}=\mathbf{\vec{r}}\times \mathbf{\vec{F}}
$$
where $\mathbf{\vec{r}}$ is the position vector of the point with respect to the centre of rotation, and $\mathbf{\vec{F}}$ is the force vector applied to that point. The resultant torque is therefore the [[Cross Product|cross product]] of the two. Due to the nature of the cross product, this means that the direction of torque is always perpendicular to the plane formed by the position vector and the applied force vector.
# Net torque

The net torque acting on a particle is related to the net tangential force applied on the particle.
$$
\sum F_{t}=ma_{t}
$$
The magnitude of the net torque due to $\mathbf{\vec{F}}_{t}$ on the particle about an axis through the centre of the circle is
$$
\sum \tau=\sum F_{t}r=(ma_{t})r
$$
Since the tangential [[Acceleration|acceleration]] is related to the [[Angular Acceleration|angular acceleration]] by $a_{t}=r\alpha$, the net torque can be expressed as,
$$
\sum \tau=(mr\alpha)r=(mr^2)\alpha
$$
$mr^2$ is the [[Moment of Inertia|moment of inertia]] of the particle about the $z$ axis passing through the origin, so,
$$
\boxed{\sum \tau = I\alpha}
$$
This relationship also holds for a rigid object (see *Physics*, Serway & Jewett p. 284 for proof). Note that the net torque is proportional to the angular acceleration with the moment of inertia being the proportionality constant. 

Torque is also related to the body's [[Angular Momentum|angular momentum]] by,
$$
\sum \mathbf{\vec{\tau}}=\frac{d\mathbf{\vec{L}}}{dt}
$$
