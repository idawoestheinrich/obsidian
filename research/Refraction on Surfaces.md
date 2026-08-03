### Refraction on Surfaces
Light is refracted during the transition from one material with an index of refraction $n_1$ to another with a different index of refraction $n_2$. Depending on the difference between the indices of refraction, the light will be refracted towards or away from the normal. Refraction follows Snell's law, which states that the ratio of the sines of the [[Angle of incidence]] $\theta_i$ and the angle of refraction $\theta_t$ is equal to the ratio of the refractive indices of the two media:

$$
\frac{\sin{\theta_i}}{\sin{\theta_t}}=\frac{n_2}{n_1}.
$$

The refraction on a surface can be seen in the figure below. For specular [[Reflection]], light is reflected from a flat surface at an angle $\theta_r$ that is equal to the [[Angle of incidence]] $\theta_r = \theta_i$.

If the angle of the outgoing light $\theta_t \ge \frac{\pi}{2}$, the light only enters the second medium as an evanescent wave with rapidly decreasing amplitude. Effectively, all the light has to return to the first medium via [[Reflection]]. This effect is called [[Total internal reflection]]  and is illustrated in the figure below. [[Total internal reflection|TIR]] occurs as soon as the incident angle $\theta_i$ is greater than the critical angle:

$$
 \theta_c = \arcsin\left(\frac{n_2}{n_1}\right).
$$

![Schematic display of light reflection and total internal reflection](THEO_Reflection.png)  
*Figure 1: (a) Schematic display of incident light reflected at a surface $n_1 > n_2$ with $\theta_i < \theta_c$. $\theta_c$ is the critical angle. (b) Schematic display of [[Total internal reflection]] ([[TIR]]) of light on a surface $n_1 > n_2$ with $\theta_i > \theta_c$.*

If light impinges at an angle $\theta_i < \theta_c$, it will partially be reflected and transmitted at the interface.  
The [[Fresnel equations]] describe the probability with which an incident photon is reflected or transmitted at a surface depending on the [[Angle of incidence]] and the refractive indices of the two materials. The [[Reflection]] coefficient $R$ is defined depending on the polarization of the incident light. If the polarity is normal to the plane of incidence ($s$-polarized), the [[Reflection]] coefficient $R_s$ is given by:
$$
R_s = \left| \frac{n_1 \cos\theta_i - n_2 \cos\theta_t}{n_1 \cos\theta_i + n_2 \cos\theta_t} \right|^2
$$
And the [[Reflection]] coefficient $R_p$ for light polarized in the plane of incidence ($p$-polarized) is given by:

$$
R_p = \left| \frac{n_1 \cos\theta_t - n_2 \cos\theta_i}{n_1 \cos\theta_t + n_2 \cos\theta_i} \right|^2.
$$

Since the polarization of the incident light is not particularly relevant for the experiments discussed here, only the mean value $R=\frac{R_s + R_p}{2}$ is considered. The transmission coefficient $T$ is simply the fraction of light that is not reflected ($T = 1 - R$) [[Jackson100964]].

For light being partially transmitted through a plate of [[PMMA]], illustrated in the figure below, the transmission coefficient depending on the [[Angle of incidence]] is shown in the plot. For this plot, the absorption and scattering on impurities in the material are neglected. As expected, the transmission coefficient drops to zero at the critical angle ($\theta_c \approx 42\degree$).
![Schematic illustration of light transmission and reflection in PMMA](THEO_Fresnel1.png)  
*Figure 2: (a) Schematic illustration of light with an [[Angle of incidence]] $\theta_i = 0$ being partially transmitted through a plate of [[PMMA]] with the index of refraction $n_\text{PMMA}\approx 1.50$ [[WU2022130018]] surrounded by air with the index of refraction $n_\text{air} \approx 1$. Taken from [[2021Hebecker]].
![[THEO_Fresnel2.png]]
(b) Plot of the transmission coefficient for the transition between air and [[PMMA]] depending on the [[Angle of incidence]]. For this plot, the absorption and scattering on impurities in the material are neglected.*
If the [[Angle of incidence]] is $\theta_i = 0$, the [[Reflection]] coefficient simplifies to:

$$
R = \left|\frac{n_1 - n_2}{n_1 + n_2}\right|^2.
$$

This leads to a transmittance coefficient of:

$$
T = 1 - R = \frac{4n_1n_2}{(n_1 + n_2)^2}
$$
for the [[Reflection]] on one surface. The total transmittance coefficient for the transmission through a [[PMMA]] plate with $n_\text{PMMA} \approx 1.50$ [[WU2022130018]], surrounded by air with $n_\text{air} \approx 1$, taking into account the [[Reflection]] on the second surface and the infinite internal reflections within the plate, is given by:

$$
T_\text{tot} = \frac{2n_\text{PMMA}}{1 + n_\text{PMMA}^2}. \tag{eq.totalT}
$$

The photon loss resulting from the transmission out of the material reduces the efficiency and energy resolution of the detector. To decrease this effect, scintillators are usually surrounded by an external reflector. Another option is to maximize the inner [[Reflection]], lowering the critical angle $\theta_c$ by choosing an outer material with a very low index of refraction $n_2$, for example, air. With [[Organic Scintillator|plastic scintillators]], internal [[Reflection]] is also facilitated by polishing the surface. A better internal or external [[Reflection]] leads to a longer mean distance traveled by the photon, increasing the attenuation length's influence on detection performance [[kolanoski2016teilchendetektoren]].

### Additional links
[[PMMA]]