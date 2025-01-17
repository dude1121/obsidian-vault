---
tags:
  - electrical-engineering
  - power-systems
  - physics
---
**Thermal power stations**, also known as **fossil fuel power stations**, are stations that [[Generator|generate]] electricity by burning fuel. In Ontario, gas/oil power plants make up about $13\%$ of total power consumed province-wide. 
# Working principle
![[coal-power-plant.png]]
A thermal power plant operates by using some fuel (the above picture uses [[Coal|coal]] but functionally this could be replaced by oil, gas, or any combustible fuel) to heat up steam, thereby increasing the pressure of the steam, which is then fed to a [[Turbine|turbine]]. This turbine begins to rotate, thus rotating the generator that it is coupled to, which generates electricity. The output [[Voltage|voltage]] of the generator is stepped up by the [[Transformer|transformer]] and then sent out via [[Transmission Line|transmission lines]]. The water within the steam lines must be purified, whereas water grabbed from some reservoir is used solely for cooling purposes and does not need to be purified. The steam sent through the turbine is then cooled in the condenser before being sent back into the boiler.

The steam that is sent to the turbine is sometimes called "HTHP" steam, meaning *high temperature, high pressure*. The steam leaving the turbine is therefore referred to as "LTLP" steam, meaning *low temperature, low pressure*. However, this is "low temperature" *relative* to the high temperature of the incoming steam. This steam is still very hot and very dangerous.
![[thermal-power-plant.png]]
1. *Boiler*.
2. *Drum*. Stores water in the boiler before it becomes steam.
3. *High-Pressure Turbine*. This turbine allows the steam to expand between the turbine blades thereby converting thermal energy into mechanical energy. The steam that leaves here is therefore cooler and of lower pressure than when it entered.
4. *Medium-Pressure Turbine*. This is similar to the high-pressure turbine, but it is larger so that the steam may expand more.
5. *Low-Pressure Turbine*. This turbine is constructed of two identical left-hand and right-hand sections. The turbine sections remove the remaining available energy from the steam.
6. *[[Condenser]]*. The condenser allows the steam to condense into water by flowing it over cooling pipes. The water in these pipes is from some outside source that then carries away the heat.
7. *Reheater*. This is a [[Heat Exchanger|heat exchanger]]. It receives hot steam from the high-pressure turbine which raises the temperature of the feedwater coming from the condenser. 
8. *Feedwater pump*.
9. *Burners*. These supply and control the amount of fuel injected into the boiler.
10. *Forced-draft fan*.
11. *Induced-draft fan*.
## Efficiency
The efficiency of a thermal power station can be found by,
$$
\eta=1-\frac{T_{2}}{T_{1}}
$$
where $T_{1}$ is the [[Temperature|temperature]] of the entering steam in [[Kelvin|kelvin]] $[\pu{ K}]$ and $T_{2}$ is the temperature of the outgoing steam, also in kelvin.

In theory the best efficiency possible for a thermal power plant is $54.7\%$. This is because the highest temperature the material containing the steam could withstand is approximately $550\degree\pu{ C}$, or $823\pu{ K}$. The lowest possible outgoing temperature is $100\degree\pu{ C}$ ($373\pu{ K}$), since below this temperature it is no longer guaranteed to be steam. 
$$
\eta_{\text{max}}=1-\frac{373\pu{ K}}{823\pu{ K}}=54.7\%
$$
In practice, however, the practical best efficiency is around $45\%$.
# Environmental impact
Thermal power plants make use of [[Fossil Fuels|fossil fuels]] to produce heat and therefore steam. Burning these fuels produces by-products. [[Coal]] and [[Petroleum|oil]], for example, produce water, [[Carbon Dioxide|carbon dioxide]], [[Sulfur Dioxide|sulfur dioxide]], and dust/ash. At first, these by-products were not thought to be problematic, but over time their impacts became known. [[Natural Gas|Natural gas]] produces much less sulfur dioxide than coal and oil, but still has a sizeable carbon dioxide output.