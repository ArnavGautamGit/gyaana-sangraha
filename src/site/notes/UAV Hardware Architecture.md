---
{"dg-publish":true,"permalink":"/UAV Hardware Architecture/","tags":["Academics","Physics"]}
---


---
# UAV Hardware Architecture
> The Hardware used by UAVs to store information, process and transit information whie controlling the flight of said UAV system bu either executing remotely provided commands or by providing a flight plan (for a [[Fully-Autonomous UAV\|Fully-Autonomous UAV]]). 

Hardware Architecture in UAVs depends on the fact whether a particular usecase requires a singular UAS or a multi-UAS?

### Common Hardware
Some kind of a [[Microcontroller\|Microcontroller]] or [[Microprocessor\|Microprocessor]] are often used for controlling the aircraft, transmission and running [[Process Concept\|processes]]. There is a specific part taughht by Janardhan Sir in class which discusses the feasibility of [[Arduino\|Arduino]] in the role. The only constraint being that we should be able to run either [[ArduPilot\|ArduPilot]] and/or [[PX4\|PX4]] on the chip for industry-standard drones. Weaker drones meant for recreational flight may use [[OpenFlight\|OpenFlight]] or similar software which does not support [[Autopilot\|Autopilot]] functionality.

[[Microcontroller\|Microcontrollers]] are cheaper, more widely used but at the same time, they are slightly limited and less customisable. Military Applications may prefer [[Microprocessor\|Microprocessors]] for this reason.
Microcontrollers have a processor with all the sensors such as accelrometer, gyroscope and other receivers like Wi-Fi and Bluetooth pre-attached which makes them rigid and completely non-customisable unless we remove just their processor and connect the sensors & receivers we want (which is basically a [[Microprocessor\|Microprocessor]]).

Apart from a processing unit, we often also need a range of sensors from Camera & [[LiDAR\|LiDAR]] to GPS & [[Inertial Measurement Units (IMUs)\|IMUs]]. Including [[Accelerometer\|Accelerometer]], [[Gyroscope\|Gyroscope]], [[Rate Gyroscope\|Rate Gyroscope]] among others.
A more extensive list of sensors cannot be made unless we actually know the function of the said drone. This was discussed in the last chapter: [[Applications of UAS\|Applications of UAS]].

We also require specific motors, antennae, transmitters, receivers and other peripherals.

### Single UAS System
For a Single UAS setup, the UAS uses either [[Microcontroller\|Microcontrollers]] or [[Microprocessor\|Microprocessors]]  similar to but lower power variants of the [[Intel 8085 Microprocessor\|Intel 8085 Microprocessor]] such as the ones compatible with ArduPilot and PX4.


Apart from microcontrollers, there are specific motors, antennae, transmitters, receivers and other peripherals.

### Multi-UAS Setup
Multi-UAS systems have multiple UAS acting as a singular unit. This is often used for patrolling or Drone Shows. 
Since there are multiple UAVs, Hardware Architecture is generally utilised is of two types:
1. Centralised Control (controlled via a [[Ground Control System\|Ground Control System]])
2. Decentralised Control (UAVs communicate among each other)
3. Distributed Control (even the data is distributed)

| ***METRIC OF COMPARISON***                                     | ***CENTRALISED CONTROL***                                           | ***DECENTRALISED CONTROL***                                          | ***DISTRIBUTED CONTROL***                                                  |
| -------------------------------------------------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Basic Definition                                               | UAS are controlled from one control system                          | UAS maintain distance with each other and follow a leading one.      | All UAS have their respective flight paths distributed among them          |
| [[UAV Communication Architecture\|Communication Architecture]] | All UAS communicate to the same [[Ground Control System\|GCS]]. | UAS communicate with one another                                     | UAS only communicate among one another only if they need to maintain space |
| Latency & Response                                             | Higher Latency and Slower Response                                  | Lower Latency and Faster Response                                    | Lower Latency than Centralised, not as low as Decentralised                |
| Management & Implementation                                    | Convenient to manage, well-known implementation                     | More Difficult to implement than centralised control                 | Hybrid Approach of the other two. Difficulty unknown.                      |
| Is there a single point of failure?                            | Single Point of Failure but lower chance of UAS crash               | No single point of failure but higher chances of a few UAVs crashing | No single point of failure, technology too young to estimate crashes.      |


---
# Footnotes