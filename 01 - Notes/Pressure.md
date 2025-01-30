---
tags:
  - physics
  - fluid-dynamics
---
**Pressure** is the [[Force|force]] applied perpendicular to the surface of an object per unit [[Area|area]] over which that force is distributed. It is defined as,
$$
P=\frac{F}{A}
$$
Pressure is measured in [[Pascal|pascals]] $[\pu{ Pa}]$. Pressure is sometimes distinguished between *absolute pressure*, which is what is defined above, and *[[Gauge Pressure|gauge pressure]]* which is the pressure of the object *relative to* the ambient pressure.

If the pressure varies over an area, the infinitesimal force $dF$ on an infinitesimal surface element of area $dA$ is
$$
dF=P\ dA
$$
The force could therefore be found by integrating both sides.
# Variation with depth
Consider an object submerged in some liquid. Let's assume that the liquid is incompressible, that is, its [[Density|density]] is uniform. Imagine selecting some imaginary cylinder of cross-sectional [[Area|area]] $A$ extending from depth $d$ to depth $d+h$. The liquid will exert force on all points on the surface of this sample, perpendicular to the surface. The pressure exerted on the bottom of the sample is $P$ and the pressure exerted on the top face is $P_{0}$. Therefore, the upward force exerted by the outside fluid on the bottom of the cylinder has a magnitude of $PA$ and the downward force exerted on the top has a magnitude of $P_{0}A$. The mass of liquid in the cylinder is $\rho V=\rho Ah$; therefore the [[Weight|weight]] of the cylinder is $M_{g}=\rho Ahg$. Since the cylinder is in equilibrium, the net force must be $0$. Assuming a positive $y$ direction,
$$
\sum \mathbf{\vec{F}}=PA\mathbf{\hat{j}}-P_{0}A\mathbf{\hat{j}}-M_{g}\mathbf{\hat{j}}=0
$$
or,
$$
PA-P_{0}A-\rho Ahg=0
$$
$$
\boxed{P=P_{0}+\rho gh}
$$
This shows that the pressure $P$ at a depth $h$ below a point in the liquid at which the pressure is $P_{0}$ is greater by an amount $\rho gh$. If the liquid is open to the atmosphere and $P_{0}$ is the pressure at the surface of the liquid, then $P_{0}$ is [[Atmospheric Pressure|atmospheric pressure]], a constant value assumed to be,
$$
P_{0}=1\pu{\! atm}=1.013\times 10^5\ \pu{ Pa}
$$
The pressure at the surface must be transmitted to every other point in the fluid, this is known as *Pascal's Law*.

>[!quote] Pascal's Law
>a change in the pressure applied to a fluid is transmitted undiminished to every point of the fluid and to the walls of the container
>

Pascal's law is the basis for machines like hydraulic presses. 
![[hydraulic-press-pascals-law.png]]
A force of magnitude $F_{1}$ is applied to a small piston with surface area $A_{1}$. The pressure is transmitted through an incompressible fluid (in theory, at least) to the face of the larger piston $A_{2}$. Since the pressure must be constant, the force applied to this larger piston $F_{2}$ is greater than $F_{1}$ by a factor of ${A_{2}}/{A_{1}}$. This allows a large output force to be applied with a smaller input force.

Since liquid is never removed or added to this system, the volume of liquid displaced by $F_{1}$, $\Delta x_{1}$, is the same volume as the liquid that displaced the larger piston a displacement of $\Delta x_{2}$. That is, $A_{1}\Delta x_{1}=A_{2}\Delta x_{2}=A_{2}/A_{1}=\Delta x_1/\Delta x_{2}$. Since $A_{2}/A_{1}=F_{2}/F_{1}$ as shown above, we can therefore say that $F_{2}/F_{1}=\Delta x_{1}/\Delta x_{2}$, or, $F_{1}\Delta x_{1}=F_{2}\Delta x_{2}$. This shows that the work done by each force is equivalent and therefore [[Law of Conservation of Energy|conservation of energy]] is satisfied.