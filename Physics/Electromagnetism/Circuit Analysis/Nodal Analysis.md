---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - linear-algebra
---
**Nodal Analysis** is a form of advanced circuit analysis that allows us to find unknown [[Voltage|voltages]] and [[Current|currents]] by use of *nodes*. Similar to how [[Mesh Loop Analysis]] is an extension of [[Kirchhoff’s Voltage Law]], nodal analysis is an extension of [[Kirchhoff's Current Law]]. Also like Mesh Loop analysis, there are two approaches to Nodal Analysis: *general* and *format*. 
# General Approach

## Procedure
 1. *Determine the number of nodes within the network.*
 2. *Pick a reference node, and label each remaining node with a subscripted value of voltage ($V_1$, $V_2$, etc.)*
 3. *Apply KCL at each node except the reference. Assume that all unknown currents leave the node for each application of KCL.*
 4. *Solve the resulting equations for the nodal voltages.*
Take the following circuit as an example:
![[Nodal Example 1.png]]

Here, we have three *nodes*: node 1, node 2, and [[Ground (Electricity)|ground]]. Since ground is assumed to have a potential of $0\text{V}$, it is our reference node, as per step 2. We'll note the voltages at node 1 and 2 as $V_1$ and $V_2$. 

Next, we build our KCL equations. For node 1,
$$
	I_{S1}-I_{R1}-I_{R2}=0\text{A}
$$
$I_{S1}$ is our source and we know its value, $4\text{A}$, and since it is entering the node it is positive. The currents through $R_1$ and $R_2$ are unknown, so we assume they are leaving and therefore negative. However, nodal analysis is about solving for the unknown *voltage*, not current. So let's express each current as the voltage across the component over the resistance according to [[Ohm's Law]]. We'll also move the source current to the right side of the equation.
$$
	\frac{V_1-V_{GND}}{R_1}+\frac{V_1-V_2}{R_2}=I_{S1}
$$
Remember that voltage across a component is a *difference* from the higher potential side to the lower potential side. We can simplify this further by remembering that $V_{GND}=0\text{V}$. Let's also separate the second term into two terms each with $R_2$ in the denominator.
$$
	\frac{V_1}{R_1}+\frac{V_1}{R_2}-\frac{V_2}{R_2}=I_{S1}
$$
Now factor.
$$
	V_1\left(\frac{1}{R_1}+\frac{1}{R_2}\right)-V_2\left(\frac{1}{R_2}\right)=I_{S1}
$$
Since $R_1$, $R_2$, and $I_{S1}$ are all known values, we can sub those values in to come up with the final equation for node 1.
$$
\begin{aligned}
	V_1\left(\frac{1}{2}+\frac{1}{12}\right)-V_2\left(\frac{1}{12}\right)=4\\
	V_1\left(\frac{7}{12}\right)-V_2\left(\frac{1}{12}\right)=4
\end{aligned}
$$
We can follow a similar process for node 2 to end up with,
$$
\begin{aligned}
	-I_{S2}-I_{R2}-I_{R3}&=0\text{A}\\
	\frac{V_2-V_1}{R_2}+\frac{V_2}{R_3}&=-I_{S2}\\
	-V_1\left(\frac{1}{R_2}\right)+V_2\left(\frac{1}{R_2}+\frac{1}{R_3}\right)&=-I_{S2}\\
	-V_1\left(\frac{1}{12}\right)+V_2\left(\frac{1}{12}+\frac{1}{6}\right)&=-2\\
	-V_1\left(\frac{1}{12}\right)+V_2\left(\frac{1}{4}\right)&=-2
\end{aligned}
$$
Our system of equations is therefore
$$
\begin{aligned}
	V_1\left(\frac{7}{12}\right)-V_2\left(\frac{1}{12}\right)&=4\\
	-V_1\left(\frac{1}{12}\right)+V_2\left(\frac{1}{4}\right)&=-2
\end{aligned}
$$
We could multiply both equations by 12 to make our [[determinant]] a little easier to evaluate.
$$
\begin{aligned}
	7V_1-V_2&=48\\
	-V_1+3V_2&=-24
\end{aligned}
$$
$$
\begin{aligned}
	V_1&=\frac{\left|\begin{aligned}48&&-1\\-24&&3\end{aligned}\right|}{\left|\begin{aligned}7&&-1\\-1&&3\end{aligned}\right|}
	&V_2&=\frac{\left|\begin{aligned}7&&48\\-1&&-24\end{aligned}\right|}{\left|\begin{aligned}7&&-1\\-1&&3\end{aligned}\right|}\\
	&=\frac{120}{20}&&=\frac{-120}{20}\\
	&=6\text{V}&&=-6\text{V}
\end{aligned}
$$

# Format Approach

## Procedure
1. *Choose a reference node and assign a subscripted voltage label to the remaining nodes of the network*.
2. *The number of equations for a complete solution is equal to the number of subscripted voltages. Column 1 of each equation is formed by summing the [[Conductance|conductances]] tied to the node of interest and multiplying the result by that subscripted node.*
3. *We must now consider the mutual terms which are always subtracted from the first column. Each mutual term is the product of the mutual conductance and the other nodal voltage, tied to that conductance.*
4. *The column to the right is the algebraic sum of the current sources tied to the node of interest. A current source is "positive" if it supplies current to the node and "negative" if it draws current from the node.*
5. *Solve the resulting simultaneous equations for the desired voltages.*

Consider the following circuit:
![[Nodal Example 2a.png]]
At present this circuit would be very complex to solve with nodal analysis, since there are 4 unknown nodes. However, we can perform a [[Source Conversion|source conversion]] on each [[Battery|battery]] to turn it into a [[Current Sources|current source]] instead of a [[Voltage Sources|voltage source]], thus reducing the total number of nodes. 
$$
	I_{ES1}=\frac{E_{S1}}{R_1}=\frac{8\text{V}}{2\Omega}=4\text{A}
$$
$$
	I_{ES2}=\frac{E_{S2}}{R_5}=\frac{1\text{V}}{10\Omega}=100\text{mA}
$$
Our circuit now looks like this:
![[Nodal Example 2b.png]]
We can build our two equations for $V_1$ and $V_2$ as detailed above. Note that summing the *conductances* is not unique to the format approach as we did this in the general approach as well, however we didn't explicitly call this out. Recall that
$$
	G=R^{-1}
$$
Our equations therefore would look like:
$$
\begin{aligned}
	&V_1(G_1+G_2+G_3)-&V_2(G_3)&&=&&I_{S1}\\
	&V_1(2^{-1}+4^{-1}+6^{-1})-&V_2(6^{-1})&&=&&4\\
	&V_1\left(\frac{11}{12}\right)-&V_2\left(\frac{1}{6}\right)&&=&&4\\
\end{aligned}
$$
$$
\begin{aligned}
	&-V_1(G_3)+&V_2(G_3+G_4+G_5)&&=&&-I_{S2}\\
	&-V_1(6^{-1})+&V_2(6^{-1}+3^{-1}+10^{-1})&&=&&-0.1\\
	&-V_1\left(\frac{1}{6}\right)+&V_2\left(\frac{3}{5}\right)&&=&&-0.1
\end{aligned}
$$
If we multiply the first equation by 12 and the second by 30 (to remove the fractions) we get
$$
\begin{aligned}
	11V_1-2V_2&=48\\
	-5V_1+18V_2&=-3
\end{aligned}
$$
We could then go on and solve with determinants or any other method of [[Solving Systems of Linear Equations|solving linear systems]].

