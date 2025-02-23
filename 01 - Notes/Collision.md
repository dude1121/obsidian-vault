---
tags:
  - physics
  - kinematics
  - dynamics
---
In kinematics, a **collision** is an event during which two particles come close to each other and interact by means of forces. In classical mechanics, the interaction forces are assumed to be much greater than any other external forces present, so we are able to use the [[Impulse|impulse]] approximation.

Collisions can be categorized into two main categories: *elastic collisions* and *inelastic collisions*. 
# Elastic collisions
An elastic collision between two objects is one in which the total [[Kinetic Energy|kinetic energy]] (as well as total [[Linear Momentum|linear momentum]]) of the system is the same before and after the collision. Collisions on the macroscopic scale are only ever *approximately* elastic because there is also some deformation or loss of kinetic energy that occurs. *Truly* elastic collisions only occur between atomic and subatomic particles.

Consider two particles of masses $m_{1}$ and $m_{2}$ moving with initial velocities $\mathbf{\vec{v}}_{1i}$ and $\mathbf{\vec{v}}_{2i}$. They collide head-on and then leave the collision site with different velocities, $\mathbf{\vec{v}}_{1f}$ and $\mathbf{\vec{v}}_{2f}$. Since both momentum and kinetic energy are conserved, we have the following relationships:
$$
m_{1}\mathbf{\vec{v}}_{1i}+m_{2}\mathbf{\vec{v}}_{2i}=m_{1}\mathbf{\vec{v}}_{1f}+m_{2}\mathbf{\vec{v}}_{2f}
$$
$$
\frac{1}{2}m_{1}{\mathbf{\vec{v}}_{1i}}^2+\frac{1}{2}m_{2}{\mathbf{\vec{v}}_{2i}}^2=\frac{1}{2}m_{1}{\mathbf{\vec{v}}_{1f}}^2+\frac{1}{2}m_{2}{\mathbf{\vec{v}}_{2f}}^2
$$
These two equations could be used as a [[Solving Systems of Linear Equations|system of equations]] that could be solved to find an unknown, or could be re-arranged to suit the needs of the problem. Eventually this turns out to be,
$$
v_{1f}=\left(\frac{m_{1}-m_{2}}{m_{1}+m_{2}}\right)v_{1i}+\left(\frac{2m_{2}}{m_{1}+m_{2}}\right)v_{2i}
$$
$$
v_{2f}=\left(\frac{2m_{1}}{m_{1}+m_{2}}\right)v_{1i}+\left(\frac{m_{2}-m_{1}}{m_{1}+m_{2}}\right)v_{2i}
$$
Note that this gives the resultant [[Speed|speed]], not [[Velocity|velocity]]. Also note that if $m_{2}$ is initially at rest ($v_{2i}=0$) then these equations simplify. If $m_{1}$ is much greater than $m_{2}$ and $m_{2}$ begins at rest, $v_{1f}\approx v_{1i}$ and $v_{2f}\approx 2v_{1i}$. That is, if a very heavy particle collides with a very light one that is initially at rest, the heavy particle continues its motion unaltered and the light particle rebound with a speed equal to about twice the initial speed of the heavy particle. An example of this might be that of a moving heavy [[Atom|atom]], like [[Uranium|uranium]], striking a light atom, like [[Hydrogen|hydrogen]]. 

In the inverse case, $m_{2}$ is much greater than $m_{1}$ and $m_{2}$ is initially at rest, then $v_{1f}\approx-v_{1i}$ and $v_{2f}\approx{0}$. That is, when a very light particle collides with a very heavy particle at rest, the light particle has its velocity reversed and the heavy one remains approximately at rest.
# Inelastic collisions
An inelastic collision is one in which the total kinetic energy of the system is *not* the same before and after the collision. Note though that the total momentum is *still* conserved. There are two types of inelastic collisions. *Perfectly inelastic* collisions are collisions in which the two objects stick together after they collide. Think of a car colliding with another car in an intersection and the force carries them both to the corner of the intersection. When the objects do not stick together, the collision is simply called *inelastic*. 
## Perfectly inelastic collisions
In a perfectly inelastic collision, the conservation of momentum leads to a special case that can  be used to analyze this situation. Consider two particles of masses $m_{1}$ and $m_{2}$ moving towards each other with initial velocities $\mathbf{\vec{v}}_{1i}$ and $\mathbf{\vec{v}}_{2i}$. The two particles collide and continue moving with a common velocity, $\mathbf{\vec{v}}_{f}$. Due to the [[Law of Conservation of Linear Momentum|law of conservation of linear momentum]],
$$
m_{1}\mathbf{\vec{v}}_{1i}+m_{2}\mathbf{\vec{v}}_{2i}=(m_{1}+m_{2})\mathbf{\vec{v}}_{f}
$$
Solving for the final velocity gives,
$$
\mathbf{\vec{v}}_{f}=\frac{m_{1}\mathbf{\vec{v}}_{1i}+m_{2}\mathbf{\vec{v}}_{2i}}{m_{1}+m_{2}}
$$
# Collisions in two dimensions
Conservation of linear momentum still holds in two dimensions, so instead of one equation for momentum we now have two (or, really, we have $n$ equations for the $n$ dimensions being examined).

$$
m_{1}v_{1ix}+m_{2}v_{2ix}=m_{1}v_{1fx}+m_{2}v_{2fx}
$$
$$
m_{1}v_{1iy}+m_{2}v_{2iy}=m_{1}v_{1fy}+m_{2}v_{2fy}
$$

![[two-dimensional-collision.png]]
Consider the above specific example.  After particle 1 and particle 2 collide, particle 1 moves with a velocity $\mathbf{\vec{v}}_{1f}$ at angle $\theta$ to the horizontal, whereas particle 2 moves with velocity $\mathbf{\vec{v}}_{2f}$ at angle $\phi$ to the horizontal. This event is known as a *glancing* collision.  If we again apply the law of conservation of momentum and note that the initial $y$ component of the momentum is zero, we get
$$
m_{1}v_{1i}=m_{1}v_{1f}\cos \theta+m_{2}v_{2f}\cos \phi
$$
$$
0=m_{1}v_{1f}\sin \theta-m_{2}v_{2f}\sin \phi
$$
The negative in the second equation is to indicate that the $y$ component of the second particle's velocity has a downward direction. As long as no more than two of the seven components in a given problem is known, these equations can be solved simultaneously. If the collision is elastic, we can also use the conservation of kinetic energy to give us a third equation:
$$
\frac{1}{2}m_{1}{v_{1i}}^2=\frac{1}{2}m_{1}{v_{1f}}^2+\frac{1}{2}m_{2}{v_{2f}}^2
$$
