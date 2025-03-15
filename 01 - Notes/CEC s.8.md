---
tags:
  - canadian-electrical-code
---
# 8-102 Voltage drop
## 1)
> The voltage drop in an installation shall be based on the connected load of the feeder or branch circuit if known; otherwise it shall be based on 80% of the rating of the overload or overcurrent device protecting the branch circuit or feeder, and not exceed
> 	a) 3% in a feeder or branch circuit; and
> 	b) 5% from the supply side of the consumer’s service (or equivalent) to the point of utilization.
> - [[Canadian Electrical Code|CEC, 25th Edition]]

The connected load voltage should be used if known, else use $80\%$ of the rating of the [[Overcurrent Device|overcurrent device]] to find the [[Voltage Drop|voltage drop]]. This calculated voltage drop can not be more than $3\%$ in a feeder or branch circuit and it can not be more than $5\%$ of the total service voltage.
# 8-104 Maximum circuit loading
## 5)
> Where a fused switch or circuit breaker is marked for continuous operation at 100% of the ampere rating of its overcurrent devices, the continuous load as determined from the calculated load shall not exceed the continuous operation marking on the fused switch or circuit breaker and
> 	a) except as required by Item b), shall not exceed 100% of the allowable ampacities of conductors selected in accordance with Section 4; or
> 	b) shall not exceed 85% of the allowable ampacities of single conductors selected in accordance with Section 4.
> - [[Canadian Electrical Code|CEC, 25th Edition]]

In other words, *if the equipment is designed to operate at 100% of its rating you can load the circuit to 100% capacity **if** the wiring is in a [[Raceway (Electrical)|raceway]] or [[Cable|cable]]. **If** the wiring is instead using single conductors, then you can load the circuit only to 85% capacity.* The ampacity of a given circuit is determined by the load of the circuit, and the [[Overcurrent Device|overcurrent device]] selected is determined by the ampacity (see [[CEC s.14#14-104|CEC s.14-104]])

However, in Canada, most equipment is designed for 80% load. This leads us to sentence 6)...
## 6)
>Where a fused switch or circuit breaker is marked for continuous operation at 80% of the ampere rating of its overcurrent devices, the continuous load as determined from the calculated load shall not exceed the continuous operation marking on the fused switch or circuit breaker and
>	a) except as required by Item b), shall not exceed 80% of the allowable ampacities of conductors selected in accordance with Section 4; or
>	b) shall not exceed 70% of the allowable ampacities of single conductors selected in accordance with Section 4.
> - [[Canadian Electrical Code|CEC, 25th Edition]]

That is, *since normal equipment is designed for 80% load in Canada, **if** the wiring is in a cable/raceway you can load the circuit to 80% capacity, **else** if it is a single conductor it can only be loaded to 70% capacity.*
# Calculated load for services and feeders
## 8-200 Single Dwellings
### 1)
> The calculated load for the service or feeder supplying a single dwelling shall be based on the greater of Item a) or b):
> a) 
> 	i) a basic load of $5000\ \pu{ W}$ for the first $90\ \pu{ m^2}$ of living area (see Rule [[CEC s.8#8-110 Determination of areas|8-110]]); plus
> 	ii) an additional $1000\ \pu{ W}$ for each $90\ \pu{ m^2}$ or portion thereof in excess of $90\ \pu{ m^2}$; plus
> 	iii) any electric space-heating loads provided for with demand factors as permitted in [[CEC s.62|Section 62]] plus any air-conditioning loads with a demand factor of 100%, subject to Rule [[CEC s.8#8-106 Use of demand factors|8-106]] 3); plus
> 	iv) any electric range load provided for as follows: $6000\ \pu{ W}$ for a single range plus $40\%$ of any amount by which the rating of the range exceeds $12\ \pu{ kW}$; plus
> 	v) any electric tankless water heaters or electric water heaters for steamers, swimming pools, hot tubs, or spas with a demand factor of $100\%$; plus
> 	vi) except as permitted by Rule [[CEC s.8#8-106 Use of demand factors|8-106]] 11), any electric vehicle supply equipment loads with a demand factor of $100\%$; plus
> 	vii) any loads provided for that have a rating in excess of $1500\ \pu{ W}$, in addition to those outlined in Items i) to vi), at
> 		A) $25\%$ of the rating of each load, if an electric range has been provided for; or
> 		B) $100\%$ of the combined load up to $6000\ \pu{ W}$, plus $25\%$ of the combined load that exceeds $6000\ \pu{ W}$, if an electric range has not been provided for; or
> b)
> 	i) $24\ 000\ \pu{ W}$ where the floor area, exclusive of the basement floor area, is $80\ \pu{ m^2}$ or more; or
> 	ii) $14\ 400\ \pu{ W}$ where the floor area, exclusive of the basement floor area, is less than $80\ \pu{ m^2}$.
# 8-304 Maximum number of outlets per circuit
## 1)
> Except as permitted by other Rules of this Code, the maximum number of outlets on any 2-wire branch circuit shall not exceed the following:
> 	a) 12 outlets for a 15 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 80%;
> 	b) 15 outlets for a 15 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 100%;
> 	c) 16 outlets for a 20 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 80%; and
> 	d) 20 outlets for a 20 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 100%.

| Rating  | Ampacity    | Max no. outlets |
| ------- | ----------- | --------------- |
| $80\%$  | $15\pu{ A}$ | $12$            |
| $80\%$  | $20\pu{ A}$ | $16$            |
| $100\%$ | $15\pu{ A}$ | $15$            |
| $100\%$ | $20\pu{ A}$ | $20$            |
**Note:** "Outlets" can be [[Electrical Receptacle|receptacles]] or [[Light Fixture|lights]]. In *residential* construction, lights and receptacles *can* be on the same circuit. In *commercial*/*industrial* applications, these loads are typically on separate circuits.

## 3)
> Where the connected load is known, the number of outlets shall be permitted to exceed the maximum number permitted in Subrule 1), provided that the load current does not exceed the continuous operation marking on the overcurrent device protecting the circuit.

If the connected load is something like lights, the load is known, and so long as the designer does not exceed the ampacity rating of the circuit, more than the maximum number of outlets may be used.