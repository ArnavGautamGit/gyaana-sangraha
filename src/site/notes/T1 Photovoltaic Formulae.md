---
{"dg-publish":true,"permalink":"/T1 Photovoltaic Formulae/","tags":["CompSci","Physics"]}
---


### Formulae from [[Energy Issues & Solutions\|Energy Issues & Solutions]]

$$\Large Energy \ Output = \dfrac{System \ size \times Insolation}{AM1.5G}$$
where,
$\large AM1.5G$ is always given,
$\large Insolation$ is always in $\large KWh/m^2$

$$\Large Land \ Requirement = \dfrac{Energy \ Output}{Insolation \times Efficiency}$$
where,
If $\large Energy \ Output$ is in KWh/year, $\large Land \ Requirement$ is in $\large km^2$ area

$$\Large Energy \ of \ photon = \dfrac{1240}{\lambda(nm)}$$
$$\Large Wavelength \ (\lambda \ in \ nm) = \dfrac{1240}{Energy \ of \ photon}$$
$$\Large Electron \ Energy \ at \ temperature \ T = \dfrac{K_BT}{q} \ eV = K_BT \ Joules$$
### Formulae from PN Junction
$$\Large p_0\times n_0 = (n_i)^2$$
where,
$\Large p_0 =$ positive charge carrier concentration
$\Large n_0 =$ negative charge carrier concentration
$\Large n_i =$ intrinsic carrier concentration
$$\LARGE \sigma = q(n_0\mu_n + p_0\mu_p)$$
$$\Large n_0 = n_i \times e^{(E_f - E_i)/K_BT}$$
$$\Large E_f - E_i = \dfrac{K_BT}{q} \times ln(\dfrac{n_0}{n_i}) \ eV$$
### Other Formulae
$$\Large L_n = \sqrt{D_n \cdot \tau_n}$$
$$\Large D_n = \mu_n \cdot \dfrac{KT}{q}$$
$$\Large L_n = \sqrt{\mu_n\cdot \dfrac{KT}{q}}$$
$$\Large I = I_0 \cdot e^{-\alpha x}$$
$$\Large I=I_0(e^{qV/KT}-1) \ \ \small (for \ PN \ junction)$$
$$\Large I=(I_0(e^{qV/KT}-1) - I_L) \ \ \small (for \ solar \ cell)$$
$$\Large Fill \ Factor \ (FF) = \dfrac{I_{mp}\cdot V_{mp}}{V_{oc}\cdot V_{sc}}$$
$$\Large P_{max} = V_{OC}\cdot I_{SC} \cdot FF$$
$$\Large Efficiency \ (\eta) = \dfrac{V_{OC}\cdot I_{SC} \cdot FF}{P_{in}}$$
where $\large P_{in} = 1kW/m^2$ of input power
$$\Large I_{SC}=q\cdot G(L_n + L_p)$$
$$\Large V_{OC} = \dfrac{nKT}{q}\cdot ln(\dfrac{I_L}{I_0}+1) = \dfrac{KT}{q} \cdot ln(\dfrac{(N_A +\Delta n)\Delta n}{(n_i)^2})$$
here, $\large N_A =$ Doping Concentration 
$\large \Delta n =$ excess carrier concentration

# Some Unit Conversions
1. $\large Terrawatt \ (TW) = 10^{12} \ Watts$
2. $\large Terrawatt \ (TW) = 10^{9} \ KiloWatts$
# Footnotes
1. $\large Band \ Gap \ of \ Si = 1.12 \ eV$
2. $\large Band \ Gap \ of \ Ge = 0.67 \ eV$
3. $\large Band \ Gap \ of \ GaAs = 1.42 \ eV$
4. $\large Band \ Gap \ of \ CdTe = 1.56 \ eV$
5. $\large n_i \ for \ Si = 10.5 \times 10^{10} \ per \ cm$

