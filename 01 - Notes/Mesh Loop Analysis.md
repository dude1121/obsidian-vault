---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - linear-algebra
cssclasses:
---
**Mesh Loop Analysis** is a method of circuit analysis that expands on the idea of [[Branch Current Analysis]] and allows us to solve circuits much easier than Branch Current Analysis allowed us to. Consider the same circuit seen in the Branch Current note.
![[Mesh Loop - General.png]]
This is the same circuit as before, with the main difference being that instead of there being three unknown currents, there are now only two. Mesh Loop, along with [[Nodal Analysis]], allows us to solve the circuit using one fewer equation and unknown variable than Branch Current Analysis. There are two methods of mesh loop analysis: *general* and *format*. The general method is shown here as an example, but generally format would be preferred.

# General Approach

In the general approach, we build two equations, both [[Kirchhoff’s Voltage Law|KVL]] loops based on currents $I_1$ and $I_2$. We then assign [[Resistor|resistor]] polarities based on these currents, as in Branch Current analysis. This gives us two equations that we can solve using [[Determinant|determinants]].

> [!question] Mesh Loop Analysis - General Approach
> Given:
> 	$E_{S1}=2\text{V}$
> 	$E_{S2}=6\text{V}$
> 	$R_1=2\Omega$
> 	$R_2=4\Omega$
> 	$R_3=1\Omega$
> Find the Kirchhoff's Voltage Law equations for this network.
> $$
> \begin{aligned}
> 	1)\text{  }&R_2(I_1+I_2)&+&R_1(I_1)&-&E_{S1}&=0\text{V}\\
> 	2)\text{  }&R_2(I_2+I_1)&+&R_3(I_2)&-&E_{S2}&=0\text{V}	
> \end{aligned}
> $$
> Expanding and rearranging...
> $$
> \begin{aligned}
> 	1)\text{  }&I_1R_2&+&I_2R_2&+&I_1R_1&=E_{S1}\\
> 		&&&I_1(R_1+R_2)&+&I_2(R_2)&=E_{S1}\\
> 		&&&6I_1&+&4I_2&=2\\
> 	1)\text{  }&I_2R_2&+&I_1R_2&+&I_2R_3&=E_{S2}\\
> 		&&&I_1(R_2)&+&I_2(R_2+R_3)&=E_{S2}\\
> 		&&&4I_1&+&5I_2&=6
> \end{aligned}
> $$
> Use determinants to find the unknown currents.
> $$
> I_1=\frac{
> 	\left|
> 		\begin{aligned}
> 			2&&4\\
> 			6&&5
> 		\end{aligned}
> 	\right|
> }{
> 	\left|
> 		\begin{aligned}
> 			6&&4\\
> 			4&&5
> 		\end{aligned}
> 	\right|
> }
> $$
> $$
> I_1=\frac{(2)(5)-(4)(6)}{(6)(5)-4^2}
> $$
> $$
> I_1=-1\text{A}
> $$

Note that the answer we get from Mesh Loop Analysis matches the answer we got from Branch Current Analysis, but it took far fewer steps. 

# Format Approach
The format approach is similar to the general approach, but it allows us to skip the step of building the KVL equations and immediately create our equations for the linear system of equations. Consider the following circuit:
![[Mesh Loop - Format.png]]
This time, there are no KVL loops, and both currents are assumed to be going in the clockwise direction. This assumption is important and must always be followed. To create our equations, we consider each current one at a time. When considering a current, we assume it is the *dominant* current. We first consider all the components that that current "touches". In this case, current $I_1$ touches components $R_1$ and $R_2$. Our first part of the equation is therefore this current multiplied by those components' resistances (or [[Impedance|impedances]] is this were an ac circuit). So our first bit of the equation looks like:
$$
\begin{aligned}
	1)\text{  }&I_1(R_1+R_2)&?=?\\
\end{aligned}
$$
Now, current $I_1$ "shares" a component with its opposing current, $I_2$. That component is $R_2$. To account for this, we subtract (because we assume this current to be dominant) this component multiplied by the opposing current from our equation. This gives us,
$$
\begin{aligned}
	1)\text{  }&I_1(R_1+R_2)-I_2R_2=?
\end{aligned}
$$
On the right side of this equation, we add in our sources, *according to their polarities*. This means that $E_{S1}$ is a positive value in our equation, since the current passes through the source from negative to positive, the preferred direction according to conventional current flow. However, $E_{S2}$ is negative, since the current passes through this source from positive to negative. This gives us our final equation for current $I_1$,
$$
\begin{aligned}
1)\text{ }&I_1(R_1+R_2)-I_2R_2=(E_{S1}-E_{S2})
\end{aligned}
$$
We can generate our equation for current $I_2$ in a similar manner,
$$
	2)\text{ }-I_1(R_2)+I_2(R_2+R_3)=E_{S2}
$$
If we substitute in values, our equations look like,
$$
\begin{aligned}
1)&&7I_1-&&6I_2&&=&&-5\\
2)&&-6I_1+&&8I_2&&=&&10
\end{aligned}
$$
This is a simple system of equations that could be solved using determinants. 