---
tags:
  - volts
  - potential
  - electromagnetism
  - physics
---
**Voltage**, also known as **electric potential**, is a measure of the “pressure” difference between positive and negative [charges](Charge.md). We also call this a difference in _electrical potential_. It is [[Units of Measurement|measured]] in [[Volt]] $[\mathrm{V}]$.

If a total of $1\text{J}$ of work is used to move a charge of $1\text{C}$ of [electrons](Electron), we say there is an electrical potential difference of $1\text{V}$. $1\text{C}$ is defined as the amount of charge present in $6.242\times10^{18}$ electrons. That is,
$$ 1\text{C}\equiv6.242\times10^{18}\text{ e}^\text{-} $$
We can therefore define voltage as,
$$ V=\frac{W}{Q} $$
# Potential in an electric field
If we have some [[Electric Field|electric field]] $\mathbf{E}$, the potential as a function of [[Position|position]] in that field is,
$$
V(\mathbf{r})=-\int_{\mathcal{O}}^\mathbf{r} \mathbf{E}\cdot d\mathbf{l}
$$
More generally, the potential in a field is related to the field by,
$$
\mathbf{E}=-\nabla V
$$
This arises because the electric field is independent of the path between two points, so a generalized potential function can be defined and based only on one position with some arbitrary point set as the reference. 

Since $\mathbf{E}=-\nabla V$ and $\nabla \cdot E=\frac{1}{\varepsilon_{0}}\rho$, it follows that,
$$
\nabla^2V=-\frac{\rho}{\varepsilon_{0}}
$$
That is, the [[Laplacian]] of the potential is $\frac{\rho}{\varepsilon_{0}}$. This is [[Poisson's Equation]]. If there is no charge density ($\rho=0$), this reduces to [[Laplace's Equation|Laplace's equation]].
$$
\nabla^2V=0
$$
