---
tags:
  - physics
  - units
---
The **decibel** is a relative [[Units of Measurement|unit of measurement]] that expresses the ratio of two values on a [[Logarithm|logarithmic]] scale. It is one-tenth of a **bel** $[\pu{ B}]$ (named after [[Alexander Graham Bell]]). It is most commonly used in terms of two different ratios: [[power]] and [[voltage]].

# Power Ratios

When expressed as a power ratio, it is defined as,
$$
L_{P}=10\log_{10}\left(\frac{P}{P_{0}}\right)
$$
where $L_{P}$ is the power ratio in decibels $[\pu{ dB}]$, $P$ is the measured power $[\pu{ W}]$ and $P_{0}$ is the reference power, also in [[Watt|watts]] $[\pu{ W}]$. This ratio means that increasing power by $3\pu{ dB}$ corresponds to doubling the power.

# Voltage Ratios

Recall that,
$$
P\propto V^2
$$
To express decibels as a voltage ratio, we can substitute this into the definition above:
$$
\begin{aligned}
L_{V}&=10\log_{10}\left(\frac{V^2}{V_{0}^2}\right)\\
&=10\log_{10}\left(\frac{V}{V_{0}}\right)^2\\
&=20\log_{10}\left(\frac{V}{V_{0}}\right)\\
\end{aligned}
$$
This ratio means that increasing voltage by $6\pu{ dB}$ corresponds to doubling the voltage.
