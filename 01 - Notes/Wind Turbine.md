---
tags:
  - physics
  - electrical-engineering
  - power-systems
---
A **wind turbine** is a device that converts wind [[Kinetic Energy|kinetic energy]] into [[Electrical Energy|electrical energy]]. As of 2023, wind made up approximately $8\%$ of Ontario's power consumption. Wind turbines are a form of [[Renewable Energy|renewable energy]] along with [[Solar Power Plant|solar]], [[Hydroelectric Power Station|hydro]], [[Biomass Power Station|bioenergy]], and [[Geothermal Power Station|geothermal]].
# Operation
![[wind-turbine-diagram.gif]]
- The *anemometer* measures the current wind [[Speed|speed]].
- The *blades* are pushed by the wind to spin the rotor. The orientation of these blades can be adjusted by the yaw drive and the pitch control (both automated). The pitch is adjusted to adjust the torque applied to the rotor so that the [[Generator|generator]] is not overloaded. 
- The *brake* slows down or stops the turbine if the wind speed is too fast for the turbine's ratings. It also may function to hold the turbine still during maintenance.
- The *controller* contains the electronics that coordinate the input from the exterior sensors like the anemometer and the wind vane as well as the output to the yaw motor or pitch motors.
- The *gear box* allows the turbine rotor to spin at a much slow speed by using [[Gear Ratio|gear ratios]] to spin the generator at a much higher rate than the turbine rotor. 
- The *generator* converts the rotational [[Mechanical Energy|mechanical energy]] into electrical energy. This output [[Voltage|voltage]] is sent in conductors down the tower until it reaches a [[Transformer|transformer]] at the bottom where it is then sent out for distribution.
- The *high-speed shaft* spins at a higher speed relative to the turbine rotor shaft. This speed will be the synchronous speed of the generator depending on the frequency of the voltage it  is generating. 
- The *low-speed shaft* is the shaft that connects to the blades, and therefore rotates at a relatively slower speed.
- The *[[Nacelle|nacelle]]* is the housing of the wind turbine that contains all the components less the blades themselves, external sensors, and the yaw drive unit.
- The *pitch* of the rotor blades determine how much wind blows the blades, thereby determining the speed at which they rotate. This pitch can be adjusted so that the turbine always turns at the correct speed to generate electricity at the correct frequency ($50\pu{ Hz}$ in Europe, $60\pu{ Hz}$ in North America). 
- *Rotor*.
- *Tower*.
- *Wind direction*.
- *Wind vane*.
- *Yaw drive*.
- *Yaw motor*.
## Generator
As mentioned, there is a generator in the nacelle of the wind turbine. Unlike other forms of power generation, however, this generator is typically an asynchronous generator (or, [[Induction Machine|induction generator]]) or, if the turbine is smaller, a [[DC Machine|dc generator]] may sometimes be used.
### Dc generator
In the even the turbine is driving a dc generator, the generated power may be stored in a [[Battery|battery]] so that it can be used later to power some load. This allows the wind turbine to, if the battery is sized properly, have a continuous supply of power instead of an intermittent one. The battery capacity can be selected by the formula,
$$
C_{b}=\frac{Pt}{E}
$$
### Asynchronous generator
In order for the asynchronous generator to generate electricity, there needs to be some supply of [[Reactive Power|reactive power]] to generate the stator field. This power comes from the grid itself. This reactive power introduces a [[Phase Shift|phase shift]] since the load is primarily [[Inductor|inductive]]. To remedy this, a [[Capacitor|capacitor]] bank is introduced in parallel to the generator to bring the [[Power Factor|power factor]] back to $1$. In most cases, the generator turns at a constant speed, however there are some more theoretical but costly ideas to build VVVF (variable voltage, variable frequency) turbines that can allow the generator to turn at various speeds but output the correct frequency by use of convertors. These designs are, at present, too expensive to realistically implement.
## Power
We can find the power of the wind that spins the turbine blades by first determining the [[Kinetic Energy|kinetic energy]] of the wind. 
$$
K_{\text{W}}=\frac{1}{2}m_{\text{W}}v_{\text{W}}^2
$$
where $m_{\text{W}}$ is the [[Mass|mass]] of some [[Volume|volume]] of air and $v_{\text{W}}$ is the [[Speed|speed]] of the wind. We know then that over some period of time $t$, the air moves some distance $vt$. The total volume then of air that moves in time $t$ is
$$
V_{\text{W}}=\pi r^2vt
$$
The blades of the turbine rotate in a circle so we only consider the cylindrical volume that passes through the turbine. In this case, $r$ is the blade length of the turbine. The mass of this air then is given by,
$$
m=\rho V
$$
where $\rho$ is the density of air (we assume typically this is $1.2\pu{\! kg/m^3}$). Therefore, the mass of the wind that passes through the turbine blades in time interval $t$ is
$$
m_{\text{W}}=1.2\pu{\! kg/m^3}\cdot \pi r^2vt
$$
We can substitute this into our kinetic energy equation,
$$
K_{\text{W}}=\frac{1}{2}1.2\pu{ \! kg/m^3}\cdot \pi r^2v^3t
$$
Since power is energy over time,
$$
\boxed{P_{\text{W}}=0.6\cdot \pi r^2v^3}
$$
To increase the power of a wind turbine then, we can:
- Increase the [[Radius|radius]] of the cross-sectional area of the turbine, that is, increase the turbine blade length. 
- Station the turbine somewhere there is stronger wind

However, the turbine can not extract all the power from the wind. This is expressed in the *power coefficient* $C_{p}$ which is a factor multiplied by $P_{\text{W}}$ to get the power input to the turbine. That is,
$$
P_{\text{t}}=C_{p}P_{\text{W}}
$$
## Tip-speed ratio
The length of the blades can not be as long as possible, however. Functionally, they are limited by the wind speed they will encounter.
![[tip-speed-plot.png]]
The above plot shows the power coefficient vs the tip-speed ratio, $\lambda$. When $\lambda$ is between $6-8$, the power coefficient is its highest value. The tip-speed ratio is given by,
$$
\lambda=\frac{\text{tip speed of blade}}{\text{wind speed}}=\frac{\omega r}{v_{\text{W}}}
$$
where $\omega$ is the [[Angular Velocity|angular speed]] of the turbine blades, $r$ is the length of the turbine blade, and $v_{\text{W}}$ is the wind speed.
# Pros & Cons
Wind power, as mentioned, is entirely *clean*, meaning it produces no harmful by-products. It also is free in that there is no cost to the "fuel" the turbine consumes. However, wind power is not constant, and therefore the power output of wind turbines is not constant. 