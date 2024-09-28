---
tags:
  - electromagnetism
  - physics
  - electronics
  - circuit-analysis
---
A **LED** or **Light-Emitting Diode** is a special kind of [[Diode|diode]] that emits [[Light|light]] when in forward bias. 
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[leD*, o-o, bipoles/length=1cm] ++(4,0)
;
\end{circuitikz}
\end{document}
```
Its symbol is identical to that of a normal diode with two arrows added pointing away from the diode, representing the [[Photon|photons]] emitted from the device.

# Construction

Like a regular diode, an LED consists of a [[PN Junction|pn junction]]. This junction however is constructed of specific elements so as to produce light  when the junction is forward biased. LEDs are made from a variety of semiconductor materials ranging from [[Indium Gallium Nitride|indium gallium nitride]] (InGaN) for colours like violet, blue, and green, to [[Gallium Arsenide Phosphide|gallium arsenide phosphide]] (GaAsP) for orange, yellow, and red. 

# Datasheet Values

The forward [[Voltage|voltage]] $V_{F}$ of an LED will vary from LED to LED, as the specific material used to make the LED will determine what its forward bias voltage is. Typically, colours with a larger [[Wavelength|wavelength]] (and therefore less [[Energy|energy]]) will require a smaller forward voltage, and colours with a smaller wavelength (and therefore more energy) will require more forward voltage. This may range from $V_{F}\approx 1.7\pu{ V}$ in a red LED, to $V_{F}\approx 2.8\pu{ V}$ in a violet LED.

Another given value on the datasheet will be the [[Radiant Intensity|radiant intensity]] $I_{c}$ which is the measure of [[Radiant Flux|radiant flux]] emitted per [[Solid Angle|solid angle]], measured in [[Watt|Watts]] per [[Steradian|steradian]] $[\pu{ W}/\pu{ sr}]$. It could also be thought of as the output [[Power|power]] per steradian. On an LED datasheet, this value might be given in milliwatts per steradian $[\pu{ mW}/\pu{ sr}]$.

The [[Irradiance|irradiance]] $E$ is another datasheet value, which is the power per unit area at some given distance. Irradiance is typically measured in Watts per square [[Metre|metre]] $[\pu{ W}/\pu{ m}^2]$ but on an LED datasheet it will likely be given in milliwatts per square centimetre $[\pu{ mW}/\pu{ cm}^2]$. This is an important value because if the LED is used in conjunction with a [[Photodiode|photodiode]], the response of that photodiode depends on the irradiance it receives from the LED.

# Applications

LEDs are often used as indicators in circuits (e.g. power on lights, mode select, etc.) but can also be combined with many other LEDs to create [[Seven Segment Display|7-segment displays]], or red, green, and blue LEDs can be combined together to form a [[Pixel|pixel]], and many pixels may be combined to form a monitor or TV. High-intensity LEDs and LED arrays are also used in brake lights or headlights on vehicles, or in traffic lights.

Also see [[OLED]] and [[Photodiode]].