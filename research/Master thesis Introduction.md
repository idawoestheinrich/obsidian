---
tags: []
---

This thesis will discuss two different topics in the field of detector research and development (R&D).  
Both are innovative technologies based on organic scintillators that are read out via wavelength-shifting (WLS) light guides.  
The following sections will present each of these detector technologies in greater detail and clarify the specific objectives of this thesis within the context of both topics.

### 1. Wavelength-Shifting Optical Modules for the SBT

The first part of the thesis will discuss the development of a quality control setup for Wavelength-shifting optical modules (WOMs). These WOMs must be produced and tested in large numbers in the near future for the implementation of the [[Surrounding background tagger]] (SBT) of the [[SHiP]] (Search for Hidden Particles) experiment. [[SHiP]] is a newly approved general-purpose beam-dump experiment based on technologies that have already been successfully demonstrated [[Alekhin_2016]], [[SHiP2022]].

[[SHiP]] is now in preparation at CERN to search for long-lived, feebly interacting particles with masses in the MeV to GeV range, like heavy neutral leptons, dark photons, dark scalars, and axion-like particles—also known as _hidden particles_—as predicted by a large number of models of the so-called _Hidden Sector_ (HS) [[Alekhin_2016]].  
With unprecedented yields of charmed hadrons, tau leptons, and photons above $100 , \text{MeV}$, [SHiP]] will operate at the _intensity frontier_ and complement the world-wide program of searches for _new Physics_ in the _high-energy_ and _precision frontiers_ [[SHiP2022]].  
The [[SHiP]] experiment will be installed and commissioned in a dedicated _Super Proton Synchrotron_ (SPS) beam-dump facility ECN3 in 2032. The current layout of the experiment is shown in the figure below.

![[2025_03_31_SHiP_layout_3D_with_labels_1.png]]
_Figure 1: Schematic illustration of the current layout of the [[SHiP]] experiment taken from [[SHiPinfrastructure]]. The setup consists of a high-density beam dump and a hadron absorber, followed by a magnetic muon shield reducing the detectors' flux. The Scattering and Neutrino Detector (SND) searches for the scattering of light dark matter and measures neutrino interactions. Long-lived HS particles will potentially decay in the $50 , \text{m}$ long decay volume into Standard Model (SM) particles, which can be identified and characterised in the downstream HS detectors._

The incoming $400\,\text{GeV}$ proton beam is dumped onto a high-density proton target, followed by a hadron absorber and a magnetic muon shield. The shield deflects the muons produced in the beam dump, thereby reducing the muon-induced background within the detector acceptance.  
The detector itself consists of two complementary systems: The _Scattering and Neutrino Detector_ (SND) and the _Hidden Sector Decay Spectrometer_ (HSDS). The SND searches for the scattering of light dark matter and measures neutrino interactions of all neutrino flavors.  
The HSDS focuses on searching the unexplored region of long-lived HS particles. The search sensitivity for long-lived particles depends on the distance between the target and the decay volume and the length of the decay volume. Consisting of a $50 , \text{m}$ long helium balloon serving as the decay volume and several sub-detectors, the HSDS is designed to reconstruct the decay vertex of a hidden sector particle and allow particle identification in an environment of effective zero background.

![[ShiP_Sensitivity.png]]

_Figure 2: Sensitivity of [[SHiP]] to (a) Heavy Neutral Leptons, (b) dark photons, (c) Higgs-like scalars S, and (d) inelastic dark matter coupled via dark photons. The light-colored bands around the lines indicate the effect of theoretical uncertainty in the production and decay of feebly-interacting particles. Taken from [[SHiPCollaboration:2929845]]._

In the benchmarks tested, [[SHiP]] is capable of detecting long-lived particles with a sensitivity that is 2-4 orders of magnitude in coupling scale beyond current experimental limits, and the span in mass may be over 1-2 orders of magnitude for fixed couplings. The expected sensitivity of [[SHiP]] to Heavy Neutral Leptons, dark photons, Higgs-like scalars, and inelastic dark matter coupled via dark photons is illustrated in Figure 2.

The SBT is subdivided into approximately 800 individual cells integrated into the support structure of the helium balloon, covering its top, bottom, and side walls. Each cell measures $60 , \text{cm}$ to $160 , \text{cm}$ in height $\times 80 , \text{cm} \times 20 , \text{cm}$ and is filled with a state-of-the-art liquid [[scintillator]] consisting of _linear alkylbenzene_(LAB) doped with $2.0 , \text{g/l}$ of the wavelength shifter _2,5-Diphenyloxazole_ (PPO), and equipped with two WOMs collecting the scintillation photons.

![[SHiP_SBT.png]]

_Figure 3: Schematic illustration of the SBT structure taken from [[AnnikaHollnagel]]. It surrounds the approximately $50 , \text{m}$ long decay volume. It is subdivided into approximately 800 individual cells filled with a state-of-the-art liquid [[scintillator]] (LS) and read out with two wavelength-shifting optical modules WOMs. The simulated photon emission and transport following a charged particle passing through the LS-SBT cell is illustrated on the right in green._

A [[WOM]] consists of a [[PMMA]] tube dip-coated with a WLS dye that absorbs scintillation photons with a wavelength in the range of $280 , \text{nm}$ to $400 , \text{nm}$ and re-emits photons in the visible spectrum. The re-emitted photons are guided to a circular [[SiPM]] array at the end of the tube via Total Internal Reflection (TIR) inside the tube walls.  
The wavelength shift is used to avoid re-absorption and to obtain photons with wavelengths in the range where the SiPMs are most effective. This detection system provides a cost-effective alternative to conventional photomultipliers, offering good time resolution and sensitivity.  
At least 1600 WOMs must be installed in the SBT. To ensure that these WOMs are of consistently high quality, a setup is developed in this work that will allow us to define a standard for and test the overall quality of the WOMs in the future.

---

### 2. Development of a New Plastic [[Scintillator]] Concept: CheapCal

The second part of this thesis focuses on generic R&D of a new plastic [[scintillator]] concept that is currently under development [[AlessiaBrignoli]]. The aim is to determine the time resolution of the current prototype developed within the _CheapCal_ project.

The CheapCal project aims to develop and characterize a new concept for a highly granular plastic [[scintillator]] calorimeter or large area muon tracker. The current CheapCal prototype is an extruded plastic [[scintillator]] plate based on polystyrene, doped with the fluorescents $1.5$% _p-Terphenyl_ (PTP) and $0.01$% _1,4-bis(5-phenyloxazol-2-yl) benzene_ (POPOP). The front and back of the plate are structured with 16 parallel WLS fibers.  
Minimum ionizing particles passing through the detector plate generate Cherenkov and scintillation photons in the material. The fibers absorb these photons and re-emit secondary photons with a longer wavelength. The re-emitted photons are guided by TIR to SiPMs coupled to both ends of each fiber.  
The distribution of the scintillation light collected by the individual fibers allows reconstruction of the point of passage, and the total number of photons collected by all fibers in a plate provides a measure of the energy deposited by the particle. By using scintillation materials with a high light yield and low attenuation length $\mathcal{O}(10 , \text{cm})$, a spatial resolution of $< 6 , \text{mm}$ is achieved, as the fibers closest to the particle crossing point collect most of the scintillation light generated.

![[CheapCal_detectorprinciple.png]]ciple)

_Figure 4: Schematic illustration of the detection principle of the CheapCal prototype. Charged particles that pass through the detector generate scintillation photons in the material (blue). The fibers collect these photons and direct them to both ends. The closer a fiber is to the source of the photons, the higher the average number of photons detected at its end. Taken from [[AlessiaBrignoli]]._

In this work, the time response and resolution of the current prototype will be determined. The result indicates the prototype's suitability for accurate event reconstruction and detector synchronization [[AlessiaBrignoli]], [[Valerian]], [[BenSkodda]].

The following chapters will discuss the physical principles of the various components of [[scintillator]] detectors, as well as their practical implementation and application in the two experiments addressed.

---

This version should work well in Markdown, with proper figure references, equations, and citations! Let me know if you need further adjustments.