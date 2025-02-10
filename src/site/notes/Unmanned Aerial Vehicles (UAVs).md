---
{"dg-publish":true,"permalink":"/Unmanned Aerial Vehicles (UAVs)/","tags":["Academics","Physics"]}
---


---
# Unmanned Aerial Vehicles (UAVs)
> Refers to remotely piloted or completely autonomous flying vehicles which may emulate Helicopters or Planes in some aspects of their design. 
> Also called "*Unmanned Aircraft Systems*" or "*Remotely Piloted Vehicles*" in some countries.

Unlike popular belief & also unlike the reasoning of Janardhan sir when teaching [[Unmanned Aerial Vehicles (Subject)\|the Subject]], the word unmanned does not always mean autonomous here.
Most of the time, there are humans that are giving the control inputs. Its called "unmanned" because there is no pilot physically sitting in any cockpit inside the vehicle which is why the term  is also popular.

UAVs are considered revolutionary because wars can take place without risking as many human lives with equipmet which can be manufactured for much cheaper. They have now an increased role outside of just Patrolling and Scouting, UAS are now a popular choice for Air-to-Ground Strikes, [[Reconnaissance\|Reconnaissance]] and [[Intelligence (Espionage)\|Intelligence (Espionage)]].

### Classification of UAVs
UAVs can be classified on the basis of many criteria. There are a few Criterions which are considered as standard Classification points. Note that no source classifies UAVs/UAS on the basis of all the criteria simultaneously. Most sources choose one or two points of classification.
- Usecase (Civilian or Military)
	- Civilian UAVs are used for Surveys & Deliveries
	- Military UAVs are used for Scouting & Bombing
- Flight Design (Fixed Wing or Multi-Rotor)
- Propulsion (Electric or Fossil Fuel)
- Weight (Nano to Large)

In India, the Laws laid out by Directorate General of Civil Aviation (DGCA) classifies UAS on the basis of Flight Design and on the basis of Weight.

### Design Process for a UAV
Design of a UAV or Drone is dependent upon the usecase & problem it is aimed at solving.
Some Design Criteria may change depending upon whether the UAV is meant for Civil or Military use but generally, there are mainly 5 criteria: 
1. Cost of Building & Upkeep
2. Performance (Efficiency, Speed)
3. Reliability (ease of maintainance)
4. Stealth (Flight Noise, [[RADAR Cross-Section (RCS)\|RCS]]) 
5. Optimisation (weight reduction, balancing)

Other Criteria such as: Flight Characteristics, Crash Survivability, UAV Weight, Design Period & Scalability to Mass Manufacturing all play a role but may or may not be the main criteria in every scenario to establish a design baseline.

Once a design baseline is drafted, Feasibility Analysis is performed to check if the design is feasibile after which it is approved after any necessary changes. After approval & finalisation of the design, Gantt Charts and other Project Management Tools are used to keep the Projects on the Deadline and review progress.

The Design Process is lead by a Chief Designer, who heads various groups from *Structural Engineering*, *Aerodynamics*, *Flight Dynamics*, *Propulsion Engineering*, *Autopilot*, *Ground Station* and all the way to *Launch & Recovery* Expertise Groups. If the groups are divided on the basis of components instead of expertise, then the groups need to be structured individually for wing design, landing gear design team etc. Generally both groupings are applied together in case of big projects.

![UAV Life Cycle.png](/img/user/Vaulted%20Images/UAV%20Life%20Cycle.png)

The Design Pipeline consists of many Reviews at each stage - including Evaluation & Testing Review & Final Design Reviews.

![UAV Design Process.png](/img/user/Vaulted%20Images/UAV%20Design%20Process.png)

The Performance Design of UAVs was developed by Sadraey himself in 2012 - in his book "Aircraft Design: A Systems Engineering Approach" which was developed on the basis of NASA's Technical Report (as claimed by the author). His book on UAV Design ([[Unmanned Aerial Vehicles (UAVs)#^1\|#^1]]) is used as a source for these notes. 
Performance Design is used in Conceptual and Preliminary Design Stages in the Design Pipeline.

![UAV Performance Design.png](/img/user/Vault%20Templates/UAV%20Performance%20Design.png)

The Detailed Design Process involves a series of questions in a flowchart which are answered on the basis of Rigorous Testing in that specific field. Various Subsystems and components are checked throughout the process such as: [[Landing Gear (LG)\|Landing Gear (LG)]], Propulsion system, Wings etc.

![UAV Detailed Design.png](/img/user/Vaulted%20Images/UAV%20Detailed%20Design.png)

### Components of UAVs
There are some basic components such as [[Landing Gear (LG)\|Landing Gear (LG)]], Wings, Fuselage among others. These Basic Components are listed here:
![UAV Basic Components.png](/img/user/Vaulted%20Images/UAV%20Basic%20Components.png)

Many controllers such as [[PID Controller\|PID Controller]] and [[Kalman Filter\|Kalman Filter]] (which has subtypes such as [[Extended Kalman Filter\|Extended Kalman Filter]] among others) are also required for fine-tuning the flight controls.

---
# Footnotes
1. "Unmanned Aircraft Design" by Mohammed Sadraey, 2017 Edition.
{ #1}
