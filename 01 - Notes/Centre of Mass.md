---
tags:
  - physics
  - kinematics
  - dynamics
---
The **centre of mass** of a system is a special point around which the total [[Mass|mass]] of a given system or object is centred. Translational [[Motion|motion]] of the centre of mass of a system is the same as if all the mass of the system were concentrated at that point. 

The [[Position|position]] of the centre of mass of a system can be described as being the average position of the system's mass. Consider a system consisting of a pair of particles joined by a rod. 
![[centre-of-mass.png]]
If a force is applied above the centre of mass, the system rotates clockwise. If the force is below the centre of mass, the system is rotated counter clockwise. If the force is directly applied to the centre of mass, the system simply moves in the direction of the force with no rotation.

# Finding centre of mass for a system of particles
First, consider the simple example above. If we rotated the system of two particles such that they lay along the x-axis, we can simplify the calculation to find the centre of mass.
![[centre-of-mass-x-axis.png]]
The x-coordinate of the centre of mass is given by,
$$
x_{\text{CM}}\equiv \frac{m_{1}x_{1}+m_{2}x_{2}}{m_{1}+m_{2}}
$$
This concept can be extended for a system of many particles with masses $m_{i}$ in three dimensions. The x coordinate of the centre of mass of $n$ particles is given by,
$$
x_{\text{CM}}\equiv\frac{m_{1}x_{1}+m_{2}x_{2}+m_{3}x_{3}+\dots+m_{n}x_{n}}{m_{1}+m_{2}+m_{3}+\dots m_{n}}=\frac{\displaystyle\sum_{i}m_{i}x_{i}}{\displaystyle\sum_{i}m_{i}}=\frac{\displaystyle\sum_{i}m_{i}x_{i}}{M}\boxed{=\frac{1}{M}\displaystyle \sum_{i}m_{i}x_{i}}
$$
where $x_{i}$ is the x coordinate of the $i$th particle and $M$ is the total mass of the system $M\equiv\displaystyle \sum_{i}m_{i}$. The $y$ and $z$ components are similarly defined as
$$
y_{\text{CM}}\equiv \frac{1}{M}\displaystyle \sum_{i}m_{i}y_{i}\text{ and }z_{\text{CM}}\equiv \frac{1}{M}\displaystyle \sum_{i}m_{i}z_{i}
$$
This means that we can locate the centre of mass with a position [[Vector|vector]] $\mathbf{\vec{r}}_{CM}$. 
$$
\mathbf{\vec{r}}_{\text{CM}}=x_{\text{CM}}\mathbf{\hat{i}}+y_{\text{CM}}\mathbf{\hat{j}}+z_{\text{CM}}\mathbf{\hat{k}}=\frac{1}{M}\displaystyle \sum_{i}m_{i}\mathbf{\vec{r}}_{i}
$$
where $\mathbf{\vec{r}}_{i}$ is the position vector of the $i$th particle.

# Finding centre of mass for an extended object

When we are considering an extended object (or, [[Rigid Body|rigid body]]) the process of finding its centre of mass is slightly more cumbersome but the same principle applies as in the system of particles case. We can consider an extended object to be a collection of a large number of particles with a negligible separation between particles. This allows us to consider the object as having a continuous mass distribution. 

If we divide the object into small elements of mass $\Delta m_{i}$ with coordinates ($x_{i},y_{i},z_{i}$), we see that the x coordinate of the centre of mass is approximately,
$$
x_{\text{CM}}\approx \frac{1}{M}\displaystyle \sum_{i}x_{i}\Delta m_{i}
$$
with $y_{CM}$ and $z_{CM}$ being very similar. If we increase the number of elements under consideration, that is, we allow the magnitude of $\Delta m_{i}$ to approach zero, we get closer to finding the actual coordinate of the centre of mass. That is,
$$
x_{\text{CM}}=\lim_{ \Delta m_{i} \to 0 } \frac{1}{M}\displaystyle \sum_{i}x_{i}\Delta m_{i} 
$$
To evaluate this limit, we replace the summation with an [[Integral|integral]] and the $\Delta m_{i}$ with a [[Differential|differential]] element $dm$.
$$
x_{\text{CM}}=\frac{1}{M} \int x\ dm
$$
We can therefore express the position vector of the centre of mass as
$$
\mathbf{\vec{r}}_{\text{CM}}=\frac{1}{M} \int \mathbf{\vec{r}}\ dm
$$
Since this object is a continuous distribution of mass, each small mass element is acted upon by [[Gravity|gravity]]. The net effect of all these forces is equivalent to the effect of one force, $M\mathbf{\vec{g}}$, through one point, called the [[Centre of Gravity|centre of gravity]]. If $\mathbf{\vec{g}}$ is constant throughout the object, then the centre of gravity is the same as the centre of mass. If an object is pivoted at its centre of gravity, it will balance in any orientation.

# Velocity and acceleration of centre of mass

We have defined the position vector of the centre of mass, meaning it is possible to define a [[Velocity|velocity]] and [[Acceleration|acceleration]] vector for that same point.
$$
\mathbf{\vec{v}}_{\text{CM}}=\frac{d\mathbf{\vec{r}}_{\text{CM}}}{dt}\text{ and }\mathbf{\vec{a}}_{\text{CM}}=\frac{d\mathbf{\vec{v}}_{\text{CM}}}{dt}
$$
The velocity of centre of mass can be used to find the total [[Linear Momentum|momentum]] of a system $\mathbf{\vec{p}}_{\text{T}}$,
$$
\mathbf{\vec{p}}_{\text{T}}=M\mathbf{\vec{v}}_{\text{CM}}
$$
Likewise, the acceleration of centre of mass can be used to find the net [[Force|force]] acting upon the object.
$$
\Sigma\mathbf{\vec{F}}_{\text{ext}}=M\mathbf{\vec{a}}_{\text{CM}}
$$
Note that this is the *external* net force, as within any system there may be some forces acting internally. However, by considering the system as a whole, we find that the internal forces cancel in pairs across the entire system, meaning the net force is caused solely by the external forces.

These two concepts, the total momentum being defined as it is and the net force being defined as it is, lead us to the conclusion that **the centre of mass of a system of particles having a combined mass $M$ moves like an equivalent particle of mass $M$ would move under the influence of the net external force of the system.**

Integrating the expression for the net external force with respect to time gives us,
$$
\int \Sigma \mathbf{\vec{F}}_{\text{ext}}\ dt=\int M\mathbf{\vec{a}}_{\text{CM}}\ dt= M\int\frac{d\mathbf{\vec{v}}_{\text{CM}}}{dt}\ dt=M\int d\mathbf{\vec{v}}_{\text{CM}}=M\Delta \mathbf{\vec{v}}_{\text{CM}}
$$
Since we know that [[Impulse|impulse]] is the same as the time integral of force, this leads us to the same conclusion, that
$$
\mathbf{\vec{I}}=\Delta \mathbf{\vec{p}}_{\text{T}}
$$
