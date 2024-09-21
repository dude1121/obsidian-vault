---
tags:
  - electromagnetism
  - electrical-engineering
  - physics
  - circuit-analysis
---
In any ac circuit with both resistive and reactive components, it can be useful to swap between series and parallel configurations. I'm not going to go into the derivation here since it is messy, but can be found on Introductory Circuit Analysis p. 746. 

From parallel to series:
$$
\begin{aligned}
R_{s}&=\frac{R_{p}X_{p}^2}{R_{p}^2+X_{p}^2}&X_{s}&=\frac{R_{p}^2X_{p}}{R_{p}^2+X_{p}^2}
\end{aligned}
$$
From series to parallel:
$$
\begin{aligned}
R_{p}&=\frac{R_{s}^2+X_{s}^2}{R_{s}}&X_{p}=\frac{R_{s}^2+X_{s}^2}{X_{s}}
\end{aligned}
$$
