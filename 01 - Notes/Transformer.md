---
tags:
  - physics
  - electromagnetism
  - electrical-engineering
---
A **transformer** is a static [[Electrical Machine|machine]] that is able to *transform* the voltage of a circuit by increasing it by some factor (step-up), decreasing it by some factor (step-down), or isolating two circuits of the same potential (isolation). Put simply, a transformer is two separate electrical circuits coupled by a [[Magnetic Circuit|magnetic circuit]].

Transformers consist of some core (typically [[Iron|iron]] or sheet steel) with two windings around the core called the *primary winding* and the *secondary winding*. In schematic diagrams these windings are typically shown on opposite legs of the core, but in reality these windings are interleaved. 
![[ideal-transformer.png]]
# The Ideal Transformer
The ideal transformer makes some key assumptions:
1. The winding [[Resistance|resistances]] are negligible
2. The [[Magnetic Flux|flux]] is contained to the core and link both windings. No leakage flux is present and core losses are negligible.
3. Core [[Permeability|permeability]] is infinite (i.e. $\mu\to \infty$). Therefore, the exciting [[Current|current]] required to establish flux in the core is negligible.

When the primary winding is connected to a time-varying [[Voltage|voltage]], a time varying flux is established in the core according to [[Faraday's Law|Faraday's law]].
$$
e_{p}=N\frac{d\Phi}{dt}
$$
This flux is linked to the secondary winding and therefore also generates a voltage across the winding according to the same law.
$$
e_{s}=N\frac{d\Phi}{dt}
$$
Since this time-varying flux is the same between each winding, we can set these equations equal to one another to arrive at,
$$
\frac{e_{1}}{e_{2}}=\frac{N_{1}}{N_{2}}
$$
This ratio is known as the *transformer ratio* or *turns ratio* and it dictates whether the secondary voltage will be greater than, less than, or equal to the primary voltage. This ratio is denoted with $a$.
$$
a=\frac{e_{1}}{e_{2}}=\frac{N_{1}}{N_{2}}
$$
If a load is added to the secondary, a current $i_{2}$ will begin to flow. In an ideal transformer, we assume that the [[Apparent Power|apparent power]] in the primary is equal to the power in the secondary. 
$$
S_{1}=S_{2}
$$
$$
v_{1}i_{1}=v_{2}i_{2}
$$
When a load is connected to the secondary, a primary current $i_{1}$ will flow to oppose the increase in counter-[[Magnetomotive Force|mmf]] in the secondary winding. Otherwise, the core flux would change drastically and the voltages $e_{1}$ and $e_{2}$ would be affected. The mmf of both windings in an ideal transformer must be equal.
$$
N_{1}i_{1}=N_{2}i_{2}
$$
$$
\frac{i_{1}}{i_{2}}=\frac{N_{2}}{N_{1}}=\frac{1}{a}
$$
This means that the currents in a transformer have an inverse relationship to the turns ratio.

