---
tags:
  - circuit-analysis
  - electromagnetism
  - physics
---
A **phasor** is a way of representing sinusoidal [[Voltage|voltages]] and [[Current|currents]]. The name comes from combining the words "[[Phase Shift|phase]]" and "[[Vector|vector]]". Despite the name, phasors are better explained as being [[Complex Numbers|complex numbers]] and not true vectors. A phasor takes the form,
$$
A=A_{rms}\angle\theta
$$
Consider the voltage $v=170\sin(\omega t-120\degree)$. To express this as a phasor, we first convert the peak voltage into its [[Root Mean Square|rms]] value.
$$
V_{rms}=170\cdot \frac{\sqrt{ 2 }}{2}=120\text{V}
$$
The voltage could then be represented as,
$$
V=120\text{V}\angle-120\degree
$$
This phasor can be drawn on the complex plane.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[gray, very thin, step=1cm] (-4.9,-4.9) grid (4.9,4.9);
\draw[very thick, <->] (-4.5,0) -- (4.5,0) node[anchor=north west]{Re};
\draw[very thick, <->] (0,-4.5) -- (0,4.5) node[anchor=south east] {Im};
\draw[thick, ->, green] (0,0) -- (-2.4,-4.157)node[midway, above, sloped]{$120$V};
\draw[green] (0.5,-1.25) node[right]{\Large$\theta$};
\path[clip] (2,0) -- (0,0) -- (-2.4, -4.157) -- cycle;
\node[circle, draw=green, minimum size=60pt] at (0,0) (circ) {};
\draw[green] (0,0) arc (90:125:1cm);
\end{tikzpicture}
\end{document}
```
We can find its component parts by way of [[Euler's Formula]]. We can rewrite our phasor as,
$$
120\text{V}\angle-120\degree=120e^{j(-120\degree)}
$$
Then apply Euler's Formula.
$$
\begin{aligned}
120e^{j(-120\degree)}&=120\left[\cos(-120\degree) + j\sin(-120\degree)\right] \\
&=120\left(-\frac{1}{2}-j\frac{\sqrt{ 3 }}{2}\right)\\
&=-60-j 60\sqrt{ 3 }\\
&\approx-60-j 103.9
\end{aligned}
$$

