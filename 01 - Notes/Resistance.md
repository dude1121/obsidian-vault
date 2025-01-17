---
tags:
  - resistivity
  - ohms
  - electromagnetism
  - physics
  - georg-ohm
---
💡 **Resistance** is the opposition to the flow of charge. It is one form of opposition, along with **[[Reactance]]** and **[[impedance]]**. It is [[Units of Measurement|measured]] in [[Ohm|ohms]] $[\Omega]$ after the German physicist Georg Ohm. Resistance shares an inverse relationship with [[Conductance|conductance]].

The resistance of a material is proportional to its length and inversely proportional to its cross-sectional area.
$$ R\propto\frac{\ell}{A} $$
The proportionality constant in this case is the material’s **[[Resistivity|resistivity]]** and it is denoted by the Greek letter $\rho$. Resistivity is measured in ohm-metres $[\Omega\cdot\text{m}]$ and varies from material to material and by temperature. Commonly used values are listed below.

| Material      | Resistivity ($\rho$) @ $T=20\degree\text{C}$ |
| ------------- | -------------------------------------------- |
| Copper (Cu)   | $16.78\times10^{-9}\text{ }\Omega\text{m}$   |
| Gold (Au)     | $22.14\times10^{-9}\text{ }\Omega\text{m}$   |
| Aluminum (Al) | $26.50\times10^{-9}\text{ }\Omega\text{m}$   |
With this constant, we can re-write our equation for resistance as
$$ R=\rho\frac{\ell}{A} $$
This relationship is known as Pouillet’s Law.

As mentioned, the resistance of a material also varies with temperature. Recall that absolute zero is equal to $-273.15\degree\text{C}=0\text{K}$. The resistance of a material approaches $0\Omega$ as the temperature approaches $0\text{K}$.

![[Copper-resistance-vs-temperature.webp]]

However, this is a complex relationship to model, so it is easier to approximate a material’s “zero” based on continuing the “linear” portion of its Resistance vs. Temperature graph. This is called the material’s _inferred absolute zero_ and it varies by material. For copper, this value is $T_{i-Cu}=-234.5\degree\text{C}$. The inferred absolute zero for aluminum is $T_{i-Al}=-236\degree\text{C}$. We can use this inferred absolute zero to determine the resistance for a material at different temperatures if we know the resistance of the material at one temperature. Algebraically this relationship can be written as,
$$ \frac{|{T_i}|+T_1}{R_1}=\frac{|T_i|+T_2}{R_2} $$
Rearranging…
$$ \frac{R_2}{R_1}=\frac{|T_i|+T_2}{|T_i|+T_1} $$
$$ \frac{R_2}{R_1}-1=\frac{|T_i|+T_2}{|T_i|+T_1}-\frac{|T_i|+T_1}{|T_i|+T_1} $$
$$ \frac{R_2}{R_1}-1=\frac{|T_i|+T_2-|T_i|-T_1}{|T_i|+T_1} $$
$$ \frac{R_2}{R_1}-1=\frac{T_2-T_1}{|T_i|+T_1} $$
$$ \frac{R_2}{R_1}=1+\frac{T_2-T_1}{|T_i|+T_1} $$
$$ R_2=R_1\left(1+\frac{T_2-T_1}{|T_i|+T_1}\right) $$
$$ R_2=R_1(1+\alpha(T_2-T_1)) $$
where,
$$\alpha\equiv\frac{1}{|T_i|+T_1}$$
$\alpha$ is called the temperature coefficient. By substituting in the inferred absolute zero of the material we want, we can find the temperature coefficient of that material for a given temperature.
$$ \alpha_{20}=\frac{1}{|-234.5\degree\text{C}|+20\degree\text{C}}=0.00393 $$
Using this allows us to find the resistance of a material given any temperature so long as we know its resistance as room temperature, $20\degree\text{C}$.
$$ R=R_{20}[1+\alpha_{20}(T-20\degree\text{C})] $$
> [!question] Example
> A bar of aluminum has a resistance of $550\Omega$ at room temperature. Find its equivalent resistance at $T=70\degree\text{C}$.
> Given:
> 	$R_{20}=550\Omega$
> 	$T=70\degree\text{C}$
> 	$T_{i-Al}=-236\degree\text{C}$
>Find the temperature coefficient of aluminum.
>	$$\alpha_{20}=\frac{1}{|-236\degree\text{C}|+20\degree\text{C}}$$
>	$$\alpha_{20}=0.00391$$
>Calculate the resistance of the aluminum at $T=70\degree\text{C}$.
>	$$R=550\Omega[1+(0.00391)(70\degree\text{C}-20\degree\text{C})]$$
>	$$R=657.525\Omega$$
>$\therefore$, the resistance of the aluminum bar at $70\degree\text{C}$ is $657.525\Omega$.
