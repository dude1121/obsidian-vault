---
tags:
  - physics
  - fluid-dynamics
---
**Buoyancy** is a force, directed upward, that is exerted by a [[Fluid|fluid]] on a submerged or floating object that opposes the [[Weight|weight]] of the object. The magnitude of the buoyant force acting on an object is equivalent to the weight of fluid that the object displaces. That is,
$$
B=m_{\ \text{fluid}}\ g
$$
This statement is known as [[Archimedes' Principle]]. This form is not as useful however as the mass of the displaced fluid is not always readily apparent. It is instead more often stated in terms of [[Density|density]] and [[Volume|volume]].
$$
\boxed{B=\rho_{\ \text{fluid}}\ gV}
$$
where $V=Ah$ is the volume of the fluid that is displaced. Since the product of the volume and density is the mass of the fluid, we see that this is equivalent to the relation shown above.

When working on problems related to buoyancy, we have two models that can help us analyze the situation: the *totally submerged object* and the *floating object*.
# Totally submerged object
When an object is totally submerged in a fluid of some density $\rho_{\text{fluid}}$, the magnitude of the upward buoyant force is $B=\rho_{\text{fluid}} gV$, where $V$ is the volume of the fluid displaced. However, from Archimedes' principle we know that $V_{\ \text{fluid}}=V_{\ \text{obj}}$, so really it does not matter which volume is used. If the object has mass $M$ and density $\rho_{\text{obj}}$, then the object's weight is equal to $F_{g}=Mg=\rho_{\text{obj}}gV_{obj}$, and the net force is $B-F_{g}=(\rho_{\text{fluid}}-\rho_{\text{obj}})gV_{\text{obj}}$. Therefore, **the direction of the net force (upward or downward) depends entirely on the densities of the object and fluid**. If $\rho_{\text{fluid}}>\rho_{\text{obj}}$, the object will float to the surface. If $\rho_{\text{fluid}}<\rho_{\text{obj}}$, the object will sink. If $\rho_{\text{fluid}}=\rho_{\text{obj}}$, then the net force will be $0\pu{\! N}$ and the object will remain in equilibrium.
# Floating object
If an object of volume $V_{\text{obj}}$ and density of $\rho_{\text{obj}}<\rho_{\text{fluid}}$ is floating on the surface of a fluid, that is, it is only *partially* submerged, the upward buoyant force is balanced by the downward gravitational force. The buoyant force has magnitude $B=\rho_{\text{fluid}}gV_{\text{fluid}}$ and the weight of the object is $F_{g}=\rho_{\text{obj}}gV_{\text{obj}}$. Since the object is in equilibrium, $F_{g}=B$. Therefore, $\rho_{\text{fluid}}gV_{\text{fluid}}=\rho_{\text{obj}}gV_{\text{obj}}$, or,
$$
\frac{V_{\text{fluid}}}{V_{\text{obj}}}=\frac{\rho_{\text{obj}}}{\rho_{\text{fluid}}}
$$
This equation shows that the **fraction of the volume of a floating object that is below the fluid surface is equal to the ratio of the density of the object to that of the fluid.**