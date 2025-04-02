---
{"dg-publish":true,"permalink":"/UAV Control System Design/","tags":["Academics","Physics"]}
---


---
# UAV Control System Design
> The part of the overall [[UAV Autopilot Design\|UAV Autopilot Design]] that controls the direction where the UAV is facing.

These systems are built with specifics in mind that no matter the weather or wind speed, whether it is [[Headwind\|Headwind]] or it is [[Tailwind\|Tailwind]], the trip must be made as smooth and safe as possible. 

The Algorithm is complicated by the fact that a UAS has 6 degrees of freedom & functionalities of many sensors may overlap or contradict and one has to give preference to one reading or combine results of multiple reading using variables.

### Design Methods
![Control System Design.png](/img/user/Vaulted%20Images/Control%20System%20Design.png)

Combining the outputs from multiple sensors depending upon whether the control laws are linear, non-linear, optimal, adaptive or robust. Generally Non-Linear are considered since real life aircrafts are also non-linear systems.

[[Linearisation\|Linearisation]] is a process of taking a non-linear system and trying to linearise it around certain equilibrium points using [[Taylor Series Expansions\|Taylor Series Expansions]].

---
# Footnotes