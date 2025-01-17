---
tags:
  - electrical-engineering
  - physics
  - power-systems
---
A **hydroelectric power station** is a [[Power Systems|power generation station]] that uses the flow of [[Water|water]] to [[Generator|generate]] electricity. Hydroelectric power stations are typically located on rivers to take advantage of already moving water. These stations make up approximately $25\%$ of Ontario's power generation.
# Working principle
![[hydroelectric station.png]]
Water flows into the dam and is filtered by the *trash rack*. The water is then sent into the *penstock* where it is fed into a [[Turbine|turbine]]. This turbine spins when it is hit by the water, thereby generating a [[Voltage|voltage]] in the generator. This voltage is then stepped up by a [[Transformer|transformer]] where it is carried away by [[Transmission Line|transmission lines]]. The *control gate* can be raised or lowered to change the water flow. This change in water flow changes the [[Torque|torque]] applied on the turbine, thereby changing the [[Power|power]] output of the station. 

The power flow of this station begins with [[Potential Energy|potential energy]] of the water at the top of the penstock which is then converted into [[Kinetic Energy|kinetic energy]] as it flows down the penstock. This kinetic energy is converted into [[Electrical Energy|electrical energy]] via the turbine and generator. 

The amount of electrical power generated is proportional to the [[Flow Rate|flow rate]] of the water, the height (or as its commonly referred to, *head*), and the [[Acceleration|acceleration]] due to [[Gravity|gravity]].
$$
P_{\text{e}}=Qgh
$$
where $Q$ is the flow rate of the water in $\pu{ kg/s}$ or $\pu{ m^3/s}$, $g$ is the acceleration due to gravity $g=9.8\pu{ m/s^2 }$, and $h$ is the height of the water at the top of the penstock in $\pu{ m}$. If a flow rate is used using units of $\pu{ m^3/s}$, the power will be expressed in $\pu{ kW}$, not $\pu{ W}$ (since $1\pu{ m^3/s}=1000\pu{ kg/s}$).  Since power is simply the time derivative of energy, the power into a hydroelectric power station is the time derivative of the potential energy of the system (as flow rate is [[Mass|mass]] per time). 

To control the flow rate, the turbine interior has some wicket gates that can be opened or shut to control the flow of water through the turbine. This has the effect of reducing the torque applied to the turbine that is turning the generator. Recall that the mechanical power input to a generator is given by,
$$
P_{\text{in}}=\omega \tau
$$
This means that by varying the torque of the turbine, the input power to the generator is also varied.
# Pumped-storage installations
Assume we have a hydroelectric station that is isolated, can not take in any exterior power, and it must meet the power demand of its region. This power demand will have a *base* value with a fluctuating peak value. 
![[power-demand-fluctuating.png]]
This station will need to provide not only the base demand but also the peak demand, and ensure that the power generated matches the demand. To do this, the station is designed to have a base power output of not the $100\pu{ MW}$, but the average of the entire demand, in this case, approximately $130\pu{ MW}$.
![[averaged-power-demand.png]]
Now, an auxiliary *peak* station only needs to generate $30\pu{ MW}$ instead of $60\pu{ MW}$. In times when the demand is *less* than the base $130\pu{ MW}$, the peak station is operated as a load, and what was previously a generator begins to behave as a [[Motor|motor]], and it pumps the water back up into the reservoir. This keeps the base station operating as efficiently as possible, since generators operate at max efficiency while at full load.

This setup has the advantage of the base station being more efficient, and the peak station requiring a smaller power rating and therefore is cheaper to build and maintain.