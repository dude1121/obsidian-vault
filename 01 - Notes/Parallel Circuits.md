---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - current-divider
---
Parallel circuits, unlike [[Series Circuits|series circuits]], have more than one path for current to flow. They are typically split up into multiple “branches.”

# Features of a parallel dc circuit

## Voltage

The [[Voltage|voltage]] in a parallel circuit is the same for each branch of the circuit.
![[Parallel DC Circuit.png]]
Circuit 3

In circuit 3, the voltages across all three resistors are equivalent. This is similar to how current is treated in [Series DC Circuits](https://www.notion.so/Series-DC-Circuits-18b1bf06699047ed96fa0e8c62922a17?pvs=21).

$$ E_{S_1}=V_{R_1}=V_{R_2}=V_{R_3} $$

If we were to number each branch $1~-~n$, we could generalize this as,

$$ V_1=V_2=V_n $$

Note that this still satisfies [[Kirchhoff’s Voltage Law]]. If we were to draw a clockwise loop in between $R_1$ and $R_2$, say, we would obtain the KWL equation:

$$ V_{R_1}-V_{R_2}=0\text{V} $$

which could be rearranged to,

$$ V_{R_1}=V_{R_2} $$
## Current

Unlike a series dc circuit, [[Current|current]] is not equivalent everywhere in a parallel circuit. It is proportional to the resistance of each branch in the circuit. To find the current in a given branch when the resistance is known, as in Circuit 3, we can use the source voltage as the branch voltage to calculate the branch current via Ohm’s Law.
$$ I_1=\frac{V_{R_1}}{R_1}=\frac{15\text{V}}{100\Omega}=150\text{mA} $$
We can do the same for branches 2 and 3:
$$
	I_2=\frac{V_{R_2}}{R_2}=\frac{15\text{V}}{330\Omega}=45.455\text{mA}
$$
$$
	I_3=\frac{V_{R_3}}{R_3}=\frac{15\text{V}}{550\Omega}=27.273\text{mA}
$$
Examining the circuit more closely, we see that as the current leaves the positive terminal of $E_{S1}$, it is split amongst the three branches. However, there is only one path that leads back to the negative terminal of the battery. We can infer from this that the total current in this circuit must be the sum of the three currents we found. That is,
$$
	I_T=I_1+I_2+I_3=150\text{mA}+45.455\text{mA}+27.273\text{mA}=222.728\text{mA}
$$
This fact, that the total current is the sum of all the branch currents, sounds familiar to the way voltage is dealt with in a series circuit. This is due to another one of Gustav Kirchhoff's law, namely [[Kirchhoff's Current Law]] (KCL). It states:

> [!QUOTE] Kirchhoff's Current Law 
> The algebraic sum of currents in a network of conductors meeting at a node must equal zero.

In the case above, if we take the junction above $R_1$, we see that there are 3 currents related to that node: the entering current, $I_T$; the current going to $R_1$, $I_1$; and the current going to the rest of the circuit, $I_{2+3}$. To use KCL, we first assume a direction for each current, then build the KCL equation similar to KVL. Currents assumed to be entering the node are positive, and currents assumed to be leaving are negative. It does not matter whether these currents actually are leaving or entering, so long as the convention is consistent.
$$
	I_T-I_1-I_{2+3}=0\text{A}
$$
## Resistance

Above we calculated the total current for circuit 3. We also were given the source voltage. This means we could find the total [[Resistance|resistance]] for this circuit. 
$$
	R_T=\frac{E_{S1}}{I_T}=\frac{15\text{V}}{222.728\text{mA}}=67.347\Omega
$$
This is an interesting result. The total resistance is lower than any one of the resistors in the circuit. This is because in a parallel circuit, the resistance drops the more branches that are added to the circuit. The lower the resistance of the branch, the lower that branch will drag the total resistance down. To find the total resistance in a parallel circuit we use the following formula:
$$
	R_T=\left(R_1^{-1}+R_2^{-1}+...+R_n^{-1}\right)^{-1}
$$
Using our example above, let's find the total resistance using this method.
$$
R_T=\left(100\Omega^{-1}+330\Omega^{-1}+550\Omega^{-1}\right)^{-1}
$$
Recall that [[Conductance|conductance]] is the reciprocal of resistance.
$$
	R_T=(10\text{mS}+3.030\text{mS}+1.818\text{mS})^{-1}=(14.848\text{mS})^{-1}=67.349\Omega
$$
Compare this to the result we got by using [[Ohm's Law]] above and see that these answers are nearly identical, as we would expect. In general, then,
$$
	R_T=\left(\sum_iR_i^{-1}\right)^{-1}
$$
Or, in terms of conductance ($G$),
$$
	R_T=G_T^{-1}=\sum_iG_i
$$
There is another method to find the total resistance known as *product over sum*. This works with two loads in parallel. Say we have two resistors in parallel, $R_1$ and $R_2$ with values $330\Omega$ and $1k\Omega$, respectively. To find their equivalent resistance, we can user product over sum.
$$
	R_T=\frac{R_1\cdot R_2}{R_1+R_2}=\frac{330\Omega\cdot1\text{k}\Omega}{330\Omega+1\text{k}\Omega}=248.12\Omega
$$
A special case arises when the resistances in parallel are equal. In that case, the equivalent resistance is equal to the value of the resistors divided by the number of equivalent resistors. For example, say there are 4 resistors of $100\Omega$ in parallel with one another.
$$
	R_T=\frac{R}{N}=\frac{100\Omega}{4}=25\Omega
$$

# Features of a parallel ac circuit
