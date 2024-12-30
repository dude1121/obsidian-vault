---
tags:
  - mathematics
  - calculus
  - real-analysis
---
The **mean value theorem** is a [[Theorem|theorem]] in [[Real Analysis|real analysis]] that has many different applications in mathematics. Put roughly, the theorem states that for any planar [[Arc|arc]] between two points, there is exists at least one point at which the [[Tangent Line|tangent]] to the arc is parallel to the [[Secant|secant]] through its endpoints.

# General statement

Let $f:[a,b]\to \mathbb{R}$ be a [[Continuous Function|continuous function]] on the closed interval $[a,b]$ and [[Differentiable Function|differentiable]] on the open interval $(a,b)$ where $a<b$ . There then exists some $c$ in $(a,b)$ such that
$$
f'(c)=\frac{f(b)-f(a)}{b-a}
$$

# For definite integrals

Let $f:[a,b]\to \mathbb{R}$ be a continuous function. Then there exists $c$ in $(a,b)$ such that
$$
\frac{1}{b-a}\int_{a}^b f(x)\ dx=f(c)
$$
This follows from the general statement due to the [[Fundamental Theorem of Calculus|fundamental theorem of calculus]].  This is sometimes also referred to as the [[Mean|mean]] or *average* value of a given function.