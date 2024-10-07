---
id: AC Electricity
aliases: []
tags:
  - physics
  - electromagnetism
  - electrical-engineering
---

**AC Electricity** (alternating current) is a form of electricity in which the [[voltage]] and [[current]] oscillate at some [[Frequency|frequency]]. An ac [[Waveform|waveform]] may be sinusoidal, square, or triangular. Ac electricity is created by a [[generator]] which behaves on the principles of [[Faraday's Law]].

# Sinusoidal Waveform

This type of waveform is the only type whose shape is unaffected by the response characteristics of [[Resistor|R]], [[Inductor|L]], or [[Capacitor|C]] components. If a sinusoidal voltage is applied across any of these elements, the resulting current will always also be sinusoidal. This is not the case with square or triangular waveforms.

If we imagine the rotating voltage like a [[vector]] at the origin, the vertical (or $y$-coordinate) of that vector can be plotted as a function of time. The result is a sine wave. How quickly the vector spins is determined by its [[Angular Velocity|angular velocity]] $\omega$. The time to complete one rotation is equal to the waveform's [[period]]. Therefore,

$$
\omega=\frac{2\pi}{T}
$$

The shorter the period, then, the greater the angular velocity. We can substitute frequency in for period for the more familiar,

$$
\omega=2\pi f
$$

## Equation

A sinusoidal waveform can represented mathematically as,

$$
f(t)=A\sin(\omega t+\theta)
$$

where $A$ is the amplitude of the wave, $\omega$ is the angular frequency, and $\theta$ (sometimes denoted with $\varphi$) is the [[Phase Shift]] of the wave. If the waveform is not offset by some value, the amplitude corresponds to the _maximum_ or _peak_ value of the function. In electrical terms, we typically denote this as $E_{pk}$ or $I_{pk}$. The equation for a sinusoidal voltage, then, is

$$
e=E_{pk}\sin(\omega t+\theta)
$$

A non-zero value for $\theta$ will shift the waveform to the left or to the right, depending on the sign of $\theta$.

Typically when referring to ac values we don't describe them in terms of a sinusoidal function, but rather as an [[Root Mean Square|rms]] value as part of a [[Phasor|phasor]].
