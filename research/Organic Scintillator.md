---
tags: 
aliases:
  - scintillator
  - plastic scintillators
---
# Organic Scintillator Materials

The [[Light yield]], $LY$, in organic scintillators, describes the number of photons of a wavelength $\lambda$ produced per unit of energy deposited in the material. When charged particles pass through the scintillator, the Light yield $LY$ is, in first approximation, proportional to the loss of energy $E$ of the particle along the path:

$$
\frac{dLY}{dx} = \epsilon_{sci} \frac{dE}{dx},
$$

where $\epsilon_{sci}$ is the scintillation efficiency [[Kolanoski, 2016]]. This linear approximation is generally true for most minimum-ionising particles. However, a high ionisation density along the particle track can lead to quenching effects that reduce the expected light yield (see section on photobleaching). This loss is proportional to the energy loss due to the quenching effects with the Birks' constant $k_B$, which must be measured for each scintillator. This leads to the semi-empirical *Birks formula*:

$$
\frac{dLY}{dx} = \frac{\epsilon_{sci} \frac{dE}{dx}}{1 + k_B \frac{dE}{dx}}.
$$

If used in a particle detector, the scintillator should have the following properties (taken from [[Kolanoski, 2016]]):

- The energy deposited in the scintillator should be converted into light with a high light scintillation efficiency $\epsilon_{sci}$.
- The light yield $LY$ should be proportional to the energy loss of the particle $\frac{dE}{dx}$, which means quenching effects should be minimised.
- The scintillation medium should be transparent to the wavelength of the scintillation light, meaning that the probability of re-absorption of the emitted scintillation photons should be minimised.
- The emitted photons should have a wavelength matching the quantum efficiency of the photodetector used for converting the number of detected photons into an electrical signal.
- The duration of the excitation and light emission procedures should be as short as possible. A fast signal pulse results in good time resolution for the detector.
- The refractive index of the scintillator material should be close to that of the entrance window of the photodetector, enabling efficient optical coupling.

Crystalline organic scintillators in solid form often have a high light yield of approximately 15000 optical photons per MeV, but they are fragile and difficult to obtain in large pieces. Therefore, many organic scintillators are available dissolved in aromatic compounds as liquid scintillators. The aromatic compounds themselves are often also scintillators but usually deliver too few photons with a detectable wavelength on the required timescale.

Usually, two or more scintillating components must be added to the base material to fulfil the properties mentioned above. The additives are scintillators and wavelength shifters that enhance the Stokes shift, resulting in a higher light yield and shorter rise time. The size of the Stokes shift can be used to adjust the emission spectrum to the photodetector's quantum efficiency and increase the material's transparency [[Kolanoski, 2016]].

The absorption and emission spectra of the aromatic compounds and solvents used for the two scintillators

![THEO_LABand2gPPO](THEO_LABand2gPPO.png)
*Figure 1: Emission spectrum of linear-alkyl-benzene (LAB) doped with PPO (fluid scintillator used in the SBT).*

![THEO_POPOP_pTerphenyl](THEO_POPOP_pTerphenyl.png)
*Figure 2: Emission spectrum of p-Terphenyl (PTP) and POPOP (additives dissolved in the basic scintillator polystyrene used for the CheapCal prototype).*

The liquid scintillator used for the SBT is based on LAB doped with $2.0\,\text{g/l}$ of the WLS scintillator PPO. The plastic scintillator used for the CheapCal prototype is based on polystyrene, doped with $1.5\%$ of the scintillator PTP and $0.01\%$ of the wavelength-shifter POPOP.
