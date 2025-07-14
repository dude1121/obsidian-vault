---
tags:
  - canadian-electrical-code
---
# Section 8 — Circuit loading and demand factors
# Scope
## 8-002 Special terminology
**Basic load** - the load of lighting and receptacle circuits, based on the outside dimensions of a specific area of building occupancy, as listed in [[CEC t.14|Table 14]].

**Calculated load** - the load calculated in accordance with the applicable requirements of this Section.

**Demonstrated load** - historical maximum demand watt information recorded over at least a 24-month period for the same type of facility as the one in question, equated to watts per m$^2$.

**Electric vehicle energy management system** - a means used to control electric vehicle supply 
equipment loads through the process of connecting, disconnecting, increasing, or reducing electric 
power to the loads and consisting of any of the following: a monitor(s), communications equipment, a 
controller(s), a timer(s), and other applicable device(s).
# General
## 8-102 Voltage drop
> 1) The voltage drop in an installation shall be based on the connected load of the feeder or branch circuit if known; otherwise it shall be based on 80% of the rating of the overload or overcurrent device protecting the branch circuit or feeder, and not exceed
> 	a) 3% in a feeder or branch circuit; and
> 	b) 5% from the supply side of the consumer’s service (or equivalent) to the point of utilization.
> 2) Notwithstanding Subrule 1), where overcurrent devices are selected in accordance with other Sections of this Code, the voltage drop shall be based on the calculated demand load of the feeder or branch circuit.
> 3) Notwithstanding Subrule 1), wiring for general-use branch circuits rated at not more than $120\ \mathrm{V}$ or $20\ \mathrm{A}$ in dwelling units, with the insulated conductor length measured from the supply side of the consumer's service to the furthest point of utilization in accordance with the values in [[CEC t.68|Table 68]], shall be acceptable.
> 4) Notwithstanding Subrule 1), at industrial establishments where conditions of maintenance and supervision ensure use by qualified persons, the design shall ensure that the voltage at the point of utilization is within the rating or voltage tolerance of the connected device(s).

The connected load voltage should be used if known, else use $80\%$ of the rating of the [[Overcurrent Device|overcurrent device]] to find the [[Voltage Drop|voltage drop]]. This calculated voltage drop can not be more than $3\%$ in a feeder or branch circuit and it can not be more than $5\%$ of the total service voltage.
## 8-104 Maximum circuit loading
> 1) The ampere rating of a consumer's service, feeder, or branch circuit shall be the ampere rating of the overcurrent device protecting the circuit or the ampacity of the conductors, whichever is less.
> 2) The calculated load in a circuit shall not exceed the ampere rating of the circuit.
> 3) The calculated load in a consumer's service, feeder, or branch circuit shall be considered a continuous load unless it can be shown that in normal operation it will not persist for
> 	a) a total of more than $1\ \mathrm{h}$ in any $2\ \mathrm{h}$ period if the load does not exceed $225\ \mathrm{A}$; or
> 	b) a total of more than $3\ \mathrm{h}$ in any $6\ \mathrm{h}$ period if the load exceeds $225\ \mathrm{A}$.
> 4) The load of a cyclic or intermittent nature shall be classified as continuous unless it meets the requirements of Subrule 3).
> 5) Where a fused switch or circuit breaker is marked for continuous operation at 100% of the ampere rating of its overcurrent devices, the continuous load as determined from the calculated load shall not exceed the continuous operation marking on the fused switch or circuit breaker and
> 	a) except as required by Item b), shall not exceed 100% of the ampacities of conductors selected in accordance with [[CEC s.4|Section 4]]; or
> 	b) shall not exceed 85% of the ampacities of single conductors selected in accordance with [[CEC s.4|Section 4]].

In other words, *if the equipment is designed to operate at 100% of its rating you can load the circuit to 100% capacity **if** the wiring is in a [[Raceway (Electrical)|raceway]] or [[Cable|cable]]. **If** the wiring is instead using single conductors, then you can load the circuit only to 85% capacity.* The ampacity of a given circuit is determined by the load of the circuit, and the [[Overcurrent Device|overcurrent device]] selected is determined by the ampacity (see [[CEC s.14#14-104|CEC s.14-104]])

However, in Canada, most equipment is designed for 80% load. This leads us to sentence 6)...
>6) Where a fused switch or circuit breaker is marked for continuous operation at 80% of the ampere rating of its overcurrent devices, the continuous load as determined from the calculated load shall not exceed the continuous operation marking on the fused switch or circuit breaker and
>	a) except as required by Item b), shall not exceed 80% of the ampacities of conductors selected in accordance with [[CEC s.4|Section 4]]; or
>	b) shall not exceed 70% of the ampacities of single conductors selected in accordance with Section 4.

That is, *since normal equipment is designed for 80% load in Canada, **if** the wiring is in a cable/raceway you can load the circuit to 80% capacity, **else** if it is a single conductor it can only be loaded to 70% capacity.*
## 8-106 Use of demand factors
### Code excerpt
> 1) In any case other than a service calculated in accordance with Rules [[CEC s.8#8-200 Single Dwellings|8-200]] and [[CEC s.8#8-202 Apartment and similar buildings|8-202]], where the design of an installation is based on requirements in excess of those given in this Section, the service and feeder capacities shall be increased accordingly.
> 2) Where two or more loads are installed so that only one can be used at any one time, the one providing the greatest demand shall be used in determining the calculated demand.
> 3) Where interlocks are installed to prevent simultaneous operation of electric space-heating and air-conditioning loads, whichever is the greater load shall be used in calculating the demand.
> 4) Where a feeder supplies loads of a cyclic or similar nature such that the maximum connected load will not be supplied at the same time, the ampacity of the feeder conductors shall be permitted to be based on the maximum load that may be connected at any one time.
> 5) Where a feeder or service supplies motor or air-conditioning loads, a demand factor as determined by a qualified person shall be permitted to be applied to these loads, provided that a deviation has been allowed in accordance with [[CEC s.2#2-030 Deviation or postponement|Rule 2-030]].
> 6) The ampacity of conductors of feeders or branch circuits shall be in accordance with the Section(s) dealing with the respective equipment being supplied.
> 7) Notwithstanding the requirements of this Section, the ampacity of the conductors of a feeder or branch circuit need not exceed the ampacity of the conductors of the service or of the feeder from which they are supplied.
> 8) Where additional loads are to be added to an existing service or feeder, the augmented load shall be permitted to be calculated by adding the sum of the additional loads, with demand factors as permitted by this Code, to the maximum demand load of the existing installation as measured over the most recent 12-month period, but the new calculated load shall be subject to [[CEC s.8#8-104 Maximum circuit loading|Rule 8-104]] 5) and 6).
> 9) For loads other than those calculated in accordance with Rules [[CEC s.8#8-200 Single Dwellings|8-200]] and [[CEC s.8#|8-202]], feeder and service load calculations shall be permitted to be based on demonstrated loads, provided that such calculations are performed by a qualified person, as determined by the regulatory authority having jurisdiction.
> 10) Where electric vehicle supply equipment loads are controlled by an electric vehicle energy management system, the demand load for the electric vehicle supply equipment shall be equal to the maximum load allowed by the electric vehicle energy management system.
> 11) For the purposes of Rules [[CEC s.8#8-200 Single Dwellings|8-200]] 1) a) vi), 8-202 1) a) vii), 8-202 3) d), [[CEC s.8#8-204 Schools|8-204]] 1) d), 8-206 1) d), 8-208 1) d), and 8-210 c), the demand load for the electric vehicle supply equipment shall not be required to be considered in the determination of the calculated load where an electric vehicle energy management system as described in Subrule 10) performs the functions of 
> 	a) monitoring the consumer’s service, feeders, and branch circuits; and
> 	b) controlling the electric vehicle supply equipment loads in accordance with Rule 8-500.
---
### Summary
##### 1) Custom Installations
- If a design exceeds standard requirements (excluding Rules 8-200 and 8-202), service and feeder capacities must be increased accordingly.
##### 2) Mutually Exclusive Loads
- When only one of multiple loads can operate at a time, only the **largest** load is used for demand calculation.
##### 3) Interlocked Heating and A/C
- If interlocks prevent both systems from running together, use the **greater** of the two loads in the demand calculation.
##### 4) Cyclic Loads
- For feeders supplying non-simultaneous loads (e.g., cyclic), ampacity may be based on the **maximum possible load at one time**.
##### 5) Motor and A/C Demand Factors
- Qualified persons may apply demand factors to motor or A/C loads **if approved** under Rule 2-030.
##### 6) Equipment-Based Ampacity
- Feeder and branch circuit conductor ampacity must follow the **rules for the specific equipment** being supplied.
##### 7) Limiting Conductor Ampacity
- Feeder or branch circuit conductors **need not exceed** the ampacity of their upstream supply conductors.
##### 8) Adding Loads to Existing Installations
- For service upgrades, the **new load** may be calculated by adding the **new loads (with demand factors)** to the **maximum demand** from the past **12 months**. Subject to Rule 8-104(5) and (6).
##### 9) Demonstrated Load Calculations
- For non-residential loads, calculations **may be based on measured (demonstrated) loads** if done by a **qualified person**, as approved by the local authority.
##### 10) EV Energy Management Systems (EVEMS)
- If an EVEMS is used, the EV load is based on the **maximum load permitted by the EVEMS**.
##### 11) Exemption from EV Load Inclusion
- In rules referencing EV loads (e.g., 8-200, 8-202), EV loads **do not need to be included** in the calculated load if an EVEMS:
  - **a)** Monitors the service, feeders, and branch circuits
  - **b)** Controls EV load per Rule 8-500
---
## 8-108 Number of spaces for branch circuit overcurrent devices
> 1) Panelboards installed in single dwellings shall, at the time of the original installation, have at least four additional spaces left for future overcurrent devices with provision for a two-pole device.
> 2) Panelboards installed in each dwelling unit in an apartment or similar building shall, at the time of the original installation, have at least two additional spaces left for future overcurrent devices with provision for a two-pole device.
## 8-110 Determination of areas
> The living area designated in Rules [[CEC s.8#8-200 Single Dwellings|8-200]] and [[CEC s.8#8-202 Apartment and similar buildings|8-202]] shall be determined from inside dimensions and include the sum of
> 	a) 100% of the area on the ground floor;
> 	b) 100% of any areas above the ground floor used for living purposes; and
> 	c) 75% of only those areas below the ground floor that exceed $1.8\ \mathrm{m}$ in height, measured from the lowest part of the ceiling assembly to the ground or other surface below it.
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
### Code excerpt
> 1) The calculated load for the service or feeder supplying a single dwelling shall be based on the greater of Item a) or b):
> 	a) 
> 		i) a basic load of $5000\ \pu{ W}$ for the first $90\ \pu{ m^2}$ of living area (see Rule [[CEC s.8#8-110 Determination of areas|8-110]]); plus
> 		ii) an additional $1000\ \pu{ W}$ for each $90\ \pu{ m^2}$ or portion thereof in excess of $90\ \pu{ m^2}$; plus
> 		iii) any electric space-heating loads provided for with demand factors as permitted in [[CEC s.62|Section 62]] plus any air-conditioning loads with a demand factor of 100%, subject to Rule [[CEC s.8#8-106 Use of demand factors|8-106]] 3); plus
> 		iv) any electric range load provided for as follows: $6000\ \pu{ W}$ for a single range plus $40\%$ of any amount by which the rating of the range exceeds $12\ \pu{ kW}$; plus
> 		v) any electric tankless water heaters or electric water heaters for steamers, swimming pools, hot tubs, or spas with a demand factor of $100\%$; plus
> 		vi) except as permitted by Rule [[CEC s.8#8-106 Use of demand factors|8-106]] 11), any electric vehicle supply equipment loads with a demand factor of $100\%$; plus
> 		vii) any loads provided for that have a rating in excess of $1500\ \pu{ W}$, in addition to those outlined in Items i) to vi), at
> 			A) $25\%$ of the rating of each load, if an electric range has been provided for; or
> 			B) $100\%$ of the combined load up to $6000\ \pu{ W}$, plus $25\%$ of the combined load that exceeds $6000\ \pu{ W}$, if an electric range has not been provided for; or
> 	b)
> 		i) $24\ 000\ \pu{ W}$ where the floor area, exclusive of the basement floor area, is $80\ \pu{ m^2}$ or more; or
> 		ii) $14\ 400\ \pu{ W}$ where the floor area, exclusive of the basement floor area, is less than $80\ \pu{ m^2}$.
> 2) The calculated load for the consumer's service or feeder conductors supplying two or more dwelling units of row housing shall be based on
> 	a) the calculated load in the dwelling unit, as determined in accordance with Subrule 1), excluding electric vehicle supply equipment loads described in [[CEC s.8#8-202 Apartment and similar buildings|Rule 8-202]] 1) a) vii), any electric space-heating loads, and any air-conditioning loads, with application of demand factors to the calculated loads as required by [[CEC s.8#8-202 Apartment and similar buildings|Rule 8-202]] 3) a) i) to v); plus
> 	b) the requirements of [[CEC s.8#8-202 Apartment and similar buildings|Rule 8-202]] 3) b) to e).
> 3) Notwithstanding [[CEC s.86#86-302 Connected Load|Rule 86-302]], the total load calculated in accordance with either Subrule 1) or 2) shall not be considered to be a continuous load for application of [[CEC s.8#8-104 Maximum circuit loading|Rule 8-104]].
---
### Summary
##### 1) Load Calculation for a Single Dwelling
Use the greater of:
###### a) Calculated Load:
- **5000 W** for the first **90 m²** of living area
- **1000 W** for each additional **90 m²** (or portion thereof)
- Plus the following at **100% demand** unless noted:
  - Electric space heating (per Section 62)
  - Air-conditioning
  - Electric range:
    - **6000 W**, plus **40%** of any portion exceeding **12 kW**
  - Tankless water heaters, hot tubs, spas, pools
  - EV supply equipment (unless Rule 8-106(11) applies)
  - Additional loads >1500 W:
    - **25%** of each load if a range is present
    - If no range:
      - **100%** of first **6000 W**
      - **25%** of any portion above **6000 W**
###### b) Minimum Load Based on Floor Area:
- **24000 W** if floor area ≥ **80 m²** (excluding basement)
- **14400 W** if floor area < **80 m²** (excluding basement)
##### 2) Load Calculation for Row Housing (Multiple Units)
- Use load from Subrule 1), but **exclude**:
  - EV supply equipment
  - Space heating
  - Air-conditioning
- Apply demand factors per Rule 8-202(3)(a)(i)–(v)
- Add space heating, A/C, EVs, and common area loads per Rule 8-202(3)(b)–(e)
##### 3) Load is Not Continuous
- Total load calculated under Subrules 1) or 2) **is not considered a continuous load** under Rule 8-104
---
## 8-202 Apartment and similar buildings
### Code excerpt
> 1) The calculated load for the service or feeder from a main service supplying loads in dwelling units shall be the greater of Item a) or b):
> 	a)
> 		i) a basic load of $3500\ \mathrm{W}$ for the first $45\ \mathrm{m^2}$ of living area (see [[CEC s.8#8-110 Determination of areas|Rule 8-110]]); plus
> 		ii) an additional $1500\ \mathrm{W}$ for the second $45\ \mathrm{m^2}$ or portion thereof; plus
> 		iii) an additional $1000\ \mathrm{W}$ for each additional $90\ \mathrm{m^2}$ or portion thereof in excess of the initial $90\ \mathrm{m^2}$; plus
> 		iv) any electric space-heating loads provided for with demand factors as permitted in [[CEC s.62|Section 62]] plus any air-conditioning loads with a demand factor of 100%, subject to [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 3); plus
> 		v) any electric range load provided for as follows: $6000\ \mathrm{W}$ for a single range plus 40% of any amount by which the rating of the range exceeds $12\ \mathrm{kW}$; plus
> 		vi) any electric tankless water heaters or electric water heaters for steamers, swimming pools, hot tubs, or spas with a demand factor of 100%; plus
> 		vii) any electrical vehicle supply equipment loads, if they are supplied from a panelboard installed in a dwelling unit, with a demand factor of 100%; plus
> 		viii) any loads provided for, in addition to those outlined in Items i) to vi), at
> 			A) 25% of the rating of each load with a rating in excess of $1500\ \mathrm{W}$, if an electric range has been provided for; or
> 			B) 25% of the rating of each load with a rating in excess of $1500\ \mathrm{W}$ plus $6000\ \mathrm{W}$, if an electric range has not been provided for; or
> 	b) $60\ \mathrm{A}$.
> 2) The total load calculated in accordance with Subrule 1) and Subrule 3) a), b), and c) shall not be considered to be a continuous load for the application of [[CEC s.8#8-104 Maximum circuit loading|Rule 8-104]]. 
> 3) The calculated load for the consumer's service or feeder supplying two or more dwelling units shall be based on the calculated load obtained from Subrule 1) a) and the following:
> 	a) excluding any electric vehicle supply equipment loads, electric space-heating loads and any air-conditioning loads, the load shall be considered to be
> 		i) 100% of the calculated load in the unit having the heaviest load; plus
> 		ii) 65% of the sum of the calculated loads in the next 2 units having the same or next smaller loads to those specified in Item i); plus
> 		iii) 40% of the sum of the calculated loads in the next 2 units having the same or next smaller loads to those specified in Item ii); plus
> 		iv)  25% of the sum of the calculated loads in the next 15 units having the same or next smaller loads to those specified in Item iii); plus
> 		v) 10% of the sum of the calculated loads in the remaining units;
> 	b) if electric space heating is used, the sum of all the space-heating loads as determined in accordance with the requirements of [[CEC s.62|Section 62]] shall be added to the load determined in accordance with Item a), subject to [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 3);
> 	c) if air conditioning is used, the sum of all the air-conditioning loads shall be added, with a demand factor of 100%, to the load determined in accordance with Items a) and b), subject to [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 3);
> 	d) except as permitted by [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 10) or [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 11), any electric vehicle supply equipment loads not supplied from a panelboard installed in a dwelling unit in accordance with [[CEC s.8#8-202 Apartment and similar buildings|Rule 8-202]] 1) a) vii), shall be added with a demand of 100%; and
> 	e) in addition, any lighting, heating, and power loads not located in dwelling units shall be added with a demand factor of 75%.
> 4) The ampacity of feeder conductors from a service supplying loads not located in dwelling units shall be not less than the rating of the equipment installed with demand factors as permitted by this Code.
---
### Summary
#### 1) Load Calculation for a Single Dwelling Unit
Use the **greater** of:
##### a) Calculated Load:
- **3500 W** for the first **45 m²** of living area
- **1500 W** for the second **45 m²** (or portion thereof)
- **1000 W** for each additional **90 m²** (or portion thereof)
- **Plus** the following, at **100% demand** unless otherwise noted:
  - Electric space heating (per **Section 62**)
  - Air-conditioning
  - Electric range:
    - **6000 W**, plus **40%** of any portion exceeding **12 kW**
  - Tankless water heaters, pool/hot tub/spa heaters
  - EV supply equipment (if from panelboard in unit)
  - Additional loads over **1500 W**:
    - **25%** of each load **if a range is present**
    - **25% + 6000 W** of each load **if no range is present**
##### b) Minimum:
- **60 A**
#### 2) Continuous Load Status
- Load calculated under 1) and 3) a–c) **is not considered a continuous load** (per Rule 8-104).
#### 3) Load Calculation for Two or More Dwelling Units
##### a) Basic Load (excluding space heating, A/C, and EVs):
- **100%** of the unit with the highest load
- **65%** of the next 2 largest units
- **40%** of the next 2 units
- **25%** of the next 15 units
- **10%** of all remaining units
##### b) Space Heating:
- Add the **total space heating load** (per Section 62), subject to Rule 8-106(3)
##### c) Air Conditioning:
- Add **total A/C load at 100%**, subject to Rule 8-106(3)
##### d) EV Supply Equipment:
- Add **EVSE loads at 100%** if not from in-unit panelboard
##### e) Common Area Loads:
- Add **lighting, heating, power (non-dwelling)** at **75% demand**
#### 4) Feeder Ampacity
- Feeder conductors supplying non-dwelling loads must be rated **not less than the equipment rating**, with permitted demand factors applied.
---
## 8-204 Schools
> 1) The calculated load for the service or feeder shall be based on the following:
> 	a) a basic load of $50\ \mathrm{W/m^2}$ of classroom area; plus
> 	b) $10\ \mathrm{W/m^2}$ of the remaining area of the building based on the outside dimensions; plus
> 	c) electric space-heating, air-conditioning, and total loads of other permanently connected equipment based on the rating of the equipment installed; plus
> 	d) except as permitted by [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 10) or [[CEC s.8#8-106 Use of demand factors|Rule 8-106]] 11), any electric vehicle supply equipment loads with a demand factor of $100\%$; plus
> 	e) cord-connected equipment intended for connection to receptacles rated more than $125\ \mathrm{V}$ or $20\ \mathrm{A}$ based on,
> 		i) $80\%$ of the rating of the receptacle; or
> 		ii) the rating of the equipment intended for connection to the receptacle.

In summary, to calculate the service for a school:
1. $50\ \mathrm{W/m^2}$ for all classroom areas plus
2. $10\ \mathrm{W/m^2}$ for all non-classroom areas (based on exterior dimensions) plus
3. Any non-basic loads i.e. heating, air conditioning, computers, etc.
4. If the equipment is cord-connected and more than $125\ \mathrm{V}$/$20\ \mathrm{A}$, take $80\%$ of the receptacle rating or $100\%$ of the equipment rating.

> 2) Demand factors shall be permitted to be applied as follows:
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
## 8-212 Exit sign, emergency lighting, and show window loads
> 1) Where a panel is supplying specific types of lighting, such as exit signs or emergency lighting, which may be located throughout a building such that it is impossible to calculate the area served, the connected load of the circuits involved shall be used in determining a feeder size.
> 2) For show window lighting installations, the demand load shall be determined on the assumption that not less than $650\ \mathrm{W/m}$ will be required measured along the base of the window(s), except that a lower figure shall be permitted where a deviation has been allowed in accordance with [[CEC s.2#2-030 Deviation or postponement|Rule 2-030]].
# Branch circuits
## 8-300 Branch circuits supplying electric ranges
> 1) Conductors of a branch circuit supplying a range in a dwelling unit shall be considered as having a demand of
> 	a) $8\ \mathrm{kW}$ where the rating of the range does not exceed $12\ \mathrm{kW}$; or
> 	b) $8\ \mathrm{kW}$ plus 40% of the amount by which the rating of the range exceeds $12\ \mathrm{kW}$.
> 2) For the purposes of Subrule 1), two or more separate built-in cooking units shall be permitted to be considered as one range.
> 3) For ranges or cooking units installed in commercial, industrial, and institutional establishments, the demand shall be considered as not less than the rating.
> 4) The demand loads given in this Rule shall not apply to cord-connected hotplates, rangettes, or other appliances.
## 8-302 Branch circuits supplying data processing equipment
> The total connected load of a branch circuit supplying one or more units of data processing equipment shall be considered to be a continuous load for the application of [[CEC s.8#8-104 Maximum circuit loading|Rule 8-104]].
## 8-304 Maximum number of outlets per circuit
> 1) Except as permitted by other Rules of this Code, the maximum number of outlets on any 2-wire branch circuit shall not exceed the following:
> 	a) 12 outlets for a 15 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 80%;
> 	b) 15 outlets for a 15 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 100%;
> 	c) 16 outlets for a 20 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 80%; and
> 	d) 20 outlets for a 20 A branch circuit where the fused switch or circuit breaker is marked for continuous operation at 100%.
> 2) Except as permitted by Subrule 3), when a receptacle is used as an outlet for the application of Subrule 1), it shall be considered as
> 	a) 1 outlet per duplex receptacle;
> 	b) 1.5 outlets per triplex receptacle; and
> 	c) 2 outlets per quadruplex receptacle.
> 3) Where the connected load is known, the number of outlets shall be permitted to exceed the maximum number permitted in Subrule 1), provided that the load current does not exceed the continuous operation marking on the overcurrent device protecting the circuit.
> 4) Where fixed multi-outlet assemblies are used, each $1.5\ \mathrm{m}$ or fraction thereof of each separate and continuous length shall be be counted as one outlet, but in locations where a number of electrical appliances are likely to be used simultaneously, each $300\ \mathrm{mm}$ or fraction thereof shall be counted as one outlet.

| Rating  | Ampacity    | Max no. outlets |
| ------- | ----------- | --------------- |
| $80\%$  | $15\pu{ A}$ | $12$            |
| $80\%$  | $20\pu{ A}$ | $16$            |
| $100\%$ | $15\pu{ A}$ | $15$            |
| $100\%$ | $20\pu{ A}$ | $20$            |
**Note:** "Outlets" can be [[Electrical Receptacle|receptacles]] or [[Light Fixture|lights]]. In *residential* construction, lights and receptacles *can* be on the same circuit. In *commercial*/*industrial* applications, these loads are typically on separate circuits.

If the connected load is something like lights, the load is known, and so long as the designer does not exceed the ampacity rating of the circuit, more than the maximum number of outlets may be used.