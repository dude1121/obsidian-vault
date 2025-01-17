---
tags:
  - physics
  - kinematics
---
The [[Force|force]] acting on an object due to [[Gravity|gravity]] is known as the **gravitational force**. It is defined as a special case of [[Newton's Laws|Newton's second law]]. The force is given by,
$$
\mathbf{\vec{F}}_{g}=m\mathbf{\vec{g}}
$$
where $\mathbf{\vec{F}}_{g}$ is the force acting on the object and $\mathbf{\vec{g}}$ is the acceleration due to gravity on [[Earth]] ($\approx 9.801\pu{ m/s^2}$). This however is only applicable on Earth's surface, as the force due to gravity varies on different bodies, and even at different altitudes on Earth. The more general form of the gravitational force equation is referred to as *Newton's law of universal gravitation*. It states that,
>[!quote] Law of universal gravitation
>Every particle in the [[Universe|universe]] attracts every other particle with a force that is directly proportional to the product of their masses and inversely proportional to the square of the distance between them.

Put algebraically,
$$
F_{g}=G\frac{m_{1}m_{2}}{r^2}
$$
$G$ is called the *gravitational constant* and it has a value of,
$$
G=6.673\times 10^{-11}\ \pu{ N}\cdot \pu{ m^2/kg^2}
$$
This form of the gravitational force is sometimes called an *inverse-square law* since the magnitude of the force is inversely proportional to the square of the separation of the particles.

Since force is a [[Vector|vector]], we can express this law in vector form by defining a unit vector $\mathbf{\hat{r}}_{12}$ which a vector of magnitude $1$ pointing from particle $1$'s location towards particle $2$. Therefore,
$$
\mathbf{\vec{F}}_{12}=-G\frac{m_{1}m_{2}}{r^2}\mathbf{\hat{r}}_{12}
$$
The negative sign indicates that particle $2$ is attracted to particle $1$. By Newton's third law, we can state that $\mathbf{\vec{F}}_{21}$ must be equal but opposite to $\mathbf{\vec{F}}_{12}$. We can use this equation to further show that the *gravitational force exerted by a finite-size, spherically symmetric mass distribution on a particle outside the distribution is the same as if the entire mass of the distribution were concentrated at the centre*. For example, the magnitude of the force exerted by the Earth on a particle of mass $m$ near the Earth's surface is,
$$
F_{g}=G\frac{M_{E}m}{R_{E}^2}
$$
where $M_{E}$ is the Earth's mass and $R_{E}$ is the Earth's radius. If we substitute in $5.9722\times 10^{24}\ \pu{ kg}$ for the Earth's mass and $6.371\times 10^6\ \pu{ m}$ for Earth's radius, we get,
$$
\begin{aligned}
F_{g}&=6.673\times 10^{-11}\ \pu{ N\cdot m^2/kg^2 }\frac{5.9722\times 10^{24}\ \pu{ kg}\cdot m }{(6.371\times 10^6\ \pu{ m})^2}\\
&=9.819\ \pu{ m/s^2}\cdot m
\end{aligned}
$$
which was our special case given above. Note that our value for $g$ is slightly different here since the typical value used $9.801$ is the *average* on earth, whereas these values are more accurate if the particle was on the equator.

We could find a more accurate value of $g$ depending on the particle's location relative to the centre of the Earth by using the relationship,
$$
g=G\frac{M_{E}}{(R_{E}+h)^2}
$$
where $h$ is some distance above the Earth's surface.
