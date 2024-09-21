---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - Gustav-Kirchhoff
  - Kirchhoff
  - KCL
---
Kirchhoff's Current Law was discovered and named after German physicist Gustav Kirchhoff. It is also known as *Kirchhoff's First Law*, with [[Kirchhoff’s Voltage Law]] being the second law. KCL states:

> [!quote] Kirchhoff's Circuit Law
> The algebraic sum of currents in a network of conductors meeting at a node must equal zero.

This could be re-worded to state that **the [[Current|current]] entering any junction is equal to the current leaving that junction**. 

In general KCL can be summarized as,
$$
	\sum_{j=1}^ni_j=0\text{A}
$$

Consider the diagram below.
![[KCL Demo.png]]
By KCL, we can create equations for the currents at Node A and Node B.

*Node A*
Since currents $I_1$ and $I_2$ are entering the node, we denote them as positive. $I_3$ is leaving the node, so it is negative in our equation.
$$
	I_1+I_2-I_3=0\text{A}
$$
*Node B*
Currents $I_3$ and $I_5$ enter Node B, but $I_4$ is leaving the node, so it is negative while the other two are positive.
$$
	I_3-I_4+I_5=0\text{A}
$$
