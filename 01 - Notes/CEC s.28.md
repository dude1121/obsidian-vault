---
tags:
  - canadian-electrical-code
---
# Section 28 — Motors and generators
# 28-010 Special terminology
**Service** - Relates to the nature of the mechanical load. 
**Continuous duty** - "any application of a motor where the motor can operate continuously with load under  any normal or abnormal condition of use"
**Locked rotor current rating** - a current rating marked on electric equipment or, where not marked, deemed to be equal to six times the full load current rating from the nameplate of the equipment or from Table [[CEC t.44|44]] or [[CEC t.45|45]] as applicable.
**Non-continuous duty** - start and stop types of load. e.g. elevators, conveyors, presses
**Service factor** - a multiplier that, when applied to the rated horsepower of an ac motor, to the rated armature current of a dc motor, or to the rated output of a [[Generator|generator]], indicates a permissible loading that may be carries continuously at rated voltage and frequency. For example, typical values for the service factor range from $1.0-1.2$, so if the service factor was $1.1$ then a $10\pu{ hp}$ could run at $11\pu{ hp}$.

![[CEC t.44]]
![[CEC t.45]]
# Wiring methods
## 28-106 Insulated conductors - individual motors
> 1) The insulated conductors of a branch circuit supplying a motor for use on continuous duty service shall have an ampacity not less than $125\%$ of the full load current rating of the motor.
> 2) The insulated conductors of a branch circuit supplying a motor for use on non-continuous duty service shall have an ampacity not less than the current value obtained by multiplying the full load current rating of the motor by the applicable percentage given in [[CEC t.27|table 27]] for the duty involved, or varying duty service where a deviation has been allowed in accordance with [[CEC s.28#2-030 Deviation or postponement|Rule 2-030]] by a percentage less than that specified in [[CEC t.27|Table 27]].
![[CEC t.27]]
## 28-108 Insulated conductors - Two or more motors
> 1) Insulated conductors supplying a group of two or more motors shall have an ampacity not less than
> 	<span>&emsp;</span>a) 125% of the full load current rating of the motor having the largest full load current rating plus the full load current ratings of all the other motors in the group, where all motors in the group are for use on continuous duty service
> 	<span>&emsp;</span>b) the total of the calculated currents determined in accordance with Rule [[CEC s.28#28-106 Insulated conductors - individual motors|28-106]] for each motor, where all motors in the group are for use on non-continuous duty service; or
> 	<span>&emsp;</span>c) the total of the following, where the group consists of two or more motors for use on both continuous and non-continuous duty service:
> 		<span>&emsp;</span><span>&emsp;</span>i) 125% of the current of the motor having the largest full load current rating for use on continuous duty service
>		<span>&emsp;</span><span>&emsp;</span>ii) the full load current ratings of all other motors for use on continuous duty service; and
> 		<span>&emsp;</span><span>&emsp;</span>iii) the calculated current determined in accordance with Rule [[CEC s.28#2)|28-106 2)]] for motors for use on non-continuous duty service. 
> 2) Where the circuitry is interlocked in order to prevent all motors of the group from running at the same time, the size of the conductors feeding the group shall be permitted to be determined for the motor, or group of motors operating at the same time, that has the largest rating selected as determined in Subrule 1).
> 3) Demand factors shall be permitted to be applied where the character of the motor loading justifies reduction of the ampacity of the insulated conductors to less than the ampacity specified in Subrule 1), provided that
> 	<span>&emsp;</span>a) the insulated conductors have sufficient ampacity for the maximum demand load; and
> 	<span>&emsp;</span>b) the rating or setting of the overcurrent devices protecting them is in accordance with [[CEC s.28#28-204 Feeder overcurrent protection|Rule 28-204]]. 
## 28-110 Feeder conductors
> 1) Where a feeder supplies both motor loads and other loads, the ampacity of the insulated conductors shall be calculated in accordance with rules [[CEC s.28#28-106 Insulated conductors - individual motors|28-106]] and [[CEC s.28#28-108 Insulated conductors - Two or more motors|28-108]] plus the requirements of the other loads. 
> 2) The ampacity of a tap from a feeder to a single set of overcurrent devices protecting a motor branch circuit shall not be less than that of the feeder, except that the ampacity of the tap shall be permitted to be calculated in accordance with Rules [[CEC s.28#28-106 Insulated conductors - individual motors|28-106]] and [[CEC s.28#28-108 Insulated conductors - Two or more motors|28-108]] if the tap does not exceed
> 	<span>&emsp;</span>a) $3\ \mathrm{m}$ in length and is enclosed in metal; or
> 	<span>&emsp;</span>b) $7.5\ \mathrm{m}$ in length, has an ampacity not less than one-third that of the feeder, and is suitably protected from mechanical damage. 

In other words, the conductor sizing for a circuit with a motor and other loads on it requires first finding the motor load conductors and then adding the other loads.
# Overcurrent protection
## 28-200 Branch circuit overcurrent protection
> 1) Each ungrounded conductor of a motor branch circuit shall be protected by an overcurrent device in accordance with Subrules 2) to 5).
> 2) The overcurrent device required by subrule 1)  shall be
> 	<span>&emsp;</span>a) a non-time-delay [[Fuse|fuse]];
> 	<span>&emsp;</span>b) a time-delay fuse;
> 	<span>&emsp;</span>c) an inverse-time [[Circuit Breaker|circuit breaker]];
> 	<span>&emsp;</span>d) an instantaneous-trip (magnetic only) circuit interrupter applied in accordance with [[CEC s.28#28-210 Instantaneous-trip circuit breakers|Rule 28-210]]; or
> 	<span>&emsp;</span>e) a self-protected combination motor controller selected in accordance with [[CEC s.28#28-500 Control Required|Rule 28-500]].
> 3) The rating of the overcurrent device required by Subrule 1) shall
> 	<span>&emsp;</span>a) not exceed the values given in [[CEC t.29|table 29]] using the rated full load current of the motor, except that an overcurrent device having a minimum rating or setting of $15\pu{ A}$ shall be permitted even though it exceeds the values specified in [[CEC t.29|Table 29]]; and
> 	<span>&emsp;</span>b) for a branch circuit supplying two or more motors, not exceed the maximum value permitted by [[CEC s.28#28-206 Grouping of motors on a single branch circuit|Rule 28-206]].
![[CEC t.29]]
> 4) Where an overcurrent device rated in accordance with Subrule 3) a) will not permit the motor to start, the rating or setting of the overcurrent device shall be permitted to be increased as follows:
> 	<span>&emsp;</span>a) for a non-time-delay fuse, not more than
> 		<span>&emsp;</span><span>&emsp;</span>i) 400% of the motor full load current, for fuses rated up to $600\ \mathrm{A}$; or
> 		<span>&emsp;</span><span>&emsp;</span>ii) 300% of the motor full load current, for fuses rated $601$ to $6000\ \mathrm{A}$;
> 	<span>&emsp;</span>b) for a time-delay fuse, not more than 225% of the motor full load current; and
> 	<span>&emsp;</span>c) for an inverse time circuit breaker, not more than
> 		<span>&emsp;</span><span>&emsp;</span>i) 400% of the motor full load current, for circuit breakers rated up to $100\ \mathrm{A}$; or
> 		<span>&emsp;</span><span>&emsp;</span>ii) 300% of the motor full load current, for circuit breakers rated greater than $100\ \mathrm{A}$.
> 5) Where the overcurrent device required by Subrule 1) is a thermal magnetic circuit breaker that has separate instantaneous-trip settings, the instantaneous-trip setting shall not be greater than that specified in [[CEC s.28#28-210 Instantaneous-trip circuit breakers|Rule 28-210]].
## 28-202 Overcurrent protection marked on equipment
> Where branch circuit protective device characteristics and ratings or settings are specified in the marking of motor control equipment, they shall not be exceeded, notwithstanding any greater rating or setting permitted by [[CEC s.28#28-200 Branch circuit overcurrent protection|Rule 28-200]].
## 28-204 Feeder overcurrent protection
> 1) For a feeder supplying motor branch circuits only, the ratings or settings of the feeder overcurrent device shall not exceed the calculated value of the overcurrent devices permitted by Rule [[CEC s.28#28-200 Branch circuit overcurrent protection|28-200]] for the motor that is permitted the highest rated overcurrent devices of any motor supplied by the feeder, plus the sum of the full load current ratings of all other motors that will be in operation at the same time.
> 2) Where a feeder supplies a group of motors, two or more of which are required to start simultaneously, and the feeder overcurrent devices as calculated in accordance with Subrule 1) are not sufficient to allow the motors to start, the rating or setting of the feeder overcurrent devices shall be permitted to be increased as necessary, to a maximum that does not exceed the rating permitting for a single motor having a full load current rating not less than the sum of the full load current ratings of all other motors that will be in operation at the same time, provided that this value does not exceed $300\%$ of the ampacity of the feeder conductors.
> 3) Where a feeder supplies one or more motor branch circuits together with other loads, the overcurrent protection required shall be determined by calculating the overcurrent protection required for the motor circuits and adding to this value the requirements of the other loads supplied by the feeder.
> 4) Where a demand factor has been applied as permitted in [[CEC s.28#28-108 Insulated conductors - Two or more motors|Rule 28-108]] 3), the rating or setting of the overcurrent device(s) protecting a feeder shall not exceed the ampacity of the feeder, except as permitted by [[CEC s.14#14-104 Rating of overcurrent devices|Rule 14-104]] and [[CEC t.13|Table 13]].

Similar to [[CEC s.28#1)|here]], the overcurrent protection is first found by determining the motor circuit overcurrent protection and then adding to it the requirements of the other loads.
## 28-206 Grouping of motors on a single branch circuit
> Two or more motors shall be permitted to be grouped under the protection of a single set of branch circuit overcurrent devices having a rating or setting calculated in accordance with [[CEC s.28#28-204 Feeder overcurrent protection|Rule 28-204]] 1), provided that the protection conforms to one of the following:
> 	<span>&emsp;</span>a) the rating or setting of the overcurrent devices does not exceed $15\ \mathrm{A}$;
> 	<span>&emsp;</span>b) protection is provided for the control equipment of the motors by having the branch circuit overcurrent devices rated or set at
> 		<span>&emsp;</span><span>&emsp;</span>i) values not in excess of those marked on the control equipment for the lowest rated motor of the group as suitable for the protection of that control equipment; or
> 		<span>&emsp;</span><span>&emsp;</span>ii) in the absence of such markings, values not in excess of 400% of the full load current of the lowest rated motor;
> 	<span>&emsp;</span>c) the motors are used on a machine tool or woodworking machine under the following conditions:
> 		<span>&emsp;</span><span>&emsp;</span>i) the control equipment is arranged so that all contacts that open motor primary circuits are in enclosures, either forming part of the machine base or for separate mounting, that have a wall thickness not less than $1.69\ \mathrm{mm}$ for steel, $2.4\ \mathrm{mm}$ for malleable cast iron, or $6.3\ \mathrm{mm}$ for other case metal; that have hinged doors with substantial catches; and that have no opening to the floor or the foundation on  which the machine rests; and
> 		<span>&emsp;</span><span>&emsp;</span>ii) the rating or setting of the branch circuit overcurrent protection is not greater than that permitted by [[CEC t.29|Table 29]] for the full load current rating of the largest motor in the group, plus the sum of the full load current ratings of all other motors in the group that may be in operation at one time, but in no case more than $200\ \mathrm{A}$ at $250\ \mathrm{V}$ or less or $100\ \mathrm{A}$ at voltages from $251$ to $1000\ \mathrm{V}$;
> 	<span>&emsp;</span>d) all the motors are operated by a single controller, as provided for in [[CEC s.28#28-500 Control required|Rule 28-500]] 3) d);
> 	<span>&emsp;</span>e) where a deviation is allowed in accordance with [[CEC s.2#2-030 Deviation or postponement|Rule 2-030]] for the group of motors that form part of the coordinated drive of a single machine or process, whereby the failure of one motor to operate creates a hazard unless all the other motors in the group are stopped; or
> 	<span>&emsp;</span>f) the motors are contained within and form part of refrigeration equipment on a $120\ \mathrm{V}$ branch circuit protected at not more than $20\ \mathrm{A}$ where each motor is rated not more than $1\ \mathrm{hp}$ and has a full load current rating of not more than $6\ \mathrm{A}$.
## 28-210 Instantaneous-trip circuit breakers
> When used for branch circuit protection, instantaneous-trip circuit breakers shall be part of a combination motor starter or controller that also provides overload protection and
> <span>&emsp;</span>a) rated or adjusted, for an ac motor, to trip at not more than $1300\%$ of the motor full load current or at not more than $215\%$ of the motor locked rotor current, where given, except that ratings or settings for trip currents need not be less than $15\pu{ A}$; or
> <span>&emsp;</span>b) rated or adjusted, for a dc motor rated at $50\pu{\! hp}$ or less, to trip at not more than $250\%$ of the motor full load current, or for a dc motor rated at more than $50\ \pu{ hp}$, to trip at not more than $200\%$ of the motor full load current.
## 28-306 Rating or trip selection of overload devices
> 1) Overload devices responsive to motor current, if of the fixed type, shall be selected or rated or, if of the adjustable type, shall be set to trip at not more than the following:
> 	<span>&emsp;</span>a) 125% of the full load current rating of a motor having a marked service factor of 1.15 or greater; or
> 	<span>&emsp;</span>b) 115% of the full load current rating of a motor that does not have a marked service factor or where the marked service factor is less than 1.15.

 That is, the overload device must be rated for 125% of the FLA (full load amps) if the service factor $\geq 1.15$ or 115% of the FLA if it is $<1.15$ or not marked at all.
## 28-308 Overload protection not required
> Overload protection shall not be required for motors complying with any of the following:
> a) a manually started motor rated at $1\pu{\! hp}$ or less that is continuously attended while in operation and is on
> 	i) a branch circuit having overcurrent protection rated or set at not more than $15\ \pu{ A}$; or
> 	ii) an individual branch circuit having overcurrent protection as required by [[CEC t.29|Table 29]] if it can be readily determined from the starting location that the motor is running;
> b) an automatically started motor having a rating of $1\ \pu{ hp}$ or less forming part of an assembly equipped with other safety controls that protect the motor from damage due to stalled rotor current and on which a nameplate, located so that it is visible after installation, indicates that such protection features are provided; or
> c) a motor that conforms with CDA C22.2 No. 77.

# Control
## 28-500 Control required
> 1) Except as permitted by Subrule 3), each motor shall be provided with a motor starter or controller for starting and stopping it that has a rating in horsepower not less than the rating of the motor it serves.
> 2) A motor controller need not open the circuit in all ungrounded conductors to a motor unless it also serves as a disconnecting means.
> 3) The motor starter or controller specified in Subrule 1) shall not be required for motors in the following applications: 
> 	<span>&emsp;</span>a) a single-phase portable motor rated at $1/3\ \mathrm{hp}$ or less connected by means of a receptacle and attachment plug rated not in excess of $15\ \mathrm{A}$, $125\ \mathrm{V}$;
> 	<span>&emsp;</span>b) a motor controlled by a manually operated general-use switch complying with [[CEC s.14#14-510 Use and rating of manually operated general-use ac switches|Rule 14-510]] having an ampere rating not less than 125% of the full load current rating of the motor;
> 	<span>&emsp;</span>c) a 2-wire portable ac or dc motor having a rating not in excess of $1/3\ \mathrm{hp}$, $125\ \mathrm{V}$ controlled by a horsepower rated single-pole motor switch;
> 	<span>&emsp;</span>d) two or more motors that are required to operate together shall be permitted to be operated from a single controller; or
> 	<span>&emsp;</span>e) for a motor where the controller is specifically designed for use with that motor, it need not be rated in horsepower.
## 28-600 Disconnecting means required
> 1) Except as permitted by Subrules 2) and 3), a separate disconnecting means shall be provided for
> 	<span>&emsp;</span>a) each motor branch circuit;
> 	<span>&emsp;</span>b) each motor starter or controller; and
> 	<span>&emsp;</span>c) each motor.
> 2) A single disconnecting means shall be permitted to serve more than one of the functions described in Subrule 1).
> 3) A single disconnecting means shall be permitted to serve two or more motors and their associated starting and control equipment grouped on a single branch circuit.
## 28-602 Types and ratings of disconnecting means
> 1) A disconnecting means for a motor branch circuit shall be
> 	<span>&emsp;</span>a) a manually operable fused or unfused motor-circuit switch that complies with Rule [[CEC s.14#14-010 Protective and control devices required|14-010]] b)  and has a horsepower rating not less than that of the motor it serves;
> 	<span>&emsp;</span>b) a moulded case switch or circuit breaker that complies with Rule [[CEC s.14#14-010 Protective and control devices required|14-010]] b) and has a current rating not less than 115% of the full load current rating of the motor it serves;
> 	<span>&emsp;</span>c) an instantaneous-trip circuit breaker that complies with Rules [[CEC s.14#14-010 Protective and control devices required|14-010]] b) and [[CEC s.28#28-210 Instantaneous-trip circuit breakers|28-210]];
> 	<span>&emsp;</span>d) an equivalent device that opens all ungrounded conductors of the branch circuit simultaneously and is capable of safely making and interrupting the locked rotor current of the connected load;
> 	<span>&emsp;</span>e) a single plug fuse for a branch circuit having one grounded conductor feeding a 2-wire single-phase or dc motor rated at not more than $1/3\ \pu{ hp}$, provided that it is used only as an isolating means and is not used to interrupt current; or
> 	<span>&emsp;</span>f) the draw-out feature of a high-voltage motor starter or controller of the draw-out type that complies with Rule [[CEC s.14#14-010 Protective and control devices required|14-010]] b), provided that it is used only as an isolating means and is not used to interrupt current.
> 2) A disconnecting means serving a group of motors on a single branch circuit shall have
> 	<span>&emsp;</span>a) a current rating not less than 115% of the full load current rating of the largest motor in the group plus the sum of the full load current rating of the largest motor in the group plus the sum of the full load current ratings of all the other motors in the group that may be in operation at the same time; and
> 	<span>&emsp;</span>b) a horsepower rating not less than that of the largest motor in the group if a motor-circuit switch is used.
> 3) A disconnecting means for a motor, motor starter, or controller shall comply with Subrule 1), except that 
> 	<span>&emsp;</span>a) an isolating switch or a general-use switch used as an isolating switch, if lockable in the open position, marked as required by [[CEC s.26#26-100|Rule 26-100]] 2), and having a current rating not less than 115% of the full load current rating of the motor it serves, shall be permitted to serve as the disconnecting means for a motor or motor starter 
> 		<span>&emsp;</span><span>&emsp;</span>i) rated at more than $100\ \mathrm{hp}$ if for three-phase operation; or
> 		<span>&emsp;</span><span>&emsp;</span>ii) rated at more than $50\ \mathrm{hp}$ if for other than three-phase operation;
> 	<span>&emsp;</span>b) a manually operated across-the-line type of motor starter marked “Suitable for Motor Disconnect” shall be permitted to serve as both starter and disconnecting means for 
> 		<span>&emsp;</span><span>&emsp;</span>i) a single motor, provided that it has a horsepower rating not less than the single motor it serves;
> 		<span>&emsp;</span><span>&emsp;</span>ii) a group of motors, provided that it has a horsepower rating not less than the largest motor in the group and a current rating not less than 115% of the full load current of the largest motor in the group plus the sum of the full load currents of all the other motors in the group that may be in operation at the same time; or
> 		<span>&emsp;</span><span>&emsp;</span>iii) a motor or group of motors contained in equipment such as an air-conditioning, refrigeration, or heating unit, provided that 
> 			<span>&emsp;</span><span>&emsp;</span><span>&emsp;</span>A) the equipment does not contain overcurrent protection; and
> 			<span>&emsp;</span><span>&emsp;</span><span>&emsp;</span>B) the starter is rated in accordance with Item i) for a single motor or Item ii) for a group of motors;
> 	<span>&emsp;</span>c) an attachment plug shall be permitted to serve as a disconnecting means for a portable motor and its starting and control equipment, provided that 
> 		<span>&emsp;</span><span>&emsp;</span>i) the attachment plug and receptacle have a current rating not less than the ampacity of the minimum size conductors permitted for the motor branch circuit or tap in which they are connected and are used only as an isolating means and not to interrupt current; or
> 		<span>&emsp;</span><span>&emsp;</span>ii) the attachment plug and receptacle are used as permitted by [[CEC s.28#28-500 Control required|Rule 28-500]] 3);
> 	<span>&emsp;</span>d) the draw-out feature of a high-voltage starter or controller of the draw-out type shall be permitted to serve as the disconnecting means for the motor or controller, provided that it is used only as an isolating means and is not used to interrupt current;
> 	<span>&emsp;</span>e) a manually operated general-use ac switch complying with the requirements of [[CEC s.14#14-510 Use and rating of manually operated general-use ac switches|Rule 14-510]] that has a current rating not less than 125% of the full load current of the motor and that need not be horsepower rated shall be permitted to be used as a disconnecting means for a single-phase motor; and
> 	<span>&emsp;</span>f) a fused or unfused motor-circuit switch shall be permitted to be used as a disconnecting means for a group of motors served from a single circuit and need not have a rating greater than that necessary to accommodate the proper rating of fuse required for the fused switch, provided that it has 
> 		<span>&emsp;</span><span>&emsp;</span>i) a horsepower rating not less than that of the largest motor in the group; and
> 		<span>&emsp;</span><span>&emsp;</span>ii) a current rating not less than 115% of the full load current of the largest motor in the group plus the sum of the full load currents of all the other motors in the group that may be in operation at the same time.
> 4) The disconnecting means shall not be of a type that is electrically operated either automatically or by remote control.
> 5) An enclosure that contains the disconnecting means for an air-conditioning, refrigeration, or heating unit and that is located outdoors shall be suitable for the environment, and where conduit is used as part of the wiring to the disconnecting means located in the enclosure, the conduit shall be drained and sealed in accordance with [[CEC s.22|Rule 22-302]].
## 28-604 Location of disconnecting means
> 1) The motor branch circuit disconnecting means described in Rule [[CEC s.28#28-602 Types and ratings of disconnecting means|28-602]] a) to d) shall
> 	<span>&emsp;</span>a) be located at the distribution centre from where the motor branch circuit originates; and
> 	<span>&emsp;</span>b) where intended to serve as a single disconnecting means for a motor branch circuit, motor, and controller or starter, also be
> 	<span>&emsp;</span><span>&emsp;</span>i) located in accordance with subrule 3); or
> 	<span>&emsp;</span><span>&emsp;</span>ii) capable of being locked in the open position by a lock-off device and clearly labelled to describe the load or loads connected.
> 2) The motor branch circuit disconnecting means described in Rule [[CEC s.28#28-602 Types and ratings of disconnecting means|28-602]] 1) f) shall be located in accordance with Subrule 3).
> 3) Except as required in Subrule 5), the motor and motor starter or controller disconnecting means shall be located
> <span>&emsp;</span>a) within sight of and within $9\ \pu{ m}$ of the motor and the machinery driven by it; and
> <span>&emsp;</span>b) within sight of and within $9\ \pu{ m}$ of the motor starter or controller.
> 4) Notwithstanding Subrule 3), where a motor or group of motors is fed from a single branch circuit in which the branch circuit disconnecting means is not capable of being acceptably locked in the open position and where the motor disconnecting means is a manually operable across-the-line type of motor starter, the motor disconnecting means shall be permitted to be located beyond the limits defined in Subrule 3), provided that,
> <span>&emsp;</span>a) it is capable of safely making and interrupting the locked rotor current of the connected load;
> <span>&emsp;</span>b) it is capable of being locked in the open position; and
> <span>&emsp;</span>c) it can be demonstrated that the location specified in Subrule 3) is clearly impracticable.
> 5) The motor disconnecting means for air-conditioning and refrigeration equipment shall be located within sight of and within $3\ \mathrm{m}$ of the equipment.
> 6) The disconnecting means shall be readily accessible or have the means for operating them readily accessible.
> 7) Motor-driven machinery of a movable or portable type for industrial use shall have a motor-circuit switch or circuit breaker mounted on the machine and accessible to the operator.