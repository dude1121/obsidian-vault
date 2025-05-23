---
tags:
  - mathematics
  - calculus
  - vector-calculus
---
**Divergence** is a [[Vector|vector]] operation on a vector function returns a [[Scalar|scalar]]. It is defined as,
$$
\begin{align}
\nabla \cdot \mathbf{v}&=\left(\frac{\partial}{\partial x} \hat{\imath}+\frac{\partial}{\partial y}\hat{\jmath}+\frac{\partial}{\partial z}\hat{k} \right)\cdot(v_{x}\hat{\imath}+v_{y}\hat{\jmath}+v_{z}\hat{k}) \\
&=\frac{\partial v_{x}}{\partial x}+\frac{\partial v_{y}}{\partial y}+\frac{\partial v_{z}}{\partial z}
\end{align}
$$
The divergence of a function is a measure of how much the vector $\mathbf{v}$ spreads out (or, diverges) from the point in question. We could take the example of a pond of water. If we sprinkled sawdust or grass on the water and the grass spread out, we would say that that point had a *positive* divergence. If they clumped together, it had a *negative* divergence.
# Special rules
Much like ordinary [[Derivative|derivatives]], divergences have product rules that apply. They are,
$$
\begin{align}
\text{I )}& \\
&\nabla \cdot (f\mathbf{A})=f(\nabla \cdot \mathbf{A})+\mathbf{A}\cdot(\nabla f) \\
\text{II )}& \\
&\nabla \cdot(\mathbf{A}\times \mathbf{B})=\mathbf{B}\cdot(\nabla \times \mathbf{A})-\mathbf{A}\cdot(\nabla \times \mathbf{B})
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
In non-cartesian coordinate systems, the divergence changes slighty.
$$
\begin{align}
\text{Spherical:}& \\
&\nabla \cdot \mathbf{v}=\frac{1}{r^2} \frac{\partial}{\partial r}(r^2v_{r})+\frac{1}{r\sin \theta} \frac{\partial}{\partial \theta}(v_{\theta}\sin \theta)+\frac{1}{r\sin \theta} \frac{\partial v_{\phi}}{\partial \phi} \\
\text{Cylindrical:}& \\
&\nabla \cdot \mathbf{v}=\frac{1}{s} \frac{\partial}{\partial s}(sv_{s})+\frac{1}{s} \frac{\partial v_{\phi}}{\partial \phi}+ \frac{\partial v_{z}}{\partial z}
\end{align}
$$
# Fundamental theorem for divergences
The fundamental theorem for divergences, also known as [[Green's Theorem]], states:
$$
\int_{\mathcal{V}}(\nabla \cdot \mathbf{v})\ d\tau=\oint_{\mathcal{S}}\mathbf{v}\cdot d\mathbf{a}
$$
In words, this says that the integral of the derivative (here, the divergence) over a *region* (in this case, the [[Volume|volume]] $\mathcal{V}$) is equal to the value of the function at the *boundary*. In the case above, this boundary is a surface integral of some volume. 