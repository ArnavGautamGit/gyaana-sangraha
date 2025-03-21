---
{"dg-publish":true,"permalink":"/Solar Cell Design - Energy Loss/","tags":["CompSci","Physics"]}
---

# Index/Contents
[[Solar Cell Design - Energy Loss#What kind of Energy Losses are possible in a Solar Cell?\|#What kind of Energy Losses are possible in a Solar Cell?]]
[[Solar Cell Design - Energy Loss#What are the Electrical Losses in a Solar Cell?\|#What are the Electrical Losses in a Solar Cell?]]
[[Solar Cell Design - Energy Loss#What is the effect of Temperature on the output of the Solar Cell?\|#What is the effect of Temperature on the output of the Solar Cell?]]
[[Solar Cell Design - Energy Loss#What are the design Principles of a Solar Cell?\|#What are the design Principles of a Solar Cell?]]
[[Solar Cell Design - Energy Loss#How do the Optical Losses change things?\|#How do the Optical Losses change things?]]
[[Solar Cell Design - Energy Loss#Basic Contruction of any Solar Cell\|#Basic Contruction of any Solar Cell]]
[[Solar Cell Design - Energy Loss#Footnotes\|#Footnotes]]

-----
# What kind of Energy Losses are possible in a Solar Cell?
Losses in a Solar Cell are primarily of two kinds:
1. ***Optical Losses*** ---> due to the Optical Properties of the cell.
2. ***Electrical Losses*** ---> due to the Electrical Properties of the cell.
	- [[Solar Cell Design - Energy Loss#Recombination Losses\|#Recombination Losses]] ---> charge carriers of the emitter and base layers recombine.
	- ***Ohmic Losses*** ---> due to Resistance of the material.
		- [[Solar Cell Design - Energy Loss#Series Resistance\|#Series Resistance]] ($\large R_S$) ---> decreases $\large I_{SC} \ and \ FF$
			- ***Emitter Resistance*** ---> Resistance offered by n-type silicon top layer.
			- ***Base Resistance*** ---> Resistance offered by p-type silicon base layer.
		- [[Solar Cell Design - Energy Loss#Shunt Resistance\|#Shunt Resistance]] ($\large R_{Sh}$) ---> decreases $\large V_{OC}$
3. ***Parasitic Resistance*** ---> Sum of all resistances due to all current-carrying components
4. [[Solar Cell Design - Energy Loss#Characteristic Resistance\|#Characteristic Resistance]] ($\large R_{CH}$) ---> Output resistance at maximum power production point. Inverse of the I-V Curve gives Characteristic Resistance.

Note: Recombination & Ohmic Losses are types of Electrical Losses.

---
# What are the Electrical Losses in a Solar Cell?
Electrical Losses are losses that occur due to electrical properties of a solar cell - such as resistance (i.e., Ohmic Losses) or electron-hole recombination (i.e., Recombination Losses). There are more types of losses that can be counted in Electrical Losses of a Solar Cell, but they are beyond the scope of our syllabus.
## Characteristic Resistance
There is a simple formula to calculate the Characteristic Resistance. Characteristic Resistance can also be defined as Parasitic Resistance at maximum power production point.
$$\Large R_{CH} = \dfrac{V_{MP}}{I_{MP}} = \dfrac{V_{OC}}{I_{SC}}$$
## Why haven't we been able to remove these losses?
If we reduce one kind of loss, the other kind increases.

***Example***: If we seek to reduce the Electrical Losses, Reflective Losses will increase instead. Since to reduce the Resistance of the material beyond a point, you would need to change the material entirely! Reflectioon Losses cannot be removed since that will increase Recombination Losses.
## Ideal level to keep the various Resistances for max. power
- Series Resistance must be as close to 0 as possible, It can never be exactly zero, but we should try to make it as close to it as possible.
- Shunt Resistance must be very high, ideally as close to $\Large \infty$ as possible.
- These conditions give the formula for new maximum power (if only series resistance is considered) as:
$$\Large P'_{MP} = V_{MP} \cdot I_{MP} - (I_{MP})^2 \cdot R_S$$
$$\Large \Rightarrow P'_{MP} = P_{MP} \cdot (1- \dfrac{I_{SC}}{V_{OC}}\cdot R_S)$$
$$\Large \Rightarrow P'_{MP} = P_{MP} \cdot (1- \dfrac{R_S}{R_{CH}})$$
$$\Large \Rightarrow P'_{MP} = P_{MP} \cdot (1- r_S)$$
$\large where, \ r_S = Normalised \ series \ resistance = \dfrac{R_S}{R_{CH}}$

$\large Similarly, \ for \ Fill \ Factor \ (FF):$
$$\Large FF' = FF \cdot (1-r_S)$$
Replace $\large r_S$ with $\large \dfrac{1}{r_{Sh}}$ for Shunt Resistance (no Series resistance involved)
## Formulae for Current Produed by a Solar Cell in the present of series, shunt & both resistances

For Series Resistance only, we get:
$$\Large I = I_{SC}-I_0\cdot[e^{\ q(V+IR_S)/nKT \ } - 1] $$
For Shunt Resistance only, we get:
$$\Large I = I_{SC}-I_0\cdot[e^{\ qV/KT \ } - 1] - \dfrac{V}{R_{Sh}}$$
For Both Series and Shunt Resistances are present, we get:
$$\Large I = I_{SC}-I_0\cdot[e^{\ q(V+IR_S)/nKT \ } - 1] - \dfrac{(V+IR_S)}{R_{Sh}}$$
## Series Resistance
Series Resistance has many components.
On a simple circuit we may say that a Solar Cell has only Series and Shunt Resistance but each of them is formed by multiple components.
Series Resistance of a solar cell is formed by:
- the Base Layer (p-type Silicon) 
- the Emitter Layer (n-type Silicon) 
- the top grid (consisting of fingers and busbars). {see [[Solar Cell Design - Energy Loss# Basic Construction of any Solar Cell\|# Basic Construction of any Solar Cell]]}
### The Base Resistance
$$\Large R_b = \dfrac{\rho_b\cdot W_b}{A}$$
$\large where, \ W_b = width \ of \ the \ base \ layer \ and \ \rho_b=the \ resistivity \ of \ the \ base \ layer.$
### The Emitter Resistance
$$\Large R_e=\dfrac{\rho_e \cdot l_2}{W_e \cdot l_1} = \rho_{Sheet} \ \small(approx.)$$
$\large here, \ l_2 = breadth \ of \ the \ emitter \ layer, \ while \ l_1 = length \ of \ the \ layer.$
## Shunt Resistance
Sir deifinitely mentioned how Shunt Resistance is created but it is not mentioned in the slides. And there is no mention of how to reduce it, so I will go with using Formulae to deduce that.


## Recombination Losses
Recombination of Charge Carriers happens due to not being able to get the separated charge carriers to the contact points {see [[Solar Cell Design - Energy Loss#^1\|#^1]]} in the Solar Cell fast enough i.e., the charge carriers are not diffusing far enough i.e., ***==Diffusion Length needs to be much larger==***. 
These losses are dealt with the ***==Passivation Layer formed by optimized doping==***. {see [[Solar Cell Design - Energy Loss#^2\|#^2]]}
The effect of a larger diffusion layer can be amplified using a ***==smaller cell volume==***.

Recombination Losses reduce current collection (by extension, $\large I_{SC}$) and Forward Bias Current (by extension $\large V_{OC}$)

---
# What is the effect of Temperature on the output of the Solar Cell?
Without going into derivations, for Silicon-based Solar Cells...
$$\Large New \ I_{SC} = +0.0006  \ per \ \degree C  \ increase\ in \ temperature$$
$$\Large New \ FF = -0.0015  \ per \ \ \degree C  \ increase\ in \ temperature$$
$$\Large New \ P_{Max} = +0.0045  \ per \ \ \degree C  \ increase\ in \ temperature$$

---
# What are the design Principles of a Solar Cell?
Armed with all the knowledge we have from before we can say that the following 4 parameters will make a perfect Solar Cell:
1. Maximum Possible Efficiency. 
	- Maximum Possible Absorption of Light
	- Separation of Light Generated Charge Carriers
	- Minimise $\large I_0$ but maximise $\large I_{SC}$
	- Transport of Separated Charge Carriers to Load with least Ohmic Losses possible.
1. Maximum Possible $\large V_{OC}$.
2. Appropriate $\large I_{SC}$ according to the $\large V_{OC}$ level.
3. Lowest Cummulative Energy Losses possible.
## Formulae for Calculating these:
$$\Large \ Efficiency \ (\eta) = \dfrac{V_{OC}\cdot I_{SC}\cdot FF}{P_{in}}$$
$$\Large Open-Circuit \ Voltage \ (V_{OC}) = \dfrac{nKT}{q}ln(\dfrac{I_L}{I_0} +1)$$
$$\Large Short-Circuit \ Current \ (I_{SC}) = I_0\cdot[e^{{qV}/{KT}}-1]-I_L$$

---
# How do the Optical Losses change things?
Until now, we did not assume the Optical Losses posed a challenged. We assumed that Optical Losses do not exist to avoid making our calculations a bit too extreme.

Optical Losses are of the following kind:
1. Reflection ---> Photon is reflected off due to the material properties of Silicon.
2. Frequency of Light ---> Light's Frequency is proportional to its Photon's Energy which must be equal to the Band Gap energy of the material used (Silicon), but light has all colours from Red to Violet and even Infrared & Ultraviolet! Which do we focus on?

Let's see each of them in greater detail.
## Reflection Loss
We need to protect the Solar Cell from the elements & since it is a fragile system, we cannot use clear/transparent plastic since it turns yellow (and ruin the cell's optical properties further) and that it can melt or burn in high temperatures!

Better idea is to just use glass.
But any interface has a very different Refractive Index and all calculations up till now were done for both the Sunlight and the Cell being in the same medium (air) but they aren't.

There are a few ways to reduce the Reflection Loss:
1. ARCs (Anti-Reflective Coatings)
2. Regular Pattern Texturing
3. Greenhouse Trapping of Light
### Method 1: Anti-Reflection Coatings (ARCs)
Coatings on Reading glasses and wearable glass is made to reflect certain frequencies of light, we are going to reverse the direction, design coatings that trap most of the frequencies.
==***Intentional Destructive Interference of Sun's Coherent rays of light forces maximum light on the solar cell***==. We also need to be mindful of the thickness of the film.
$$\Large Minimum \ Thickness = d_1 = \dfrac{\lambda_0}{4 \cdot \mu_{film}}$$
$$\Large n_1 = \mu_{film} = \sqrt{\mu_{air} \cdot \mu_{glass}} = \large 1.224$$
Why $\Large\mu_{glass}$ and not $\Large \mu_{silicon}$? The layer is added to the air-glass interface.
***==Due to unique wavelengths, we cannot use just 1 layer, but multiple layers drive up costs.==***
### Method 2: Regular Pattern Texturing
Use Total Internal Reflection to texture the panel's surface to trap a wide range of $\lambda$ so that it is more versatile than ARCs.
Also note that there are two texture schemes that are very popular in the industry:
1. Random Pyramid ---> Random Pyramid Shapes Structure popping above from the surface.
2. Inverted Pyramid ---> Pyramids etched down into the silicon surface instead of pointing up.
### Method 3: Greenhouse Trapping of Light
This method utilizes the ***==Lambertian Rear Reflectors==***.
At the bottom of Solar Cell where the light reflects off of, we use specific kind of reflectors which reflect the light in random direction, increasing the possibility of trapping the light in the base of the Solar Cell.
Let's see using a Diagram.
![Lambertian Rear Reflectors.png](/img/user/Vaulted%20Images/Lambertian%20Rear%20Reflectors.png)
These were very effective since they increased the path length of light by 50 times!

---
# Basic Contruction of any Solar Cell
The Solar Cell has a glass covering to protect it, underneat it therer is a bluish/blackish colour (Silicon) that is the real photovoltaic surface the glass protects.
The horizontal metallic lines are the fingers and the thicker vertical lines are the busbars. Both of these act as contact points in a Solar Cell.
All contacts in the Solar Cell is made of metallic substances like Silver, Copper and Aluminium that are great conductors. (Silver is rare due to cost).

Both Fingers and Busbars need to be optimally spaced since less spacing means more materials i.e., higher series resistance. Less fingers and busbars would create higher recombination losses.

Power Generated between any pair of fingers:
$$\Large P_{gen} = J_{MP} \cdot b \cdot \dfrac{S}{2} \cdot V_{MP}$$
% of emitter power loss for a finger-pair:
$$\Large \% P_{loss} = \dfrac{P_{loss}}{P_{gen}} = \dfrac{\rho \cdot S^2 \cdot J_{MP}}{12 \cdot V_{MP}}$$
Power loss in a finger:
$$\Large P_{loss} = \dfrac{1}{3} \cdot b^3 \cdot (J_{MP})^2 \cdot S^2 \cdot \dfrac{\rho_f}{W_f \cdot d_f}$$
where,
$\large b = length \ of \ finger$
$\large J_{MP} = Maximum \ Current \ Density$
$\large S = Finger \ Spacing$
$\Large \rho_f = \large Resistivity \ of \ Finger$
$\large W_f = Width \ of \ Finger$
$\large d_f = Depth \ of \ Finger$

---

Next Chapter --->[[Solar Cell Design - Efficiency\|Solar Cell Design - Efficiency]]
# Footnotes
1. ***Contact Points*** of a solar cell could be understood as the positive and negative terminals of a battery
{ #1}

2. ***Passivation*** (also called "Surface Passivation") as the name suggests refers to a process of converting something active to passive. 
   In Photovoltaics, surface passivation is the process of reducing the number of dangling Silicon bonds which can get ionised and aims to decrease recombination on the top layer of the Solar Cell with a passivating layer of an oxide of the same element (such as $SiO_2$ for Silicon-based cells) i.e.,  ***==It is the process to destroy (or "passivate") the ability of charged particles to recombine by reducing the number of ionised particles at the top layer by applying a coating of an oxide of the element used to make the Solar Cell==***.
{ #2}


