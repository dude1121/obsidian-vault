---
tags:
  - reduce-and-return
  - circuit-analysis
  - electromagnetism
  - physics
---
Often, a circuit is neither purely [[Series Circuits|series]] nor purely [[Parallel Circuits|parallel]]. Instead, it is some sort of combination of the two. Consider the following circuit.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, a=$10$V] (0,-4) -- (3,-4) node[ground]{} -- (6,-4)
(0,0) to[R, l=$R_1$, a=$5\Omega$,v<=$V_{R1}$, voltage shift=4] (3,0) 
to[R, l_=$R_2$, a^=$10\Omega$, v<=$V_{R2}$, voltage shift=4, *-*] (3,-4)
(3,0) to[R, l=$R_3$, a=$4\Omega$, v<=$V_{R3}$, voltage shift=4] (6,0)
to[R, l_=$R_4$, a^=$6\Omega$, v<=$V_{R4}$, voltage shift=4] (6,-4)
;
\end{circuitikz}
\end{document}
```
Here there are four resistors in a combination of series and parallel. We could express their relation with notation. In this case,
$$
	R_1,R_2||(R_3,R_4)
$$
The commas mean the two components are in series, and the double bar means they are in parallel. The notation above can be read as "[[Resistor]] $R_1$ is in series with $R_2$, which is in parallel with $R_3$ and $R_4$, who are in series with each other." Examining the circuit in this way helps us break it down and find a way to solve it. One way to do this is the "Reduce and Return" method. 

The circuit above is also known as a **ladder network**, since it resembles a ladder turned on its side. These networks are common and relatively easy to solve with the reduce and return method.
# Reduce and Return
After analyzing the configuration of the resistors, we start as far away from the source as possible and work our way back. To begin, notice that $R_3$ and $R_4$ are in series with one another. We could call their combined [[Resistance|resistance]] $R_T'$. 
$$
	R_T'=R_3+R_4=4\Omega+6\Omega=10\Omega
$$
We can then re-draw our circuit with our new $R_T'$ resistance.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, a=$10$V] (0,-4) -- (3,-4) node[ground]{} -- (6,-4)
(0,0) to[R, l=$R_1$, a=$5\Omega$,v<=$V_{R1}$, voltage shift=4] (3,0) 
to[R, l_=$R_2$, a^=$10\Omega$, v<=$V_{R2}$, voltage shift=4, *-*] (3,-4)
(3,0) -- (6,0)
to[R, l_=$R_T'$, a^=$10\Omega$, v<=$V_{RT'}$, voltage shift=4] (6,-4)
;
\end{circuitikz}
\end{document}
```
This is still not a purely parallel or series circuit, so we have to continue. Notice now that $R_2$ and $R_T'$ are in parallel. We can call their combined resistance $R_T''$. 
$$
	R_T''=\frac{R_2R_T''}{R_2+R_T''}=\frac{(10\Omega)(10\Omega)}{10\Omega+10\Omega}=5\Omega
$$
Redrawing the circuit again, we are left with just $R_1$ and $R_T''$.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, a=$10$V] (0,-4) -- (3,-4) node[ground]{}
(0,0) to[R, l=$R_1$, a=$5\Omega$,v<=$V_{R1}$, voltage shift=4] (3,0)
to[R, l_=$R_T''$, a^=$5\Omega$, v<=$V_{RT''}$, voltage shift=4] (3,-4)
;
\end{circuitikz}
\end{document}
```
We could stop here, as this is now a simple series circuit, but to complete the process, let's combine these two resistances. 
$$
	R_T=R_1+R_T''=5\Omega+5\Omega=10\Omega
$$
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[battery, l=$E_{S1}$, a=$10$V] (0,-4) -- (3,-4) node[ground]{}
(0,0) -- (3,0)
to[R, l_=$R_T$, a^=$10\Omega$, v<=$V_{RT}$, voltage shift=4] (3,-4)
;
\end{circuitikz}
\end{document}
```
If the problem were asking us to find the total [[Current|current]] in the circuit, for example, this is now a trivial task, something that wasn't readily apparent at the beginning. 