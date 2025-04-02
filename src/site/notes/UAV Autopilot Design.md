---
{"dg-publish":true,"permalink":"/UAV Autopilot Design/","tags":["Academics","Physics","Software-Development"]}
---


---
# UAV Autopilot Design
Autopilots in UAVs need to have 3 subsystems done right: Automatic [[UAV Control System Design\|Flight Controls Systems]], [[UAV Guidance System Design\|Guidance System]] & [[UAV Navigation System Design\|Navigation System]] i.e., where the drone wants to go, calculation of the path to get there and control inputs to pick that trajectory.

![Autopilot Subsystems.png](/img/user/Vaulted%20Images/Autopilot%20Subsystems.png)

The Constraints are that the entire system needs to be a Dynamic, [[Real-Time System\|Real-Time System]] capable of updating all the three subsystems in accordance with the variation in predicted and measured trajectories i.e., the Autopilot system must be capable of assessing that it is going in the wrong direction and must be able to smoothly Course-Correct in real-time as it keeps moving towards the destination.

![Autopilot Design Process.png](/img/user/Vaulted%20Images/Autopilot%20Design%20Process.png)

Three major sections of [[UAV Control System Design\|control system]], [[UAV Guidance System Design\|guidance system]], and [[UAV Navigation System Design\|navigation system]] are designed in parallel. At any stage of the design procedure, the output is checked with the design requirements, and a feedback is taken. The process is repeated until the requirements are met.

Major Requirements from any Autopilot system is the required accuracy, stability, structural stiffness, maneuverability, flying quality, reliability, cost and processor.

The [[PID Controller\|PID Controller]] is often used in [[UAV Control System Design\|UAV Control System Design]].
The [[Kalman Filter\|Kalman Filter]] is often used for Linearisation - a system as complex as a UAV with multiple variables can never be linear but Taylor Series Expansions are used to Linearise the equations around certain Equilibrium points. 

---
# Footnotes