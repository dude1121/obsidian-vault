---
tags:
  - electrical-engineering
---
A **per-unit rating** is a method for giving values in some system based on ratios of some 'base' rating instead of their absolute values. It is commonly denoted as p.u.
$$
\mathrm{p.u. value}=\frac{\mathrm{real\ value}}{\mathrm{base\ value}}
$$
The *base* value is typically the rated value of a component or system.
>[!question] Example
>In a $24.9\ \mathrm{kV}$, $6\ \mathrm{MVA}$ system, the base values would be
>$S_{B}=6\ \mathrm{MVA}$, $E_{LB}=24.9\ \mathrm{kV}$
>$E_{\phi B}=\frac{E_{LB}}{\sqrt{ 3}}=\frac{24.9\ \mathrm{kV}}{\sqrt{ 3}}=14.4\ \mathrm{kV}$
>$S_{\phi B}=\frac{S_{B}}{3}=\frac{6\ \mathrm{MVA}}{3}=2\ \mathrm{MVA}$
>$I_{B}=\frac{S_{\phi B}}{E_{\phi B}}=\frac{2\ \mathrm{MVA}}{14.4\ \mathrm{kV}}=139\ \mathrm{A}$
>$Z_{B}=\frac{E_{\phi B}}{I_{B}}=\frac{14.4\ \mathrm{kV}}{139\ \mathrm{A}}=103\ \Omega$

>[!question] Example 2
>Reactors of $X_{\mathrm{p.u.}}=0.087$ are used in the lines in the system above. Calculate the short circuit current.
>
>Since the voltage per-unit is not mentioned, we assume $E_{\mathrm{p.u.}}=1$.
>
>$I_{\mathrm{p.u.}}=\frac{E_{\mathrm{p.u.}}}{X_{\mathrm{p.u.}}}=\frac{1}{0.087}=11.5$
>
>$I_{\mathrm{s.c.}}=I_{B}I_{\mathrm{p.u.}}=139\ \mathrm{A} \cdot 11.5=1598\ \mathrm{A}$

