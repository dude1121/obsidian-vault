---
tags:
  - electrical-engineering
  - electronics
---
A **three phase inverter** is an [[Inverter|inverter]] circuit that produces a three phase [[AC Electricity|ac signal]]. These circuits have applications in [[Brushless DC Motor|brushless dc motors]], ac power supplies, or renewable energies.
# Sample circuit
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[](B){} to[vsource, l=$V_s$] ++(0,6) node[](A){}

(A) to[short] ++(1.5,0) node[circ](C){} to[cC, l=$C$] ++(0,-6) node[circ]{}

(C) to[short] ++(2,0) node[circ](F){} to[short] ++(0,-0.5) node[nigfete, anchor=D, bodydiode](Q1){} node[right]{$Q_1$}
(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.S) node[circ](D){} to[short] ++(0,-2.25) node[nigfete, anchor=D, bodydiode](Q2){} node[right]{$Q_2$}
(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] (Q1.S |- B) node[circ](E){} to[short] (B)

(F) to[short] ++(2.5,0) node[circ](G){}  to[short] ++(0,-0.5) node[nigfete, anchor=D, bodydiode](Q3){} node[right]{$Q_3$}
(Q3.G) node[ocirc]{} node[left]{$G_3$}
(Q3.S) to[short] ++(0,-1) node[circ](H){} to[short] ++(0,-1.25) node[nigfete, anchor=D, bodydiode](Q4){} node[right]{$Q_4$}
(Q4.G) node[ocirc]{} node[left]{$G_4$}
(Q4.S) to[short] (Q4.S |- E) node[circ](I){} to[short] (E)

(G) to[short] ++(2.5,0) node[circ](K){} to[short] ++(0,-0.5) node[nigfete, anchor=D, bodydiode](Q5){} node[right]{$Q_5$}
(Q5.G) node[ocirc]{} node[left]{$G_5$}
(Q5.S) to[short] ++(0,-2) node[circ](L){} to[short] ++(0,-0.25)
node[nigfete, anchor=D, bodydiode](Q6){} node[right, yshift=-5mm, xshift=3mm]{$Q_6$}
(Q6.G) node[ocirc]{} node[left]{$G_6$}
(Q6.S) to[short] (Q6.S |- E) node[circ](M){} to[short] (I)

(D) to[short] ++(6,0) node[ocirc](N){} node[right]{A}
(H) to[short] (H -| N) node[ocirc]{} node[right]{B}
(L) to[short] (L -| N) node[ocirc]{} node[right]{C}

;
\end{circuitikz}
\end{document}
```
This inverter circuit consists of three discrete stages:
1. The three half bridges (or sometimes called the 'legs'). These legs make up each phase.
2. The gate driver. This driver may be controlled with three discrete half-bridge driver ICs or possible one three phase driver IC. 
3. The control. This is controlled by three discrete [[Pulse Width Modulation|PWM]] signals. These signals allow us to determine whether the output signal is a square wave or sine wave.
# Three phase inverter outputs
The output of a three phase inverter can be either a [[Square Wave|square wave]] or a [[Sinusoidal Function|sine wave]]. 
## Square wave output
To obtain a square wave output, we keep the [[Duty Cycle|duty cycle]] $D$ constant in the first half cycle (from $0\degree-180\degree$). In the second half cycle, we pull the half bridge low so that that phase's voltage is $0\ \mathrm{V}$ for the entire half cycle. Each phase is staggered by a phase shift of $120\degree$ ($\frac{2\pi}{3}$). 
![[three-phase-inverter-square.png]]
The waveforms for this set up is shown above. Note that these phases must remain balanced, otherwise these relationships can become erratic.
## Sine wave output
For a sine wave output, we use the same method for a [[Inverter#Sine wave output|single phase sine wave output]]. That is,
$$
v_{\varphi}=\frac{V_{s}}{2}+\frac{V_{\mathrm{p-p}}}{2}\sin(\omega t+\theta)
$$
The only thing that changes between the phases in this case is the [[Phase Shift|phase shift]]. For phase A, we typically assume this to be $\theta=0$, meaning that $\theta_{B}=-\frac{2\pi}{3}$ and $\theta_{C}=\frac{2\pi}{3}$.

Our line voltages can therefore be defined as,
$$
\begin{align}
v_{\mathrm{AB}}&=\frac{\sqrt{ 3 }}{2}V_{\mathrm{p-p}}\sin\left( \omega t+\frac{\pi}{6} \right) \\
v_{\mathrm{BC}}&=\frac{\sqrt{ 3 }}{2}V_{\mathrm{p-p}}\sin\left( \omega t-\frac{\pi}{2} \right) \\
v_{\mathrm{CA}}&=\frac{\sqrt{ 3 }}{2}V_{\mathrm{p-p}}\sin\left( \omega t+\frac{5\pi}{6} \right) \\
\end{align}
$$
Note that $V_{\mathrm{p-p}}$ can range only from $0-V_{s}$. 
