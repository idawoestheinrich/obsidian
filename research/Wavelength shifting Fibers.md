---
tags: 
aliases:
  - WLS fibres
rating: /10
---
### Wavelength Shifting Fibres

The light guides and collectors of the prototype \Gls{CheapCal} are \Gls{WLS} fibres that are embedded on both sides of the scintillator plate at uniform distances. The fibres used are model Y-11, produced by the manufacturer Kuraray. Therefore, the functional principle of the \Gls{WLS} fibres will be explained using this example.

The fibres absorb the photons emitted by the scintillator and re-emit photons with a higher wavelength. The fibres have a diameter $D = 1\,\text{mm}$ and consist of a polystyrene (\Gls{PS}) core (refraction index $n_\text{PS}=1.59$), doped with additional [[Wavelength-shifting molecules|WLS]] molecules. The core is coated with $T = 0.02\,\text{mm}$ of [[PMMA]] with a refraction index of $n_\text{PMMA} \approx 1.50$ to ensure that the outer refractive index is lower than the inner one, thus enabling [[Total internal reflection|TIR]].

A schematic illustration of the cross-section of such a fibre is shown in the figure below.

![Schematic view of a typical Kuraray fibre.](THEO_Structure_Fibre.png)
*Figure 1: Schematic view of the cross-section of a typical Kuraray fibre.*

The difference in the refraction indices enables [[Total internal reflection|TIR]] for all photons emitted with an angle to the normal $\theta_i$ that is larger than:

$$
\theta_c = \arcsin\left(\frac{n_\text{PMMA}}{n_\text{PS}}\right)\approx 69.57\degree.
$$
All total reflected photons, therefore, lie within two capture cones that point in the direction of the fibre ends and have an opening angle:
$$
\omega = 2 \cdot (90\degree - \theta_c) = 40.86\degree.
$$
This is illustrated in the following figure.

![Schematic illustration of TIR within a WLS fibre.](THEO_Fibre_schematic.png)
*Figure 2: Schematic illustration of the \Gls{TIR} within a \Gls{WLS} fibre. The photons emitted within two cones that point in the direction of the fibre ends with opening angle $\omega = 40.86\degree$ are captured.*

With this information, it is possible to calculate the geometric capture efficiency $\epsilon_\text{TIR}$, which describes the probability of an isotropically emitted photon being captured by \Gls{TIR} within the light guide. For \Gls{WLS} fibres, $\epsilon_\text{TIR}$ can be calculated by the ratio of the volume of the two capture cones and the volume of the total sphere $V_\text{sphere} = 4\pi$. The volume of a cone is given by the solid angle $\Omega$:
$$
\Omega = 4\pi \sin^2\left(\frac{\omega}{4}\right).
$$
The total geometric capture efficiency is then given by:

$$
\epsilon_\text{TIR} = \frac{2\Omega}{4\pi} = 2 \sin^2\left(\frac{\omega}{4}\right) = 6.2\%.
$$

The fibres transport the photons to the end of the detector plate, where they are [[Optical Coupling|optically coupled]] to [[SiPM]]. 

In dieser Arbeit werden die Farsern des Herstellers Kuraray, Modell Y-11 verwendet. daher soll das funktionsprinzip der Fasern anhand dieses Beispiels erklärt werden.
Isotop emittierten photonen werden total reflektiert, wenn sie in einem Winkel  mit einer theroretischen WK von 20.4 Grad oder weniger auf den rand  des fibers treffen. Siehe abb.... 
Polystylene(PS) Core n =1.59 
Polymethylmethacrylate (PMMA) Cladding n=1.49
Calculate theoretical Capture efficiency 
Compare absorption and emission spectrum of WLS fibers

