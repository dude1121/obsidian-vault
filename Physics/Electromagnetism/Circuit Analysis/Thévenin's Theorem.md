---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
  - network-theorems
---
**Thévenin's Theorem** (named after French engineer Leon-Charles Thévenin) is a network analysis tool that allows us to analyze networks with sources that are not in series or parallel, and, along with its [[Norton's Theorem|sister theorem]], reduce the number of components within the circuit while producing the same characteristics at the output terminals. The theorem states:

> [!quote] Thévenin's Theorem
> Any two-terminal network can be replaced by an equivalent circuit consisting solely of a [[Voltage Sources|voltage source]] and a series [[Impedance|impedance]].

# Procedure

1. *Identify the load and remove it from the circuit. Label the terminals of the remaining two-terminal network.*
2. *Set all sources to zero and find the Thévenin-equivalent impedance. ($R_{Th}$ or $Z_{Th}$)*
3. *Solve the circuit to find $E_{Th}$. I.e. the [[Voltage|voltage]] across the two terminals.*
4. *Redraw the Thévenin circuit and re-insert the load.*

---
## Example

![[Thevenin 1a.png]]

Find the Thévenin equivalent voltage and resistance. 

Given:
- $E_{S1}=9\text{V}$
- $R_1=3\Omega$
- $R_2=6\Omega$
Find:
- $E_{Th}=$
- $R_{Th}=$

First remove the load.
![[Thevenin 1b.png]]

Then, remove the source and replace it with either a short (if it is a [[Voltage Sources|voltage source]]) or an open (if it is a [[Current Sources|current source]]). Remember to not remove any internal [[Resistance|resistances]] from the sources.
![[Thevenin 1c.png]]
Looking in from the terminals, determine the Thévenin impedance.
$$
	R_{Th}\equiv R_1||R_2
$$
$$
	R_{Th}=\frac{R_1R_2}{R_1+R_2}=\frac{(3\Omega)(6\Omega)}{3\Omega+6\Omega}=2\Omega
$$
Now, with the source added back in, find the Thévenin voltage. Since $R_2$ is in [[Parallel Circuits|parallel]] with the terminals $a$ and $b$, we can say that $E_{Th}$ is equivalent to the voltage across $R_2$.
$$
	E_{Th}=V_{R2}=\left(\frac{R_2}{R_1+R_2}\right)E_{S1}=\left(\frac{6\Omega}{3\Omega+6\Omega}\right)(9\text{V})=6\text{V}
$$
Redraw the circuit with the Thévenin equivalent components.
![[Thevenin 1d.png]]

---
Any Thévenin circuit can be converted into a Norton circuit by means of a [[Source Conversion|source conversion]].
$$
	I_{N}=\frac{E_{Th}}{R_{Th}}
$$
$$
	R_N=R_{Th}
$$
