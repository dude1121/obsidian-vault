---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - voltage-divider
---
> [!info] DC and AC
> Electricity comes in two varieties: _DC_ and _AC_. These stand for _direct current_ and _alternating current_, respectively, and they refer to the fact that in DC circuits the current never changes direction, but in AC circuits it does.

A circuit is a closed loop that contains a _source_ (either a [[Voltage Sources|voltage source]] or a [[Current Sources|current source]]) and a _load_, as discussed in [[Ohm's Law]]. A circuit can be in two configuration: _series_ and _parallel_. **A series circuit is one in which there is only one path for the current to travel**. Parallel circuits have multiple paths in which current may travel and are discussed in [[Parallel Circuits]]. 

# Features of a series dc circuit

## Voltage

In a series circuit, the [[Voltage|voltage]] across all loads must be equal to the total voltage provided by the sources to the circuit. This is due to something called [[Kirchhoff’s Voltage Law]] (KVL). It states:

> [!quote] Kirchhoff's Voltage Law
> The sum of all voltages in a closed loop must equal zero.

For example, consider circuit 2:
![[Series DC Circuit.png]]
Circuit 2

We can write an equation summarizing KVL as,
$$ E_{S1}-V_{R1}-V_{R2}=0\text{V} $$
The signs of each voltage depend on the convention assumed. In this case, we assume conventional current flow, meaning that current flows from the positive side of $E_{S1}$ into $R_1$ and $R_2$. This means that the voltages across the two resistors _oppose_ the voltage from the source. In this case, we mark the voltages across the resistors as negative. In general, if we draw our loop in a given direction, say clockwise, any voltage arrow that is in the same direction as the rotation is positive in our KVL equation, and any arrow that opposes our “loop” is negative. From this we can see that
$$ E_{S1}=V_{R1}+V_{R2} $$
We can further derive a **[[Voltage Divider|voltage divider rule]]**. If we know the resistances of all the resistors and the total voltage across all of them, we can find each [[Resistor|resistor]]’s voltage without needing to know the current. In the case above with two resistors, the voltage across $R_2$ can be found by,
$$ V_{R2}=E_{S1}\left(\frac{R_2}{R_T} \right) $$
Put generally,
$$ V_{R_n}=\left(\sum_i V_{R_i}\right)\left(\frac{R_n}{\displaystyle\sum_iR_i} \right) $$
## Current

In a series circuit, the [[Current|current]] remains constant across all loads. This means that, referring to circuit 2, the current through $R_1$ is the same as the current through $R_2$. Put generally,
$$ I_T=I_1=I_2=I_n $$
This means that if we know the voltage of one component and find its current through Ohm’s Law, we can find the current through the entire series circuit. We also can of course find the total resistance in the circuit and use Ohm’s Law to find the total current.
## Resistance

[[Resistance]] in a series circuit can be treated individually, on a per-component basis, or it can be totalled and dealt with that way. In this way, we can combine all the resistances in the circuit and model the circuit as having one source, one load, no matter how many loads are actually in the circuit.

For example, in circuit 2, the total resistance is given by,
$$ R_T=R_1+R_2 $$
But in general,
$$ R_T=\sum_nR_n=R_1+R_2+...+R_n $$
## Sources in series

Much like we can combine loads into one “effective” load, we can also combine sources, provided their polarities are _aiding_. Two sources are said to be aiding one another if the positive terminal of one source connects directly to the negative terminal of the second source. We can also of course add sources that are not aiding but rather _opposing_, however this means the two sources total voltage will be the one source _minus_ the other, not plus.
$$
	E_{ST}=\sum_nE_{Sn}=E_{S1}+E_{S2}+...+E_{Sn}
$$
# Features of a series ac circuit
