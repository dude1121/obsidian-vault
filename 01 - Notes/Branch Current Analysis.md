---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - linear-algebra
---
In more complicated circuits, additional tools are needed to solve them. Take this circuit for example.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, a=$2$V] (0,-4)
(0,0) to[R, l=$R_1$, a=$2\Omega$, v<=$V_{R1}$, -*, voltage shift=4, f=$I_1$] (3,0)
(6,0) to[R, l=$R_3$, a=$1\Omega$,v^<=$V_{R3}$, voltage shift=4, f=$I_3$] (3,0)
(6,0) to[battery, l=$E_{S2}$, a=$6$V] (6,-4)
to[short, -*] (3,-4)
to[short] (0,-4)
(3,-4) to[R, l_=$R_2$, a^=$4\Omega$, v<=$V_{R2}$, voltage shift=4, f=$I_2$] (3,0)
;
\end{circuitikz}
\end{document}
```

There are two [[Voltage Sources|voltage sources]], $E_{S1}$ and $E_{S2}$, and three resistors, $R_1$, $R_2$, and $R_3$, but the currents are unknown. We can't use [[Ohm's Law]] to solve this, at least not directly. Instead we can use a tool called **Branch Current Analysis**. This is the fore-runner to more advanced techniques like [[Nodal Analysis]] and [[Mesh Loop Analysis]].

# Procedure

1. *Assign a distinct current of arbitrary direction to each branch of the network.*
		In this first step, we look at each individual branch of the circuit with an unknown current, and we assign it an arbitrary direction. Whether or not the current is actually flowing in this direction is irrelevant (our answer will end up being negative if the assumption was incorrect).
2. *Indicate the polarities for each [[Resistor|resistor]] as determined by the assumed current direction.*
		Now that we have decided on a direction for our currents, we must also assume a polarity for each resistor that is consistent with our assumption for current.
3. *Apply [[Kirchhoff’s Voltage Law]] around each closed, independent loop of the network.*
		The direction of the KVL loop is irrelevant, and the loops do not all have to be in the same direction.
4. *Apply [[Kirchhoff's Current Law]] at the minimum number of nodes that will include all branch currents of the network.*
		The KCL equations will help tie together our KVL loop equations.
5. *Solve the resulting simultaneous [[Linear Equations|linear equations]] for assumed branch currents.*

Let's use the above circuit as an example.
> [!question] Branch Current Analysis
> ![[Branch.png]]
> Given:
> 	$E_{S1}=2\text{V}$
> 	$E_{S2}=6\text{V}$
> 	$R_1=2\Omega$
> 	$R_2=4\Omega$
> 	$R_3=1\Omega$
> Find the Kirchhoff's Voltage Law equations for this network.
> $$
> \begin{gathered}
> 	1) -V_{R2}+V_{R1}-E_{S1}=0\text{V} \\
> 	2) -V_{R2}+V_{R3}-E_{S2}=0\text{V}
\end{gathered}
> $$ 
> Find the Kirchhoff's Current Law equation for Node $A$.
> $$ 
> \begin{gathered}
> 3)\text{ } I_1+I_2+I_3=0\text{A}
\end{gathered}
> $$
> Recall that $V=IR$. Express all unknown voltages in terms of current and resistance. Rearrange the three equations as a system of three linear equations.
> $$
> \begin{aligned}
> 	1) &\text{ }I_1(R_1)&-&I_2(R_2)&+&I_3(0)&=&E_{S1} \\
> 	2) &\text{ }I_1(0)&-&I_2(R_2)&+&I_3(R_3)&=&E_{S2} \\
> 	3) &\text{ }I_1&+&I_2&+&I_3&=&0
> \end{aligned}
> $$
> Use [[Determinant|determinants]] to solve for each unknown current.
> $$
> I_1=\frac{\left|
> 	\begin{aligned}
> 		&E_{S1}&-R_2&&0\\
> 		&E_{S2}&-R_2&&R_3\\
> 		&0&1&&1\\
> 	\end{aligned}	
> 	\right|}{\left|
> 	\begin{aligned}
> 		&R_1&-R_2&&0\\
> 		&0&-R_2&&R_3\\
> 		&1&1&&1\\
> 	\end{aligned}	
> 	\right|}
> $$
> $$
> I_1=\frac{\left|
> 	\begin{aligned}
> 		&2&-4&&0\\
> 		&6&-4&&1\\
> 		&0&1&&1\\
> 	\end{aligned}	
> 	\right|}{\left|
> 	\begin{aligned}
> 		&2&-4&&0\\
> 		&0&-4&&1\\
> 		&1&1&&1\\
> 	\end{aligned}	
> 	\right|}
> $$
> $$
> 	I_1=\frac{(2)(-4)(1)+(-4)(1)(0)+(0)(6)(1)-[(0)(-4)(0)+(1)(1)(2)+(-4)(6)(1)]}{(2)(-4)(1)+(-4)(1)(1)+(0)(0)(1)-[(0)(-4)(1)+(1)(1)(2)+(-4)(0)(1)]}
> $$
> $$
> 	I_1=\frac{14}{-14}
> $$
> $$
> 	I_1=-1\text{A}
> $$
> *Note: This would ideally be done for all three currents, but the process is repetitive.*


