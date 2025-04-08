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
# 8-106 Use of demand factors
## 1)
> In any case other than a service calculated in accordance with Rules 8-200 and 8-202, where the design of an installation is based on requirements in excess of those given in this Section, the service and feeder capacities shall be increased accordingly.
## 2)
> Where two or more loads are installed so that only one can be used at any one time, the one providing the greatest demand shall be used in determining the calculated demand.
## 3)
> Where interlocks are installed to prevent simultaneous operation of electric space-heating and air-conditioning loads, whichever is the greater load shall be used in calculating the demand.
## 4)
> Where a feeder supplies loads of a cyclic or similar nature such that the maximum connected load will not be supplied at the same time, the ampacity of the feeder conductors shall be permitted to be based on the maximum load that may be connected at any one time.
## 5)
> Where a feeder or service supplies motor or air-conditioning loads, a demand factor as determined by a qualified person shall be permitted to be applied to these loads, provided that a deviation has been allowed in accordance with Rule 2-030.
## 6)
> The ampacity of conductors of feeders or branch circuits shall be in accordance with the Section(s) dealing with the respective equipment being supplied.
## 7)
> Notwithstanding the requirements of this Section, the ampacity of the conductors of a feeder or branch circuit need not exceed the ampacity of the conductors of the service or of the feeder from which they are supplied.
## 8)
> Where additional loads are to be added to an existing service or feeder, the augmented load shall be permitted to be calculated by adding the sum of the additional loads, with demand factors as permitted by this Code, to the maximum demand load of the existing installation as measured over the most recent 12-month period, but the new calculated load shall be subject to Rule 8-104 5) and 6).
## 9)
> For loads other than those calculated in accordance with Rules 8-200 and 8-202, feeder and service load calculations shall be permitted to be based on demonstrated loads, provided that such calculations are performed by a qualified person, as determined by the regulatory authority having jurisdiction.
## 10)
> Where electric vehicle supply equipment loads are controlled by an electric vehicle energy management system, the demand load for the electric vehicle supply equipment shall be equal to the maximum load allowed by the electric vehicle energy management system.
## 11)
> For the purposes of Rules 8-200 1) a) vi), 8-202 1) a) vii), 8-202 3) d), 8-204 1) d), 8-206 1) d), 8-208 1) d), and 8-210 c), the demand load for the electric vehicle supply equipment shall not be required to be considered in the determination of the calculated load where an electric vehicle energy management system as described in Subrule 10) performs the functions of 
> 	a) monitoring the consumer’s service, feeders, and branch circuits; and
> 	b) controlling the electric vehicle supply equipment loads in accordance with Rule 8-500.
# Calculated load for services and feeders
Service size is based on multiple factors including:
- type of building
- area of the building
- what power loads are in the building

Definitions:
- **Basic load**: the load of lighting and receptacle circuits, based on the outside dimensions of a specific area of building occupancy, as listed in Table [[CEC t.14|14]]. (No *power* loads)
![[CEC t.14]]
- **Calculated load**: the load calculated in accordance with the applicable requirements of this Section.
- **Demand factors**: applied to electrical loads to reduce the calculated load based on building area and type 
- **Service**: from utility transformer to building
- **Feeder**: from service to metered tenant
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
## 8-204 Schools
### 1)
> The calculated load for the service or feeder shall be based on the following:
> 	a) a basic load of $50\ \mathrm{W/m^2}$ of classroom area; plus
> 	b) $10\ \mathrm{W/m^2}$ of the remaining area of the building based on the outside dimensions; plus
> 	c) electric space-heating, air-conditioning, and total loads of other permanently connected equipment based on the rating of the equipment installed; plus
> 	d) except as permitted by Rule 8-106 10) or Rule 8-106 11), any electric vehicle supply equipment loads with a demand factor of $100\%$; plus
> 	e) cord-connected equipment intended for connection to receptacles rated more than $125\ \mathrm{V}$ or $20\ \mathrm{A}$ based on,
> 		i) $80\%$ of the rating of the receptacle; or
> 		ii) the rating of the equipment intended for connection to the receptacle.

**We will not be tested on EV stuff**. 

In summary, to calculate the service for a school:
1. $50\ \mathrm{W/m^2}$ for all classroom areas plus
2. $10\ \mathrm{W/m^2}$ for all non-classroom areas (based on exterior dimensions) plus
3. Any non-basic loads i.e. heating, air conditioning, computers, etc.
4. If the equipment is cord-connected and more than $125\ \mathrm{V}$/$20\ \mathrm{A}$, take $80\%$ of the receptacle rating or $100\%$ of the equipment rating.
### 2)
> Demand factors shall be permitted to be applied as follows:
> 	a) for a building with an area up to and including $900\ \mathrm{m^2}$ based on the outside dimensions:
> 		i) as permitted in section 62 for any electric space-heating loads provided for; and
> 		ii) $75\%$ for the balance of the load; and
> 	b) for a building with an area exceeding $900\ \mathrm{m^2}$ based on the outside dimensions:
> 		i) as permitted in section 62 for any electric space-heating loads provided for; and
> 		ii) the balance of the load shall be divided by the number of square metres to obtain a load-per-square-metre rating and the demand load may be considered the sum of
> 		A) $75\%$ of the load per square multiplied by 900; and
> 		B) $50\%$ of the load per square metre multiplied by the area of the building in excess of $900\ \mathrm{m^2}$.

To determine demand factors for non-basic loads:
1. If the building area $> 900\ \mathrm{m^2}$:
	a. Refer to section 62 for space-heating demand factors and
	b. take $75\%$ of the load rating
2. If the building area $<\ 900\ \mathrm{m^2}$:
	a. Refer to section 62 for space-heating demand factors and
	b. divide the load rating by the area to get the load per area rating. Take $75\%$ of this rating multiplied by $900$, and then take $50\%$ of this rating multiplied by the remainder.
---
**Example**
A school has an area of $6000\ \mathrm{m^2}$. $4500\ \mathrm{m^2}$ of this area is classroom area. In addition the school has the following loads:
- Air conditioning: $200\ \mathrm{kW}$
- Heating: Gas
- Cafeteria loads: $150\ \mathrm{kW}$
- Computers: $30\ \mathrm{kW}$
- Shops: $35\ \mathrm{kW}$
- Theatre lights: $10\ \mathrm{kW}$
- Parking lot lights: $3\ \mathrm{kW}$
- Elevator: $20\ \mathrm{kW}$

Step 1: $50\ \mathrm{W/m^2}$ for classroom area.
$$
\begin{align}
L &= 50\ \mathrm{W/m^2} \cdot 4500\ \mathrm{m^2} \\
&=225\ \mathrm{kW}
\end{align}
$$
Step 2: $10\ \mathrm{W/m^2}$ for non-classroom area.
$$
\begin{align}
L&=10\ \mathrm{W/m^2}\cdot 1500\ \mathrm{m^2} \\
&=15\ \mathrm{kW}
\end{align}
$$
$$
\begin{align}
L_{T}&=225\ \mathrm{kW}+15\ \mathrm{kW} \\
&=240\ \mathrm{kW}
\end{align}
$$
Step 3: Add together the other loads.
$$
\begin{align}
L_{\ \mathrm{other}}&=200\ \mathrm{kW}+150\ \mathrm{kW}+30\ \mathrm{kW}+35\ \mathrm{kW}+10\ \mathrm{kW}+3\ \mathrm{kW} + 20\ \mathrm{kW} \\
&=448\ \mathrm{kW}
\end{align}
$$
Step 4: Divide the *total load* by the *total area*.
$$
\begin{align}
R&=\frac{L_{T}+L_{\ \mathrm{other}}}{A} \\
&=\frac{240\ \mathrm{kW} + 448\ \mathrm{kW}}{6000\ \mathrm{m^2}} \\
&=114.667\ \mathrm{W/m^2}
\end{align}
$$
Step 5: Apply the factors in 8-204 2) b) ii).
$$
\begin{align}
L_{\ \mathrm{service-total}}&=(75\%\cdot R\cdot 900\ \mathrm{m^2}) + (50\%\cdot R \cdot 5100\ \mathrm{m^2}) \\
&=(75\% \cdot 114.667\ \mathrm{W/m^2} \cdot 900\ \mathrm{m^2})+(50\% \cdot 114.667\ \mathrm{W/m^2}\cdot 5100\ \mathrm{m^2}) \\
&=369.8\ \mathrm{kW}
\end{align}
$$
---
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