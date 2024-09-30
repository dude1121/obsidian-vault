---
tags:
  - electromagnetism
  - physics
---
**Impedance** is the total opposition to the flow of [[Charge|charge]] within a circuit. It is made up of both [[Resistance|resistance]] and [[Reactance|reactance]]. Impedance is a [[Vector|vector]] but crucially it is *not* a [[Phasor|phasor]] since it is constant and not time-varying. Impedance is denoted using $Z$ and it is [[Units of Measurement|measured]] in [[Ohms]] $[\Omega]$. The inverse of impedance is [[Admittance|admittance]].
$$
Z=R+jX
$$
We can write the impedance either as a sum of its real and [[Complex Numbers|imaginary]] parts or as a vector with a magnitude and direction. For example, consider the circuit below:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[european voltages]
\draw
(0,0) to[R,l=$R$,a=$100\Omega$] (0, 3)
to[L,l=$L$, a=$330$mH] (0,6)
to[C,l=$C$, a=$50\mu$F] (0,9)
to[short, -o] (3,9)
(0,0) to[short, -o] (3,0)
;
\end{circuitikz}
\end{document}
```

If the frequency is $f=120\text{Hz}$, then
$$
\begin{aligned}
\omega&=2\pi f&X_{C}&=(\omega C)^{-1}&X_{L}&=\omega L\\
&=2\pi(120\text{Hz})&&=((240\pi)(50\mu \text{F}))^{-1}&&=(240\pi)(330\text{mH})\\
&=240\pi&&=26.526\Omega&&=248.814\Omega\\
&&&=-j 26.526\Omega&&=j 248.814\Omega\\
X_{T}&=X_{L}+X_{C}&Z_{T}&=R+X_{T}\\
&=j 248.814\Omega-j 26.526\Omega&&=100\Omega+j 222.288\Omega\\
&=j 222.288\Omega&&=243.746\Omega\angle 65.779\degree
\end{aligned}
$$
The total impedance of this circuit then is $Z_{T}=100\Omega+j 222.288\Omega$. We can convert this into its magnitude and direction the same way we do for phasors.

# Impedance Diagrams

We can model the impedances in a circuit using an impedance diagram, that shows all the various impedances present as vectors.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[very thin, gray, step=1cm](-0.9,-5.9) grid (5.9,5.9);
\draw[very thick, <->] (-0.5,0) -- (5.5,0) node[anchor=north west]{$x$};
\draw[very thick, <->] (0,-5.5) -- (0,5.5) node[anchor=south east]{$y$};
\draw[cyan,thick,->](0,0) -- (2,0) node[anchor=south west]{$R$};
\draw[green,thick,->](0,0) -- (0,4.96)node[right]{$X_L$};
\draw[red,thick,->](0,0)--(0,-0.52)node[right]{$X_C$};
\draw[orange,thick,->](0,0)--(2,4.446)node[right]{$Z_T$};
\end{tikzpicture}
\end{document}
```
This can be helpful in visualizing the various impedances present in a circuit, as well as if the circuit is primarily inductive or capacitive.

# Impedance at Resonance

Note that,
$$
Z=R_{T}+jX_{T}
$$
and
$$
X_{T}=X_{C}+X_{L}
$$
where $X_{C}$ will always be negative and $X_{L}$ will always be positive. If $X_{C}=X_{L}$, then $X_{T}=0\Omega$. This means that the impedance will be entirely real, with no imaginary component. For any circuit, there exists a frequency that will make the reactances cancel out. 
$$
\begin{aligned}
X_{L}&=X_{C}\\
2\pi fL&=\frac{1}{2\pi fC}\\
(2\pi)^2LCf&=\frac{1}{f}\\
f^2&=\frac{1}{(2\pi)^2LC}\\
f&=\frac{1}{\sqrt{ (2\pi)^2LC }}\\
&=\frac{1}{2\pi \sqrt{ LC }}
\end{aligned}
$$
This frequency is called the [[Resonance|resonance]] frequency.
