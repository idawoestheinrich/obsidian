---
tags: 
aliases:
  - Geometric capture efficiency
  - capture efficiency
---
# Geometrical Capture Efficiency 

Similar to the [[Wavelength-shifting molecules|WLS]] fibres, the geometrical capture efficiency of a [[WOM]] tube, $\epsilon_\text{TIR}$, describes the probability of secondary photons being captured by [[Total internal reflection|TIR]]. The criteria for [[Total internal reflection|TIR]] for isotropically emitted photons within [[PMMA]] surrounded by air is that the angle to the normal $\theta_i$ needs to be bigger than:

$$
\theta_c = \arcsin\left(\frac{n_\text{air}}{n_\text{PMMA}}\right) \approx 42.16\degree.
$$

The geometrical capture efficiency of a tube can be approximated with the geometrical capture efficiency of a flat plate with the assumption that the photon is emitted at or very close to the outer or inner surface, as illustrated in the figure below [[bastianquerner]],[[2022WOM]]. With a scintillation photon represented in blue being absorbed and re-emitted in the [[Wavelength-shifting molecules|WLS]] layer and captured by [[Total internal reflection|TIR]] (green) or lost (red). The escape cone with the critical angle for the re-emitted photon $\theta_c$ is represented by the grey dashed lines.

![Schematic illustration of the geometric capture efficiency and the reflection angle relations in a tube.](THEO_Escape_Cone.png)  
*Figure 2: (a) Schematic illustration of the geometric capture efficiency $\epsilon_\text{TIR}$ of a [[WOM]] tube. The scintillation photon (blue) is absorbed and re-emitted in the material and either captured by [[Total internal reflection|TIR]] (green) or lost (red). Non-captured light is illustrated in the form of light cones with an opening angle of $2\theta_c$. Taken from [[bastianquerner]], [[2022WOM]]. (b) Schematic illustration of the [[Reflection]] angle relations in a tube for the inner and outer surface ($\beta \leq \alpha$). Taken from [[2014Hebecker]].*

The theoretical capture efficiency of a flat surface is then calculated by subtracting the normalized volumes of the two escape cones with an opening angle $\omega = 2\theta_c$ from one:

$$
\epsilon^\text{geo}_\text{captured} =  1 - 2\sin^2\left(\frac{\theta_c}{2}\right) = 74.1\%.
$$

Due to the coating on the in- and outside of the [[WOM]], a few more geometric considerations must be made. Due to the curvature of the tube shown in the following figure, the capture efficiency depends on the origin of the photon. The [[Reflection]] on the inner wall will always occur at an identical or steeper angle than the one on the outer wall ($\alpha \geq \beta$) [[2014Hebecker]].

![Schematic illustration of the reflection angle relations in a tube for the inner and outer surface.](THEO_WOM_inner_outer_reflection.png)  
*Figure 3: Schematic illustration of the [[Reflection]] angle relations in a tube for the inner and outer surface ($\beta \leq \alpha$). Taken from [[2014Hebecker]].*

Since a steeper angle has an equal or higher probability for [[Reflection]], there are two different cases:  
The most probable case is that the photon comes from outside the [[WOM]] and is absorbed on the outer [[Wavelength-shifting molecules|WLS]] layer. The secondary photon is then always captured if $\theta_i > \theta_c$ whereby $\theta_i$ is the angle relative to the normal at the point of impact.  
If the photon is absorbed on the inner [[Wavelength-shifting molecules|WLS]] layer, the capture efficiency $\epsilon^\text{geo}_\text{captured}$ decreases because the requirement now is $\theta_i > \theta_c + (\alpha - \beta)$.  
If the absorption efficiency of the [[Wavelength-shifting molecules|WLS]] layers is $\epsilon_\text{absorption} = 1$, this is only the case if the incoming photon comes from the [[Organic Scintillator|scintillator]] on the inside of the [[PMMA]] vessel.