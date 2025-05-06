---
tags:
  - mathematics
  - calculus
  - vector-calculus
---
The **curl** is a [[Vector|vector]] operation on a [[Vector Function|vector function]] that returns a vector as well. The curl is technically defined as the [[Cross Product|cross product]] of the [[Del Operator|del operator]] and a vector function. That is,
$$
\begin{align}
\nabla \times \mathbf{v}&= \left|\begin{matrix}
\mathbf{\hat{x}} & \mathbf{\hat{y}} & \mathbf{\hat{z}} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
v_{x} & v_{y} & v_{z}
\end{matrix}\right| \\
&=\mathbf{\hat{x}}\left(\frac{\partial v_{z}}{\partial y}-\frac{\partial v_{y}}{\partial z} \right)+\mathbf{\hat{y}}\left(\frac{\partial v_{x}}{\partial z}-\frac{\partial v_{z}}{\partial x} \right)+\mathbf{\hat{z}}\left(\frac{\partial v_{y}}{\partial x}-\frac{\partial v_{x}}{\partial y} \right)
\end{align}
$$
The curl is a measure of how much the vector function swirls around the point in question. 
# Special rules
Much like ordinary [[Derivative|derivatives]], curls have product rules that apply. They are,
$$
\begin{align}
\text{I )}& \\
&\nabla \times (f\mathbf{A})=f(\nabla \times \mathbf{A})+\mathbf{A}\times(\nabla f) \\
\text{II )}& \\
&\nabla \times(\mathbf{A}\times \mathbf{B})=(\mathbf{B}\cdot \nabla)\mathbf{A}-(A\cdot \nabla)\mathbf{B}+\mathbf{A}(\nabla \cdot \mathbf{B})-\mathbf{B}(\nabla \cdot \mathbf{A})
\end{align}
$$
There is also a quotient rule for divergences.
$$
\begin{align}
\text{III )}& \\
& \nabla \cdot \left( \frac{\mathbf{A}}{g} \right)=\frac{g(\nabla \cdot \mathbf{A})-\mathbf{A}\cdot(\nabla g)}{g^2}
\end{align}
$$
# Curvilinear coordinates
In non-cartesian coordinate systems, the curl changes slightly.
$$
\begin{align}
\text{Spherical:}& \\
&\nabla \times \mathbf{v}=\frac{1}{r\sin \theta} \left[\frac{\partial}{\partial \theta}(\sin \theta v_{\phi})-\frac{\partial v_{\theta}}{\partial \phi}\right]\mathbf{\hat{r}}+\frac{1}{r}\left[\frac{\frac{1}{\sin \theta}\partial v_{r}}{\partial \phi}-\frac{\partial}{\partial r}(rv_{\phi})\right]\mathbf{\hat{\theta}} \\
&\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ +\frac{1}{r}\left[ \frac{\partial}{\partial r}(rv_{\theta})-\frac{\partial v_{r}}{\partial \theta}\right] \mathbf{\hat{\phi}}\\
\text{Cylindrical:}& \\
&\nabla \times \mathbf{v}=\left(\frac{1}{s}\frac{\partial v_{z}}{\partial \phi}-\frac{\partial v_{\phi}}{\partial z}\right)\mathbf{\hat{s}}+\left(\frac{\partial v_{s}}{\partial z}-\frac{\partial v_{z}}{\partial s}\right)\mathbf{\hat{\phi}}+\frac{1}{s}\left[\frac{\partial}{\partial s}(sv_{\phi})-\frac{\partial v_{s}}{\partial \phi}\right]\mathbf{\hat{z}}
\end{align}
$$
# Fundamental theorem for curls
The fundamental theorem for divergences, also known as [[Stokes' Theorem]], states:
$$
\int_{\mathcal{S}} (\nabla \times \mathbf{v}) \cdot d\mathbf{a}=\oint_{\mathcal{P}} \mathbf{v} \cdot d\mathbf{l}
$$
In words, this says that the integral of the derivative (here, the curl) over a *region* (in this case, a patch of surface $\mathcal{S}$) is equal to the value of the function at the *boundary*. In the case above, this boundary is a closed line integral. In other words, the total curl of a vector field over some surface is the same as the total flow at the boundary of that surface.