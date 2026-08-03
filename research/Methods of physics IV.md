---
tags:
  - context/DPG2026
aliases:
date:
---
# Tagging at ATLAS with GN3: Beyond heavy-flavour
- Diptaparna Biswas
> Accurate identification of jets that originate from heavy-flavour hadrons is pivotal for many ATLAS analyses, from Higgs-boson and top-quark measurements to searches for new physics. We present GN3, our newest jet flavour tagger, which introduces a full-transformer architecture tailored to the environment of LHC Run-2 and Run-3.
GN3 processes low-level track, neutral particle, and muon information to extract correlations between the inputs and infer the origin of the jet. Compared with the current Run-3 baseline, GN2, the new model achieves a significantly better separation of b- and c-jets from light-flavour jets across a wide kinematic phase-space.
In this talk, we will discuss the architecture and training workflow, as well as the newest results from GN3. Furthermore, we will highlight the new capabilities added to GN3, which extend its functionality into the realm of s-tagging.

# Identification of low pT b-hadrons at the ATLAS experiment
- Hagen Möbius — DESY, Zeuthen, Germany
- The identification of b-hadrons in an event, called b-tagging, is an important part of the physics program of the ATLAS experiment, in particular for Standard Model precision measurements, studies of the Higgs boson and searches for physics beyond the Standard Model. The starting point for standard b-tagging techniques in the ATLAS experiment are jets, bundles of particles. This leads to constraints on the energy of both the b-hadron and the surrounding hadronic activity and consequently low pT b-hadrons in a jet below the jet reconstruction threshold are not reconstructed.  This talk presents an algorithm with a jet-independent b-hadron identification strategy. The algorithm, called the *NewVrtSecInclusiveTool*, reconstructs secondary vertices that can be associated with the decay of low pT b-hadrons. The procedure and performance of the algorithm are discussed. Furthermore, the origins of the tracks contributing to these secondary vertices are examined to assess the accuracy of the b-hadron reconstruction.
- b-Hadrons produce secondary verticies SV
- If PT is to low b-Hadrons do not produce a jet
- Soft secondary verticies 
- HepMC event record 
- Efficiency and average number of fake SSV
	- Truth track making tool 
	- 
**Summary**
-  low pr b-hadrons are missed in standard b-tagging techniques since they rely on a jet above the jet reconstruction threshold
- NVSI is a new approach to reconstruct low p, b-hadrons independent of a jet → construct soft secondary vertices
- defined SSVs outside of jets and b-hadrons in acceptance
- introduced a AR matching procedure to define true SSVs, so SVs coming from a b-hadron decay and fake SSVs o defined SSV tagging efficiency and average number of fake SSVs to quantify the performance of the algorithm SSV track origin analyses revealed:
- 99.4% of the matched SVs have 50% or more tracks coming from a b-hadron → AR classification works o 8.7% of the fake SSVs are purely from b-hadron tracks → not fake

# Investigating the use of fast detector simulation for jet flavor identification algorithms in ATLAS —
Austin Olson

In the ATLAS experiment, identification of quark flavor in a given jet is done with machine learning algorithms known as “taggers”, trained with simulated events. Taggers’ performance depend on accurate simulation of jet constituents. Previously, only tracks associated to jets were used in training, but the latest tagger, GN3, also uses all particle-flow constituents. At the same time, approximation of calorimeter showers with generative modeling (FastSim) is becoming more adopted by the ATLAS Collaboration in lieu of full Geant4 simulation (FullSim). 
Many rare signal samples and several background samples are pro- duced using FastSim, making it essential to evaluate the performance of these samples in this new GN3 model. Recent studies indicate significant scope for improving performance of GN3-like models solely by increasing the amount of training data, making FastSim samples a desirable option for model training itself. This talk presents comparisons of FastSim and FullSim samples in the context of ATLAS taggers.

- classical simulation 
- computational expensive f.e. GEANT4
- Calorimeters - relay on Machine Learning? Is it scaleable
	- is it accurate?
	- can it map to full Sim
- Input variables evaluated
- neutral particle flows
- about 10 % differnce in b-jets, c-jets light jets
	- for light yets 20% less muons
- Signal efficiency 
- GANs - why don’t swich to normalizing flows

# Shiva
- why can we see photons with the SBT
- It is taken into account, that the  $\rho$ mass is not constant
- How do we distinguish different masses 
- What is our mass resolution?

# Measurement of the η Reconstruction Efficiency at Belle II— 
•Johannes Mirfanger
- The precise reconstruction of η mesons is essential for a wide range of physics analyses at Belle II. This work presents a data-driven determination of the η reconstruction efficiency using the decay D*+ → D0π+, comparing the two D0 decay modes D0→ K−π+ and D0→ K−π+η. By forming the ratio of these channels and correcting for the known branching fractions, we extract the η reconstruction efficiency of the Belle II detector. A key strength of this method is the ability to directly compare data and Monte Carlo simulation, enabling a clean assessment of potential discrepancies between them. 
- The extracted efficiency is further studied as a function of key kinematic variables, including the η momentum and polar angle. This offers detailed insight into detector performance across phase space. Ongoing work focuses on evaluating the robustness of the efficiency under varied event-selection criteria and on optimizing cut strategies for future analyses. The presentation will discuss the current status and give an outlook on the analysis.
	How many do we construct and compare to how many there should be
	- control channels 
	- Fit the flat background and the peaking signal - estimated number of signal events
	- Till now only simulated data
	- 0.52 efficiency 
	- Show a correlation 

**Summary**
• Reconstruct D* from D° → K°n* n and D° → Km*
• Extract signal events by fit of the D° masses
• Calculate channel ratio to get , Reconstruction efficiency
**Outlook**
• Use the method on real recorded Data (full Belle I| Dataset)
• Try recoil method to validate the study (e* e -> n + X)





