---
tags:
  - electrical-engineering
  - electronics
---
A **phase shift circuit** is a circuit that can generate pulses for an [[Rectifier#Controlling the output voltage|SCR rectifier]] to adjust the phase shift angle $\delta$ in the rectifier.
# Example
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[scale=0.6, transform shape]
\draw
        (0,0) node[ocirc](AC1){} node[left]{$AC1$} to[R, n=R1] ++(2,0) node[circ](A){}
        to[R, l2_=$R_2$ and $1\mathrm{k}\Omega$] ++(0,-2) node[rground]{}
        (R1) node[yshift=10mm, xshift=-2mm]{$R_1$} node[yshift=5mm]{$10\mathrm{k}\Omega$}
        (A) to[short] ++(1,0) node[circ](B){} to[short] ++(1,0)
        node[op amp, anchor=+, yscale=-1](U1){}

        (U1.center) node[]{$U_1$}

        (0,-3) node[ocirc](AC2){} node[left]{$AC2$} to[R, n=R3] ++(2,0) node[circ](C){}
        to[R, l2_=$R_4$ and $1\mathrm{k}\Omega$] ++(0,-2) node[rground]{}
        (R3) node[yshift=10mm, xshift=-2mm]{$R_3$} node[yshift=5mm]{$10\mathrm{k}\Omega$}
        (C) to[short] ++(1.5,0) node[circ](D){} to[short] ++(0.5,0)
        node[op amp, anchor=+, yscale=-1](U2){}

        (U2.center) node[]{$U_2$}

        (U1.-) to[short] (U1.- -| D) to[short] (D)
        (U2.-) to[short] (U2.- -| B) to[short] (B)

        (U1.out) to[short] ++(1,0) node[circ](E){} to[R, l=$R_5$, a=$10\mathrm{k}\Omega$] ++(0,2) node[vcc]{5V}

        (E) to[short] ++(0,-0.5) to[R,l2_=$R_6$ and $10\mathrm{k}\Omega$] ++(2,0) node[circ](F){} to[cC, l2=$C_1$ and $0.1\mu\mathrm{F}$] ++(0,-1) node[rground]{}

        (E) to[short] ++(2,0) node[circ](DP){} to[short] ++(2,0) node[nand port, anchor=in 1](U3){}

        (U3.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$} node[yshift=8mm, xshift=-7mm]{$U_3$}

        (DP) to[short] ++(0,0.5) node[circ]{} node[above]{DP}

        (U2.out) to[short] ++(1,0) node[circ](H){} to[R, l2=$R_7$ and $10\mathrm{k}\Omega$] ++(0,1.5) node[vcc]{} node[above=4mm]{5V}

        (H) to[short] ++(0,-1) to[R,l=$R_8$, a=$10\mathrm{k}\Omega$] ++(2,0) node[circ](I){} to[cC, l2=$C_2$ and $0.1\mu\mathrm{F}$] ++(0,-1) node[rground]{}

        (H) to[short] ++(2,0) node[circ](DN){} to[short] ++(2,0) node[nand port, anchor=in 2](U4){}

        (U4.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

        node[yshift=8mm, xshift=-7mm]{$U_4$}

        (DN) to[short] ++(0,0.5) node[circ]{} node[above]{DN}

        (F) to[short] ++(1.5,0) node[](F1){} to[short] (F1 |- U4.in 1) to[short] (U4.in 1)

        (F1) node[above, xshift=-5mm]{DPD}

        (I) to[short] ++(1.75,0) node[](I1){} to[short] (I1 |- U3.in 2)

        to[short] (U3.in 2)

        (I1) node[above, xshift=-5mm]{DND}

        (U3.out) to[short] ++(1,0) node[nand port, anchor=in 1](U5){}

        (U5.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

        node[yshift=8mm, xshift=-7mm]{$U_5$}

        (U4.out) to[short] ++(0.5,0) node[](U4A){} to[short] (U4A |- U5.in 2)

        to[short] (U5.in 2)

        (U5.out) to[short] ++(2,0)

        node[dipchip, num pins=12, hide numbers, no topmark, external pins width=0.25, anchor=bpin 2](U6){$U_6$}

        (U6.bpin 1)

        node[left, yshift=2mm, font=\tiny]{1}

        node[right, font=\small] {A}

        (U6.bpin 2)

        node[left, yshift=1mm, font=\tiny]{2}

        node[right, font=\small] {B}

        (U6.bpin 4)

        node[left, yshift=1mm, font=\tiny]{14}

        node[right, font=\small] {C}

        (U6.bpin 5)

        node[left, yshift=1mm, font=\tiny]{15}

        node[right, font=\small] {R/C}

        (U6.bpin 6)

        node[left, yshift=2mm, font=\tiny]{3}

        node[right, font=\small] {CLR}

        (U6.bpin 7)

        node[right, yshift=1mm, font=\tiny]{4}

        node[left, font=\small] {$\bar{\mathrm{ Q }}$}

        (U6.bpin 9)

        node[right, yshift=1mm, font=\tiny]{13}

        node[left, font=\small] {Q}

        (U6.bpin 1) node[ocirc, xshift=-1mm, scale=1.5]{} to[short] ++(-0.5,0) node[circ](P1){}

        to[short] ++(0,1) to[short] ++(0.5,0) node[rground]{}

        (U6.bpin 4) to[short] (U6.bpin 4 -| P1) to[short] (P1)

        (U6.bpin 5) to[short] ++(-2,0) node[circ](P15){} to[short] ++(-1,0) to[short] ++(0,-0.5) to[cC, l2_=$C_3$ and $1\mu\mathrm{F}$] ++(0,-1) to[short] ++(0,-0.75) node[rground]{}

        (U6.bpin 6) node[ocirc, xshift=-1mm, scale=1.5]{} to[short] ++(-0.75,0) node[circ](P3){} to[short] ++(0,-1.5) to[short] ++(0.5,0) node[vcc]{} node[above=4mm]{$5\mathrm{V}$}

        (P3) to[short] ++(-0.5,0) to[pR, mirror, n=POT] ++(0,-2)

        (POT.wiper) to[short] (POT.wiper -| P15) to[short] (P15)

        (U6.bpin 7) to[short] ++(0.5,0) node[circ](P4){} to[short] ++(2.5,0) node[circ](P4A){} to[short] ++(0,3) to[short] ++(1,0)

        node[and port, number inputs=4, anchor=in 3](U7){}

        (U7.center) node[xshift=-7mm]{$U_7$}

        (U7.in 1) to[short] ++(-0.5,0) to[short] ++(0,0.5) node[vcc]{5V}

        (U7.in 2) to[short] ++(-1.5,0) node[circ]{} node[above]{DPD}

        (U7.in 4) to[short] ++(-2.5,0) node[circ](U75){} to[short] ++(0,0.5) node[ocirc]{} node[above]{OC}

        (U75) to[short] ++(0,-4) node[circ](J){}

        (J) to[short] (J -| U7.in 4) node[and port, number inputs=4, anchor=in 2](U8){}

        (U8.center) node[xshift=-7mm]{$U_8$}

        (U8.in 1) to[short] ++(-0.5,0) node[circ]{} node[above]{DND}

        (U8.in 3) to[short] (U8.in 3 -| P4A) to[short] (P4A)

        (U8.in 4) to[short] ++(-0.5,0) to[short] ++(0,-1) to[short] ++(-0.5,0) node[vcc]{} node[above=4mm]{$5\mathrm{V}$}

        (J) to[R, l=$R_9$, a=$10\mathrm{k}\Omega$] ++(-2,0) node[circ](K){}

        (K) to[short] ++(0,-1.25) node[circ](L){} to[short] ++(0.25,0) node[nand port, anchor=in 1](U9){}

        (U9.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

        node[yshift=-8mm, xshift=-7mm]{$U_9$}

        (L) to[short] (L |- U9.in 2) to[short] (U9.in 2)

        (K) to[short] ++(-0.75,0) to[cC] ++(0,-2) node[rground]{} node[xshift=-7mm, yshift=5mm]{$C_4$}

        node[xshift=-5mm, yshift=1mm]{$0.1\mu\mathrm{F}$}

        (U9.out) to[short] (U9.out -| J) to[short] (J)

        (P4) to[short] ++(0,0.5) node[ocirc]{} node[above]{SH}

        (U7.out) to[short] ++(0.5,0) node[circ]{} node[right]{GP}

        (U8.out) to[short] ++(0.5,0) node[circ]{} node[right]{GN}

        ;
\end{circuitikz}
\end{document}
```
The above circuit is a sample driver circuit for an SCR rectifier. It operates in five main steps:
1. **Digital**. The first section of the circuit "digitizes" the [[AC Electricity|ac]] input, converting the sinusoidal voltage into a high signal and a low signal. These inputs are fed into [[Comparator|comparators]] $U_{1}$ and $U_{2}$ with outputs $DP$ and $DN$, respectively. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[ocirc](AC1){} node[left]{$AC1$} to[R, n=R1] ++(2,0) node[circ](A){}
        to[R, l2_=$R_2$ and $1\mathrm{k}\Omega$] ++(0,-2) node[rground]{}
        (R1) node[yshift=10mm, xshift=-2mm]{$R_1$} node[yshift=5mm]{$10\mathrm{k}\Omega$}
        (A) to[short] ++(1,0) node[circ](B){} to[short] ++(1,0)
        node[op amp, anchor=+, yscale=-1](U1){}

        (U1.center) node[]{$U_1$}

        (0,-3) node[ocirc](AC2){} node[left]{$AC2$} to[R, n=R3] ++(2,0) node[circ](C){}
        to[R, l2_=$R_4$ and $1\mathrm{k}\Omega$] ++(0,-2) node[rground]{}
        (R3) node[yshift=10mm, xshift=-2mm]{$R_3$} node[yshift=5mm]{$10\mathrm{k}\Omega$}
        (C) to[short] ++(1.5,0) node[circ](D){} to[short] ++(0.5,0)
        node[op amp, anchor=+, yscale=-1](U2){}

(U2.center) node[]{$U_2$}

(U1.-) to[short] (U1.- -| D) to[short] (D)
(U2.-) to[short] (U2.- -| B) to[short] (B)

(U1.out) to[short] ++(1,0)
(U2.out) to[short] ++(1,0)
;
\end{circuitikz}
\end{document}
```
2. **Edge Detector**. This section of the circuit detects when the signals $DP$ and $DN$ change from low to high or high to low. It accomplishes this by feeding their output into a configuration of [[NAND Gate|NAND gate]] [[Schmitt Trigger|Schmitt triggers]]. The output of $U_{3}$ and $U_{4}$ form the inputs to $U_{5}$. $DPD$ and $DND$ are delayed versions of $DP$ and $DN$, respectively, delayed by the RC filter formed by $R_{6}$ and $C_{1}$ (as well as $R_{8}$ and $C_{2}$). This delay triggers the Schmitt triggers (which  are positive-edge detecting) to send out a pulse to $U_{5}$. This pulse causes $U_{5}$ to produce pulses every time the $DP$ / $DN$ signals change state.  
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[short] ++(1,0) node[circ](E){} to[R, l=$R_5$, a=$10\mathrm{k}\Omega$] ++(0,2) node[vcc]{5V}

        (E) to[short] ++(0,-0.5) to[R,l2_=$R_6$ and $10\mathrm{k}\Omega$] ++(2,0) node[circ](F){} to[cC, l2=$C_1$ and $0.1\mu\mathrm{F}$] ++(0,-1) node[rground]{}

        (E) to[short] ++(2,0) node[circ](DP){} to[short] ++(2,0) node[nand port, anchor=in 1](U3){}

        (U3.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$} node[yshift=8mm, xshift=-7mm]{$U_3$}

        (DP) to[short] ++(0,0.5) node[circ]{} node[above]{DP}

        (0,-3) to[short] ++(1,0) node[circ](H){} to[R, l2=$R_7$ and $10\mathrm{k}\Omega$] ++(0,1.5) node[vcc]{} node[above=4mm]{5V}

        (H) to[short] ++(0,-1) to[R,l=$R_8$, a=$10\mathrm{k}\Omega$] ++(2,0) node[circ](I){} to[cC, l2=$C_2$ and $0.1\mu\mathrm{F}$] ++(0,-1) node[rground]{}

        (H) to[short] ++(2,0) node[circ](DN){} to[short] ++(2,0) node[nand port, anchor=in 2](U4){}

        (U4.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

        node[yshift=8mm, xshift=-7mm]{$U_4$}

        (DN) to[short] ++(0,0.5) node[circ]{} node[above]{DN}

        (F) to[short] ++(1.5,0) node[](F1){} to[short] (F1 |- U4.in 1) to[short] (U4.in 1)

        (F1) node[above, xshift=-5mm]{DPD}

        (I) to[short] ++(1.75,0) node[](I1){} to[short] (I1 |- U3.in 2)

        to[short] (U3.in 2)

        (I1) node[above, xshift=-5mm]{DND}

        (U3.out) to[short] ++(1,0) node[nand port, anchor=in 1](U5){}

        (U5.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}

        node[yshift=8mm, xshift=-7mm]{$U_5$}

        (U4.out) to[short] ++(0.5,0) node[](U4A){} to[short] (U4A |- U5.in 2)

        to[short] (U5.in 2)

        (U5.out) to[short] ++(2,0)
;
\end{circuitikz}
\end{document}
```
3. **Phase shift**. The next section is what allows us to introduce a phase shift into our rectifier. The IC $U_{6}$ is a $\text{74LS123}$ monostable circuit that outputs a pulse at $Q$ (and by extension, an opposite pulse at $\bar{Q}$). The pulse width of the output pulse is determined by the $R/C$ input, which in this case is adjustable by adjusting the [[Potentiometer|potentiometer]]. The output is technically $Q$ which would correspond to the phase shift angle $\delta$, but we make use of $\bar{Q}$ which corresponds to the conduction angle $\alpha$.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[nand port, anchor=in 1](U5){}
        (U5.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}
        node[yshift=8mm, xshift=-7mm]{$U_5$}
        
        (U5.out) to[short] ++(2,0)

        node[dipchip, num pins=12, hide numbers, no topmark, external pins width=0.25, anchor=bpin 2](U6){$U_6$}

        (U6.bpin 1)
        node[left, yshift=2mm, font=\tiny]{1}
        node[right, font=\small] {A}

        (U6.bpin 2)
        node[left, yshift=1mm, font=\tiny]{2}
        node[right, font=\small] {B}

        (U6.bpin 4)
        node[left, yshift=1mm, font=\tiny]{14}
        node[right, font=\small] {C}

        (U6.bpin 5)
        node[left, yshift=1mm, font=\tiny]{15}
        node[right, font=\small] {R/C}

        (U6.bpin 6)
        node[left, yshift=2mm, font=\tiny]{3}
        node[right, font=\small] {CLR}

        (U6.bpin 7)
        node[right, yshift=1mm, font=\tiny]{4}
        node[left, font=\small] {$\bar{\mathrm{ Q }}$}

        (U6.bpin 9)
        node[right, yshift=1mm, font=\tiny]{13}
        node[left, font=\small] {Q}

        (U6.bpin 1) node[ocirc, xshift=-1mm, scale=1.5]{} to[short] ++(-0.5,0) node[circ](P1){}

        to[short] ++(0,1) to[short] ++(0.5,0) node[rground]{}

        (U6.bpin 4) to[short] (U6.bpin 4 -| P1) to[short] (P1)

        (U6.bpin 5) to[short] ++(-2,0) node[circ](P15){} to[short] ++(-1,0) to[short] ++(0,-0.5) to[cC, l2_=$C_3$ and $1\mu\mathrm{F}$] ++(0,-1) to[short] ++(0,-0.75) node[rground]{}

        (U6.bpin 6) node[ocirc, xshift=-1mm, scale=1.5]{} to[short] ++(-0.75,0) node[circ](P3){} to[short] ++(0,-1.5) to[short] ++(0.5,0) node[vcc]{} node[above=4mm]{$5\mathrm{V}$}

        (P3) to[short] ++(-0.5,0) to[pR, mirror, n=POT] ++(0,-2) node[below]{$POT_1$} node[yshift=-5.5mm, xshift=-1mm]{$10\mathrm{k}\Omega$}

        (POT.wiper) to[short] (POT.wiper -| P15) to[short] (P15)
;
\end{circuitikz}
\end{document}
```
4. **Oscillator**. This stage provides an oscillating signal to the gate logic stage. This is done by using another Schmitt trigger NAND gate to create a pulsing signal that triggers the outputs.
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) node[circ](J){}

(J) to[R, l=$R_9$, a=$10\mathrm{k}\Omega$] ++(-2,0) node[circ](K){}

(K) to[short] ++(0,-1.25) node[circ](L){} to[short] ++(0.25,0) node[nand port, anchor=in 1](U9){}
(U9.center) node[xshift=-7mm]{$\LARGE \mathrm{S}$}
node[yshift=-8mm, xshift=-7mm]{$U_9$}
(L) to[short] (L |- U9.in 2) to[short] (U9.in 2)

(K) to[short] ++(-0.75,0) to[cC] ++(0,-2) node[rground]{} node[xshift=-7mm, yshift=5mm]{$C_4$}
node[xshift=-5mm, yshift=1mm]{$0.1\mu\mathrm{F}$}

(U9.out) to[short] (U9.out -| J) to[short] (J)
;
\end{circuitikz}
\end{document}
```
5. **Gate Logic**. The final stage of this circuit sends out a pulsed signal to $GP$ and $GN$. $GP$ and $GN$ are never on at the same time and are offset from one another by a phase shift $\delta$ that is determined by the 3rd stage of this circuit. These outputs need to be pulsed so that the [[Pulse Transformer|pulse transformer]] can operate properly. The width of these pulses are determined by the oscillator circuit. The logic gates are designed in such a way that the gate signal is only sent out when: a) the circuit is powered with $5\ \pu{ V}$, b) $DPD$ (see stage 2) is high, c) the signal corresponding to the conduction angle $\alpha$ is high, and d) the oscillator is high. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[short] ++(1,0) node[circ](P4){} to[short] ++(2.5,0) node[circ](P4A){} to[short] ++(0,3) to[short] ++(1,0)
node[and port, number inputs=4, anchor=in 3](U7){}
(U7.center) node[xshift=-7mm]{$U_7$}

(U7.in 1) to[short] ++(-0.5,0) to[short] ++(0,0.5) node[vcc]{5V}
(U7.in 2) to[short] ++(-1.5,0) node[circ]{} node[above]{DPD}
(U7.in 4) to[short] ++(-2.5,0) node[circ](U75){} to[short] ++(0,0.5) node[ocirc]{} node[above]{OC}

(U75) to[short] ++(0,-4) node[circ](J){}
(J) to[short] (J -| U7.in 4) node[and port, number inputs=4, anchor=in 2](U8){}
(U8.center) node[xshift=-7mm]{$U_8$}

(U8.in 1) to[short] ++(-0.5,0) node[circ]{} node[above]{DND}
(U8.in 3) to[short] (U8.in 3 -| P4A) to[short] (P4A)
(U8.in 4) to[short] ++(-0.5,0) to[short] ++(0,-1) to[short] ++(-0.5,0) node[vcc]{} node[above=4mm]{$5\mathrm{V}$}

(P4) to[short] ++(0,0.5) node[ocirc]{} node[above]{SH}

(U7.out) to[short] ++(0.5,0) node[circ]{} node[right]{GP}
(U8.out) to[short] ++(0.5,0) node[circ]{} node[right]{GN}
;
\end{circuitikz}
\end{document}
```
