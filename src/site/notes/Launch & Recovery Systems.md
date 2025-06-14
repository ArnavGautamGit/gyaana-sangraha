---
{"dg-publish":true,"permalink":"/Launch & Recovery Systems/","tags":["Academics","Physics","Aviation"]}
---


---
# Launch & Recovery Systems
> Launch (Deployment) & Recovery (Return) of Aircrafts & Drones use the same principles of Physics. The Launchers for Drones can be considered analogous to the ones used for Aircrafts on Aircraft Carriers. 

For Drones, it is the minimum requirement before commencing the mission.
Although most [[Fixed-Wing UAVs\|Fixed-Wing UAVs]] tend to use conventional runways for takeoff & landing and most of the [[Multi-Rotor UAVs\|Multi-Rotor UAVs]] around the world use [[Vertical Takeoff & Landing (VTOL)\|Vertical Takeoff & Landing (VTOL)]] for the most accurate results, smaller Fixed-Wing UAVs or other UAS with unique configurations must have a L&R system.

Other UAVs that are from micro to small sizes, that cannot have a runway access, are to be studied here.

## Theory behind Launch Design
This is the basic theory behind Launch Design for any Aircraft & it is also valid for a UAV.
The Force needed to launch could be provided by any source of acceleration, be it external or the Propulsion System of the Aircraft itself.

To accelerate a particular Aircraft or UAS from velocity $\large V_1$ to Velocity $\large V_2$, we need the following formula:
$$\Large (V_2)^2 - (V_1)^2 = 2ax$$
In this formula, $\large a=$ linear acceleration and $\large x =$ distance covered.

Thus,
For a launching system $\large V_1 = 0$ since the UAV starts from rest and $\large x=$ Length of the Launcher.
We introduce the equation required for launch:
$$\Large (V_2)^2 = 2aL$$
where $\large L=$ Length of the Launcher i.e., Distance over which the linear acceleration ($\large a$) is applied regardless of if the acceleration is applied from an external launching mechanism or just having the aircraft going down a runway at full speed.

Force Required to provide this launch can be found using [[Newton's Second Law of Motion\|Newton's Second Law of Motion]],
$$\Large F_L - F_f - Wcos\theta = ma$$
here, Force of Launch ($\large F_L$) must be greater than the Force of Friction ($\large F_f$) to move.
Force of Friction can be derived from: $\large F_f = \mu cos\theta$
$\large W$ is the weight of the aircraft or drone derived from the formula $\large W = mg$.

Substituting the value of Force of Friction in the above equation:
$$\Large F_L - \mu Wcos\theta - Wcos\theta = ma$$
$$\Large F_L = Wcos\theta (1+\mu) + ma$$

Note that launching with an angle of 180 degrees (parallel to the ground) like Aircraft Carriers is going to make the launcher require either more thrust or more length (bigger apparatus). To reduce the footprint of any Launching Apparatus, it is beneficial to keep the Aircraft speed at the end of the launcher/runway to be 10-30% of [[Stall Speed\|Stall Speed]] and launching angle to be around 45 degrees.

## Rail Launcher
Using a part of the Aircraft or UAV to be fixed/attached into the launcher rails (which generally comprise of Two Rails and mobility wheels) on which the Aircraft is accelerated until it can reach speeds which can sustain flight. Using the equations given above.

These kinds of Launchers are used on Aircraft Carriers & also for UAVs like [[AAI RQ-7 Shadow 200\|AAI RQ-7 Shadow 200]]. The only difference being that American Carriers use them parralel to the ground since the thrust of the launcher on the ground combined with the thrust from those massive engines are able to do the trick. UAVs barely have that kind of thrust.
![RQ-7 Shadow 200 Launcher.png](/img/user/Vaulted%20Images/RQ-7%20Shadow%20200%20Launcher.png)

For such mobile angled launchers, it is imperative that the Pneumatic Pistons, Rubber Bungees or any other form of providing launching force should be reusable and either be fixed to the ground or have a reacting mass. Often times, Rockets are also used to provide the sudden acceleration needed to propel the UAVs for launch.

## Other Launch Methods
Smaller UAVs may be launched using Hand Launch Technique where the initial throw is provided by hand. Similarly, smaller Aircrafts may be Air Launched by a larger aircraft. Imagine a C-130 dropping 10s (if not 100s) of UAVs from above.


## Various Recovery Systems
Those Aircrafts that have enough room and size to land conventionally often have landing gear of some sort whether retractable or fixed. Rotorcrafts (such as Helicopters & [[Multi-Rotor UAVs\|Multi-Rotor UAVs]]) often use [[Vertical Takeoff & Landing (VTOL)\|VTOL]].

On the other hand, Aircrafts that are too small (like [[Fixed-Wing UAVs\|Fixed-Wing UAVs]]) or do not have a free runway are often caught using Hookarms (which adjust to catch/hook the aircraft as it flies by) or by Nets. The Latter is considered cheaper, safer, more full-proof and more foregiving in case of misses.

Many Aircraft or UAVs have the option of skid & belly landings where some ski-like landing gear or fuselage strengthening is required.

Others may opt for a Parachute Recivery or a hybrid of Parachute with Landing Gear so it effectively becomes a good [[Short Takeoff & Landing (STOL)\|Short Takeoff & Landing (STOL)]] Vehicle like the [[Mig-21 Bison\|Mig-21 Bison]].
The only thing to keep in mind is the equation of [[Stall Speed\|Stall Speed]] where the Maximum Drag Coefficient $\large C_{Lmax}$ is swapped with the Parachute's Drag Coefficient $\large C_D$.

Aircrafts heavier than 200 kg generally avoid all of these and go for a runway with landing gear. Since if an aircraft is that heavy, it is obvious the wingspan would have to keep up and it won't hurt to put some landing gear on said aircraft and add another 5-10 kg (which is 2.5% to 5% of 200 kg). 


---
# Footnotes