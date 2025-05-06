---
tags:
  - physics
  - electromagnetism
  - electronics
  - telecommunications
---
Electrical **Noise** is any undesired [[Voltage|voltage]] or [[Current|current]] that end up appearing at the output of a [[Receiver|receiver]]. Noise may be generated from within the system itself (*internal noise*) or from outside the system (*external noise*). 

A noise source is typically very small in magnitude (on the order of microvolts) but communications [[Receiver|receivers]] amplify small signals to large signals. This makes even a very small $10\ \mathrm{\mu V}$ noise signal a problem when it is then transmitted and amplified. 
![[noise-amplification.png]]
# External noise
External noise can further be categorized based on its source.
## Human-made noise
Human-made noise is the most troublesome form of external noise. It is often caused by spark-producing mechanisms (engine ignition systems, [[Light Fixture#Fluorescent|fluorescent lights]], and [[DC Machine|commutators]]). These sparks create [[Electromagnetic Radiation|EM radiation]] that is transmitted through the atmosphere and can be detected by an antenna. If there is enough of this noise in the same vicinity as a [[Transmitter|transmitter]] or receiver, this noise will interfere with the intelligence. Human-made noises typically occur at frequencies up to $500\ \mathrm{MHz}$. 

Human-made noise also includes interference from [[Transmission Line#Power transmission lines|power lines]]. These can range from large high to medium voltage transmission and distribution lines, to large services within a building. If the service includes large loads like motors that are constantly switched on and off, this switching can also introduce noise into telecommunication systems.
## Atmospheric noise
Atmospheric noise includes naturally occurring disturbances in the [[Atmosphere|atmosphere]] including [[Lightning|lightning]]. Atmospheric noise is most troublesome at lower frequencies, but is not a significant factor for $f > 20\ \mathrm{MHz}$. This is because the amplitude of atmospheric noise is inversely proportional to its frequency, so the higher the frequency, the lower the amplitude and therefore the lower its impact on intelligence signals.
## Space noise
This third form of external noise comes from outer space and is fairly evenly divided between our [[Sun|sun]] and all other [[Star|stars]]. Noise originating from our sun is called *solar noise*. Solar noise is cyclical and reaches peaks around once every eleven years.

All other stars also generate space noise. Their collective contribution is called *cosmic noise*. Cosmic noise occurs at frequencies ranging from $8\ \mathrm{MHz} \leq f \leq 1.5\ \mathrm{GHz}$. Energy below this threshold is absorbed by the [[Ionosphere|ionosphere]].
# Internal noise
Components and circuits within the receiver itself can introduce internal noise that adds to the external noise applied to the [[Antenna|antenna]]. These have the most drastic effect in the first stage of amplification, where the intelligence signal is at its lowest level and therefore requires the most amplification.
## Thermal noise
Thermal noise is one of the two types of noise produces by electronic circuits. This is a result of interactions between free [[Electron|electrons]] and vibrating [[Ion|ions]] in a [[Conductor|conductor]]. These vibrations cause electrons to arrive at the end of a resistor (or resistive element) at a random rate, causing a randomly fluctuating potential difference across the resistance. 

This type of noise was studied extensively by [[J.B. Johnson]] and is as such sometimes termed *Johnson noise*. Johnson discovered that this noise was dependant on the temperature of the conductor and the system bandwidth. Since it is temperature dependant, it is also sometimes called *thermal noise* or even *white noise*[^1]. The equation for the power of thermal noise is,
$$
P_{\mathrm{n}}=kT\ \Delta f
$$
where $P_{\mathrm{n}}$ is the power of the noise, $k$ is [[Boltzmann's Constant]], $T$ is the [[Temperature|temperature]] of the resistance in [[Kelvin|kelvin]] $[\mathrm{K}]$, and $\Delta f$ is the system bandwidth in [[Hertz|hertz]] $[\mathrm{Hz}]$.

[^1]: This arises from the realm of [[Fibre Optics|optics]] where white light contains all frequencies or colours.
