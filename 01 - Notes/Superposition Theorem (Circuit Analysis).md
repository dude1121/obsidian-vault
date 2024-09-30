---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - network-theorems
---
**Superposition Theorem** is a technique that allows us to analyze networks that have two or more sources that are not in series or parallel. The theorem states:

> [!quote] Superposition Theorem
> The [[Current|current]] through, or [[Voltage|voltage]] across, any element of a network is equal to the algebraic sum of the currents or voltages produced independently by each source.

Consider the following circuit:
![[Superposition 1a.png]]
To examine this circuit with each source independently, we much remove each source from the circuit. Setting a [[Voltage Sources|voltage source]] to zero [[Volts|volts]] is almost like placing a short circuit across its terminals, therefore we can replace a voltage source with a "jumper", a direct connection of zero ohms. ***Any internal [[resistance]] associated with the source must remain in the circuit***. 

Setting a [[Current Sources|current source]] to zero [[Amperes|amps]] is like replacing it with an open circuit, therefore when removing a current source from a network, replace it with an open circuit of infinite ohms. Once again, **any internal resistance associated with the source must remain in the circuit***.

In the circuit above, lets first remove the current source.
![[Superposition 1b.png]]
Since the space where $I_{S1}$ was is now an open circuit, it is almost as if it does not exist. Current will only travel in this small series circuit with $E_{S1}$, $R_1$, and $R_2$. In this case,
$$
\begin{aligned}
	V_{R1}'&=\left(\frac{R_1}{R_1+R_2}\right)E_{S1}\\
	&=\left(\frac{12\Omega}{12\Omega+6\Omega}\right)(36\text{V})\\
	&=24\text{V}
\end{aligned}
$$
which means that by [[Kirchhoff’s Voltage Law|KVL]],
$$
\begin{aligned}
	E_{S1}-V_{R1}'-V_{R2}'&=0\text{V}\\
	V_{R2}'&=E_{S1}-V_{R1}'\\
	&=36\text{V}-24\text{V}\\
	&=12\text{V}
\end{aligned}
$$
The current therefore is given by,
$$
\begin{aligned}
	I_T'=I_{R1}'&=\frac{V_{R1}'}{R_1}\\
	&=\frac{24\text{V}}{12\Omega}\\
	&=2\text{A}
\end{aligned}
$$
Now that we have our values with $E_{S1}$ only, let's examine the circuit with only $I_{S1}$.
![[Superposition 1c.png]]
This now becomes a parallel circuit, with a current source and two branches. We can use the current divider rule to find the current through each branch.
$$
\begin{aligned}
	I_{R2}''&=\left(\frac{R_1}{R_1+R_2}\right)I_{S1}\\
	&=\left(\frac{12\Omega}{12\Omega+6\Omega}\right)9\text{A}\\
	&=6\text{A}
\end{aligned}
$$
By [[Kirchhoff's Current Law|KCL]],
$$
\begin{aligned}
	I_{S1}+I_{R1}''-I_{R2}''&=0\text{A}\\
	I_{R1}''&=I_{R2}''-I_{S1}\\
	&=6\text{A}-9\text{A}\\
	&=-3\text{A}
\end{aligned}
$$
Note that we keep the same convention as before. Even though we know that with the current source only this current is actually travelling in the opposite direction, we do not change our initial assumed direction.

The voltages can be found now for each [[Resistor|resistor]].
$$
	V_{R1}''=I_{R1}''R_1=(-3\text{A})(12\Omega)=-36\text{V}
$$
$$
	V_{R2}''=-V_{R1}''=-(-36\text{V})=36\text{V}
$$
Now that we've calculated the voltage and current for each component using each source individually, we can combine the values we found previously to find the actual voltages and currents.
$$
	V_{R1}=V_{R1}'+V_{R1}''=24\text{V}+(-36\text{V})=-12\text{V}
$$
$$
	I_{R1}=I_{R1}'+I_{R1}''=2\text{A}+(-3\text{A})=-1\text{A}
$$
These negative values tell us that our initial assumption was incorrect, and that the current is actually travelling *into* the source, not out from it.
$$
	V_{R2}=V_{R2}'+V_{R2}''=12\text{V}+36\text{V}=48\text{V}
$$
$$
	I_{R2}=I_{R2}'+I_{R2}''=2\text{A}+6\text{A}=8\text{A}
$$
In a real situation, you would not need to use superposition for all these values. If you found only the currents or voltages you could then use [[Ohm's Law]] at the end to find the other. However this demonstration shows that all values can be found using only superposition.