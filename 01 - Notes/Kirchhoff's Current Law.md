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
	\sum_{j}i_j=0\text{A}
$$

Consider the diagram below.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
	\draw
	(0,0) to[short, f=$I_1$] ++(2,-2) node[circ, label=left:\Large A](A){}
	to[short, f=$I_3$] ++(4,0) node[circ, label=right:\Large B](B){}
	(A) to[short, f<=$I_2$] ++(-2,-2)
	(B) to[short, f=$I_4$] ++(2,2)
	(B) to[short, f<=$I_5$] ++(2,-2)
	;
\end{circuitikz}
\end{document}
```

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
