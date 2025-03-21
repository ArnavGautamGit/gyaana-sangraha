---
{"dg-publish":true,"permalink":"/Solar Cell Design - Efficiency/","tags":["CompSci","Physics"]}
---

# Index/Contents
[[Solar Cell Design - Efficiency#What is Efficiency in a Solar Cell?\|#What is Efficiency in a Solar Cell?]]
[[Solar Cell Design - Efficiency#Effect of material chosen on Efficiency\|#Effect of material chosen on Efficiency]]
[[Solar Cell Design - Efficiency#Footnotes\|#Footnotes]]

-----
# What is Efficiency in a Solar Cell?
Efficiency is the effort done for unit result i.e., how much effort we had to put in to start seeing the results.
In terms of Photovoltaics, Efficiency is the percentage of useful energy the Solar Panel outputs after taking certain energy from the Sun's photons as an input.

---
# Effect of material chosen on Efficiency
A Solar Cell (although theoretically) can be made of any element but by that logic a gun can be made out of paper. In both cases, we know that it is not practical.
Hence, to see which elements are best suited for Solar Cells lets examine some elements and compounds used in Photovoltaics.

## Silicon (Si) and its types
As we have seen in [[Solar Cell Design - Elements\|Solar Cell Design - Elements]], the materials chosen to build the cell affect the cell immensely.
We know that the Solar Panels are made of Silicon Wafers - which are smaller thin chunks of Silicon taken from the same [[Solar Cell Design - Efficiency#^1\|ingot]] of Silica & are often shaped as circular disks.

Silica can be shaped into three main types of Silicon:
1. ***Crystalline Silicon*** ---> Also called as ***c-Si***
2. ***Amorphous Silicon*** ---> Also called as ***a-Si***
3. ***Microcrystlline Silicon***

Although Crystalline Silicon (by virtue of being crystalline) has a regular, recurring crystal lattice structure, it means it is better conductor of electricity and is inherently better but amorphous Silicon has its advantages.

### Advantages of Amorphous Silicon
1. It has a higher Absorbtion Coefficient. Which leads to 2 advantages:
	1. It can allow for thinner Solar Cells saving weight, material and cost.
	2. We learnt in [[Solar Cell Design - Elements\|Solar Cell Design - Elements]] that Absorbtion Length is inversely proportional to the Absorbtion Coefficient i.e., Cells made of a-Si are 100x thinner.
2. Due to the Silicon being Amorphous, it can absorb longer wavelength photons as well i.e., it can absorb more number of electrons since it can capture late infrared photons as well.

## Cadmium-Telluride (CdTe) & its properties
- In certain situations, these are considered much more efficient than Si since it is a direct band gap semiconductor. They have a high Absorbtion Coefficient i.e., they can be made very thin.
- CdTe also has a higher Band Gap Energy than Si (1.5 eV instead of 1.1 eV) which means that will absorb less number of photons since lesser energy photons cannot participate in the Photovoltaic Effect. This still makes it ideal for single-junction cells.
- Efficient but total power produced is lesser than Si since 20% of 100 > 25% of 50.
- CdTe crystals also have a high bond energy i.e., it does not react with atmospheric gasses, has higher radiation resistant.
- This makes CdTe great for Space Applications in Satellites.
- CdTe Crystals create smaller *Grain Size* {see [[Solar Cell Design - Efficiency#^2\|#^2]]} which means higher exposed surface area for photon absorbtion.
- CdTe's grain boundaries are electrically inactive i.e., they cannot be ionised i.e., ***==there is no need of [[Solar Cell Design - Energy Loss#^2\|Passivation]]==***. 

---
# Thin Film vs Bulk Solar Cell
In theory, Thin Film Cells sound greatly efficient due to the reduction in Recombination Losses (due to smaller base & smaller overall cell), increase in Light Generated Current (i.e., $\large I_{SC}$) and the high absorbtion coefficient (which allows us to build thin film cells in the first place).

Practically however, It is very well known and recognised that bulk cells are more efficient. 

$$\Large \eta = \dfrac{V_{OC}\cdot I_{SC}\cdot FF}{P_{in}}$$
in the given formula, we already have an increase in the $\large I_{SC}$ which means that to properly increase Efficiency, we need to increase $\large V_{OC}$:
$$\Large V_{OC}= \frac{KT}{q}ln[\dfrac{J_L}{J_o} + 1]$$
Here, we cannot increase temperature, since $\large V_{OC}$ decreases on increase of temperature 
{please see [[Solar Cell Design - Energy Loss#What is the effect of Temperature on the output of the Solar Cell?\|Solar Cell Design - Energy Loss#What is the effect of Temperature on the output of the Solar Cell?]]}

To increase $\large V_{OC}$ : 
1. Increase Light-Generated Current Density $\large J_L = {I_{SC}}/{Area}$
2. Decrease Dark-Saturation Current Density $\large J_O = {I_{O}}/{Area}$

$$\Large J_O = (J_O)_{emitter} + (J_O)_{base}$$
$$\Large (J_O)_{base} = \dfrac{q \cdot (n_i)^2 \cdot D_P}{N_A \cdot L_N} \cdot \dfrac{{\large\dfrac{S_B \cdot L_N}{D_N}+tanh(W_b/L_N)}}{{\large1+\dfrac{S_B \cdot L_N}{D_N}+tanh(W_b/L_N)}}$$
where,
$\large D_N =$ Diffusion Coefficient of Electrons
$\large D_P =$ Diffusion Coefficient of Holes
$\large S_B =$ Siurface Recombination on Back Side


---
Next Chapter --->[[Solar Cell Design - Summary\|Solar Cell Design - Summary]]
# Footnotes
1. ***Ingot***: High Purity monocrystalline or multicrystalline solid Silicon formed by melting [[Electronic Grade Silicon (EGS)\|Electronic Grade Si]] followed by a controlled solidification.
{ #1}

2. ***Grain Size***: Each crystalline material is made of crystals and multiple such crystals together form the crystal lattice. Hence, by extension we can see how Crystal Lattices can combine to form larger structures like Grains. Even in Photovoltaics, these grains of any material (for example: Silicon or CdTe) form the emitter and base of cells just how grains of sand make up a desert. Whenever any material is layered on top of a surface, it is (on a microscopic level) made of grains.
{ #2}

3. 

