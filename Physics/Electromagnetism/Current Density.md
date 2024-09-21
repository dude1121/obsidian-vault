---
tags:
  - electromagnetism
  - physics
  - Gustav-Kirchhoff
  - ohms-law
---
The **current density** is the amount of [[Charge|charge]] per unit time that flows through a unit area of a given cross-section. It is typically a [[Vector|vector quantity]], with the direction being that of the motion of charges at the given point. It is measured in [[Amperes|amperes]] per square-[[Metre|metre]] $\left[ \frac{\text{A}}{\text{m}^2} \right]$.

Current density can be described in terms of charge flowing over a surface (i.e. **surface current density**) or through a three dimensional volume (i.e. **volume current density**).
Surface current density is typically denoted with $\mathbf{K}$ and is given by,
$$
\mathbf{K}\equiv\frac{d\mathbf{I}}{d \ell_{\perp}}
$$
where $d\mathbf{I}$ is the current flowing over the surface, and $d \ell_{\perp}$ is an infinitesimal width of the surface, parallel to the flow of charge. $\mathbf{K}$ is therefore *current per unit width*. We can define $\mathbf{K}$ in terms of the surface charge density ($\sigma$) and the velocity of the charges ($\mathbf{v}$),
$$
\mathbf{K}=\sigma \mathbf{v}
$$
Volume current density is typically denoted with $\mathbf{J}$ and is defined as,
$$
\mathbf{J}\equiv\frac{d\mathbf{I}}{da_{\perp}}
$$
where $d\mathbf{I}$ is the current flowing through the volume, and $da_{\perp}$ is an infinitesimal cross-sectional area of the given volume, parallel to the flow of charge. $\mathbf{J}$ therefore is *current per unit area*. Much like $\mathbf{K}$, we can define $\mathbf{J}$ in terms of the volume charge density ($\rho$) and the velocity of those charges ($\mathbf{v}$),
$$
\mathbf{J}=\rho \mathbf{v}
$$

In most substances, we can also find the volume current density by finding the product of the force acting upon the charges and the material's ability to let those charges flow. In other words, 
$$
\mathbf{J}=\sigma \mathbf{f}
$$
where $\sigma$ is the [[Conductance|conductivity]] of a given material (not to be confused with surface charge density, also denoted by $\sigma$), and $\mathbf{f}$ is the *force per unit charge*. In an electrical circuit where the force acting on the charges is an [[Electric Field|electric field]], we can replace $\mathbf{f}$ with $\mathbf{E}$.
$$
\mathbf{J}=\sigma \mathbf{E}
$$
This is Kirchoff's reformulation of [[Ohm's Law]].