---
tags:
  - electrical-engineering
  - electrical-machines
---
A **dc motor drive** is a [[Driver Circuit|driver]] for a [[DC Machine#As a Motor|dc motor]] that allows us to control the performance of a dc motor using a dc source.
# Four quadrant operation
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[very thick, <->] (-3,0) -- (3,0) node[anchor=north west] {$n$};
\draw[very thick, <->] (0,-3) -- (0,3) node[anchor=south east] {$\tau$};
\draw (1.5,1.5) node[anchor=center] {I};
\draw (1.5,1) node[anchor=center] {Forward Motor};
\draw (-1.5,1.5) node[anchor=center] {II};
\draw (-1.5,1) node[anchor=center] {Reverse Motor};
\draw (-1.5,-1) node[anchor=center] {III};
\draw (-1.5,-1.5) node[anchor=center] {Reverse Braking};
\draw (1.5,-1) node[anchor=center] {IV};
\draw (1.5,-1.5) node[anchor=center] {Forward Braking};
\end{tikzpicture}
\end{document}
```
We can break down a dc motor's operation as shown above. It can be doing one of four things based on 1) the direction of rotation and 2) the direction of torque. To operate in all four quadrants, we make use of a full bridge or [[H-Bridge|h-bridge]] circuit to control the motor.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[](V2){} to[vsource, l=$\mathcal{V}_\mathrm{s}$] ++(0,5)
-- ++(2,0) node[circ](C1){}

(C1) to[short] ++(3,0) node[circ](A){} to[short] ++(0,-0.5) node[nigfete, bodydiode, anchor=D](Q1){$Q_1$} 
(Q1.G) node[ocirc]{} node[left]{$G_1$}
(Q1.S) to[short] ++(0,-0.5) node[circ](B){} node[left]{A}
to[short] ++(0,-0.5) node[nigfete, bodydiode, anchor=D](Q2){$Q_2$}
(Q2.G) node[ocirc]{} node[left]{$G_2$}
(Q2.S) to[short] ++(0,-0.5) node[circ]{} node[ground](G){}

(A) -- ++(5,0) to[short] ++(0,-0.5) node[nigfete, bodydiode, anchor=D](Q3){$Q_3$}
(Q3.G) node[ocirc]{} node[left]{$G_3$}
(Q3.S) to[short] ++(0,-0.5) node[circ](C){} node[right]{B}
to[short] ++(0,-0.5) node[nigfete, bodydiode, anchor=D](Q4){$Q_4$}
(Q4.G) node[ocirc]{} node[left]{$G_4$}
(Q4.S) to[short] ++(0,-0.5) to[short] (G)
(V2) to[short] (V2 |- G) to[short] (G)

(C1) to[cC, l=$C_1$] (C1 |- G) node[circ]{}

(B) to[R, l=$R_o$] ++(2.5,0) to[Telmech=M,n=motor] (C)
;
\end{circuitikz}
\end{document}
```
$R_{\mathrm{o}}$ is the internal resistance of the motor. Much like the inverter, there are two ways we can operate this motor: $100\%$ low-side or $50\%$ offset.
## $100\%$ low-side
If we want to operate the motor in the first quadrant, we can make the duty cycle for $\mathrm{B}$ $D_{\mathrm{B}}=0\%$. This pulls $Q_{4}$ high permanently. We then can alter the speed of the motor by varying the duty cycle on $\mathrm{A}$, where the voltage across the motor $V_{\mathrm{M}}$ will be
$$
\begin{align}
V_{\mathrm{M}}&=V_{\mathrm{A}}=D_{\mathrm{A}}\mathcal{V_{\mathrm{s}}}
\end{align}
$$
For quadrant $\mathrm{II}$ operation we do much the same thing. We turn $Q_{2}$ on permanently and we vary the duty cycle on $Q_{3}$. In this case,
$$
V_{\mathrm{M}}=V_{\mathrm{B}}=D_{\mathrm{B}}\mathcal{V}_{\mathrm{s}}
$$
Operating in quadrants $\mathrm{III}$ and $\mathrm{IV}$ depends solely on the applied voltage to the motor $V_{\mathrm{M}}$. If $V_{\mathrm{M}}>E_{\mathrm{o}}$ (where $E_{\mathrm{o}}$ is the [[DC Machine#Counter-emf|counter-emf]] generated by the motor), then the machine acts as a motor and we operate in quadrants $\mathrm{I}$ and $\mathrm{II}$. However, if $V_{\mathrm{M}}<E_{\mathrm{o}}$, now the machine is acting as a generator, and applies a voltage back to the source. This is known as *regenerative braking* and it allows us to use the kinetic energy in the motor to charge our voltage source slightly. If we are in quadrant $\mathrm{I}$ and $V_{\mathrm{M}}<E_{\mathrm{o}}$, we enter quadrant $\mathrm{IV}$ (and likewise if we were in quadrant $\mathrm{II}$ then we enter quadrant $\mathrm{III}$). 

We can control how quickly the motor stops by adjusting the armature current. We can do this by remembering that the armature current will be determined by,
$$
I_{\mathrm{Arm}}=\frac{V_{\mathrm{M}}-E_{\mathrm{o}}}{R_{\mathrm{o}}}
$$
Therefore, for a given $E_{\mathrm{o}}$, if we decrease $V_{\mathrm{m}}$ even further, we increase $I_{\mathrm{Arm}}$ (the negative value of $I_\mathrm{Arm}$ indicates that the current is travelling back to the source). This increase in current means the machine is dissipating energy faster and will in turn run out of energy and come to a stop quicker.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[](V2){} to[vsource, l=$\mathcal{V}_\mathrm{s}$] ++(0,5)
-- ++(2,0) node[circ](C1){}

(C1) to[short] ++(3,0) node[circ](A){} to[cvsource, a=$D_\mathrm{A}\mathcal{V}_\mathrm{s}$, l=$V_\mathrm{M}$] ++(0,-2.5) node[circ](B){} node[left]{A}
to[short] ++(0,-0.5) node[ocirc]{} to[open, l=$Q_2$] ++(0,-1.5) node[ocirc]{} to[short] ++(0,-0.5) node[circ]{} node[ground](G){}

(A) -- ++(5,0) to[short] ++(0,-0.5) node[ocirc]{} to[open, l=$Q_3$] ++(0,-1.5) node[ocirc]{} to[short] ++(0,-0.5) node[circ](C){} node[right]{B}
to[short] ++(0,-0.5) node[ocirc]{} to[short, l=$Q_4$] ++(0,-1.5) node[ocirc]{} to[short] ++(0,-0.5) to[short] (G)
(V2) to[short] (V2 |- G) to[short] (G)

(C1) to[cC, l=$C_1$] (C1 |- G) node[circ]{}

(B) to[R, l=$R_o$] ++(2.5,0) to[Telmech=M,n=motor] (C)

(motor.south) node[above, yshift=3mm, xshift=-2mm]{$+$}
(motor.north) node[above, yshift=3mm, xshift=2mm]{$-$}
(motor.left) node[above]{$E_\mathrm{o}$}
;
\end{circuitikz}
\end{document}
```
Above is a simplified circuit when the motor is moving forward. $Q_{2}$ and $Q_{3}$ are replaced with opens and $Q_{4}$ is replaced with a short. $Q_{1}$ is replaced with a dependant voltage source which we call $V_{\mathrm{M}}$. If $V_{\mathrm{M}}<E_{\mathrm{o}}$ then the path of current goes from $E_{\mathrm{o}}$, through $V_{\mathrm{M}}$ (which in reality is through the body diode of the [[Metal Oxide-Semiconductor Field Effect Transistor|MOSFET]] $Q_{1}$), and back through the voltage source $\mathcal{V}_{\mathrm{s}}$, thus charging $\mathcal{V}_{\mathrm{s}}$. As power is dissipated via the internal resistance $R_{\mathrm{o}}$, the generator slows down, and $E_{\mathrm{o}}$ decreases. If the goal is to stop the motor entirely, we can make $D_{\mathrm{A}}=0$ and the motor will simply stop once $E_{\mathrm{o}}=0\ \mathrm{V}$. However, if we want to simply slow down the motor we can adjust $V_{\mathrm{M}}$ until the motor's speed decreases to our desired level.

In an application like a vehicle, we might not know if the user wants to stop the motor or simply slow it down. Or, if we want to stop the motor, abruptly removing $V_{\mathrm{M}}$ may draw too much current and damage the system. To maintain a safe current therefore and stop the motor more slowly, a current feedback system is typically used. 

The PWM signal to the MOSFETs will typically be controlled by some sort of [[Microprocessor|microprocessor]], and this microprocessor will simultaneously monitor the current. If the current becomes too large, the processor may increase the duty cycle (and therefore $V_{\mathrm{M}}$) to compensate. If the current becomes too small (i.e. if $E_{\mathrm{o}}$ approaches $V_{\mathrm{M}}$), the processor may decrease the duty cycle to keep the motor slowing down. Recall that the [[Torque|torque]] of the motor is related to its armature current, so monitoring the current allows us to monitor the torque as well.

We can determine the necessary applied terminal voltage by summing the two voltages in series across the terminals $\mathrm{A-B}$.
$$
\begin{align}
V_{\mathrm{M}}&=E_{\mathrm{o}}+V_{R_{o}} \\
&\boxed{=kn + I_{\mathrm{Arm}}R_{o}} \\
\end{align}
$$
where $k$ is the voltage-speed constant in units of $[\pu{ V/\! rpm}]$ and $n$ is the motor speed in $[\mathrm{rpm}]$. Since torque is related to current by,
$$
\tau=\frac{Z\Phi I}{2\pi}
$$
we can determine an expression for the terminal voltage in terms of speed and torque.
$$
\boxed{V_{\mathrm{M}}=kn+\frac{\tau R_{\mathrm{o}}}{c}}
$$
where $\displaystyle c=\frac{Z\Phi}{2\pi}$. Since $k$, $c$, and $R_{\mathrm{o}}$ are all constants unique to a given motor, $V_{\mathrm{M}}$ becomes a function of speed $n$ and torque $\tau$.