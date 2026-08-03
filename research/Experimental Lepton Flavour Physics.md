---
tags:
  - context/HEP_Herbstschule2025
  - topic/particle_physics
  - type/lecture
aliases:
---
Ann-Katharin Perrevoort
[Lecture 1: Experimental Lepton Flavour Physics](https://indico.physik.uni-siegen.de/event/592/contributions/1451/attachments/636/1488/ExpLeptonFlavourPhysics_Herbstschule2025_part1.pdf)

- Selction of experiments that investigate lepton flavour
- Leptons@Collider Experiments
- Muon Experiments
- Neutrinos
# 10th September 2025
## Indirect searches for BSM with Leptons
- Energy fortier 
	- direct production of heavy BSM particles
- Precision/Intensity frontier
	- Indirect search fir tiny deviations
	- Sensitive to small coupling and/or heavy particles in loop
	- Use processes that are rare or forbidden in the SM
- Lepton flavour is conserved due to an accidential symmetry in the SM
- **[[Lepton Flavour Violation]]** (LFV) is a forbidden process
- BSM? 
	- LFV often predicted
- If neutrino mixing is added to SM Charged LFV (**cLFV**) still heavily supressed
	- If you see it, you would have find BSM proof
	## Detecting Leptons
	- Charge Leptons
	- Photons
	- Hadrons
	- No neutrinos
	- *Transverse Slice of the Compact Muon Solenoid (CMS) Detector* 
	- Muons are MIPs and therefore go through the hole detector
	### Muons - the easiest to detect
	- Rather light
	- rathe long lifetime 
	- MIP - passes through all detectors and looses rather little energy
	- Characteristic signal in muon system - tracking and muon system
	- Cone around the muon and check how much other stuff is going on - how isolated is the muon
	### Electrons 
	- Electrons are very light and stable
	- Reconstructed from electromagnetic calorimeter
	- Need matching track 
	- Recover bremsstrahlung losses
	- Identification
		- Distinguish from jets
		- leakage in HCal
	- Isolation 
	### Tau - the hardest to detect
	- Heavy 1777MeV and short-ived 2.8$\cdot10^{-13}$s
	- Multiple decay modes
		- Leptonic BR ~ 35%
		- Hadronic BR ~ 65%
	- Neutrino from tau decay not directly detected
		- Reconstruct visible products
		- Missing transverse Energy
	- All decay products within a cone 
		- 1 or 3 associated tracks (1-prong/3-prong)
		+ calorimeter activity 	
	### Example Z -> e$\tau$ and Z->$\mu\tau$
	- with the full Run2 dataset
	- Oposite sign $l^\pm\tau^\pm$ pair
	- Back to back Z rest frame
	- $\nu$ collinear with $\tau_{had-vis}/l$ from $\tau$
	- Misidentification - Data driven estimate
	### Misidentification 
	- $\mu$ -> e (leptonic $\tau$ decays)
	- Reasons: Muon decay into a electron, emitts a hard photon - enhanced activity in ECal 
	- Expect mismatch of $p_T$ measurements 
	- fakes from jet -> $l/\tau_{had-bis}$ misidentification estimated with data-driven **fake factor** methods
		- Count events passing/failing quality criteria in a **fake enriched region** (FR)
		- Ratio is fake factor
		- Count events failing quality criteria in **signal region (SR)**
	- This is really tricky
		-  what are all the systematic uncertainties 
	## Observables
	- Two body decay ? 
	- Closest proxy to invariant mass of $l-\tau_{vis}- \nu$ system is collinear mass (not the missing mass)
		- invariant mass of $l-\tau_{vis}-E_T^{miss}$ system
		- Assume $E_T^{miss}$ has z-component such that the pseudorapidity of the missing energy agrees with the one from $\tau_{vis}$
	- Kinematic discriminant $\Delta\alpha$
		- $\tau_{vis}$ collinear with $\tau$$$p(\tau) = \alpha p(\tau_{vis})$$
		- Invariant mass $Z->l\tau$
		*whenever something looks to complicated we use a neural net*
		- **Binary neural net (NN)** 
		- Binned maximum likelihood fit to data 
		- World leading upper limit on branching fraction $B$($Z->l\tau$)
# Thursday 11th September 2025
 [Lecture 2: Experimental Lepton Flavour Physics](https://indico.physik.uni-siegen.de/event/592/contributions/1451/attachments/636/1488/ExpLeptonFlavourPhysics_Herbstschule2025_part1.pdf)
 ## Experimental Lepton Flavour Physics
 ### Recap:
 Lepton Flavour Violation 
 - a nice signature to search for
Charged Lepton flavour violation 
- forbidden in the SM
- predicted in BSM models
If neutrino mixing is added to SM cLFV still heavily supressed
Example from ATLAS 
## How to reach smaller branching ratio
- more stats - intensity
- lower uncertainties -> precison
- Background free
- Muons
## Searches for cLFV in Muon beams
- Muon Beams 
	## Muon Source at PSI
	- Paul-Scherrer Institude - worlds most intense continuous muon beam
	- Proton Beam from cyclotron (590MeV, 2.2mA)
	- Producing of pions on Carbon target
	- Pion decay to muons - very light mesons are the easiest to produce
	- 10000 muon decays per 1 electron decay 
	- Continuos sub-surface $\mu^+$ with 28MeV
		- $10^8\mu/s$ at existing beam line
		-  $10^10\mu/s$ with future High Intensity Muon Beam (2029+)
- High- intensity muon sources paired with high-precision experiments
	- first search for an exited electron - muon decaying into electron and photon
	- You can not produce taus that easy - *as many muons per second as taus per year*
- Golden Channels - MEG-MEGII search for $\mu^+ -> e^+\gamma$ and Mu3e for $\mu^+-> e^+e^-+e^+$ and M2e for $\mu^-N - > e^-N$
### $\mu -> e\gamma$  Decay  
Signal
- muon decays ar rest
- mono-energetic $e$ and $\gamma$ - back to back
Background
 - Radiative muon decay $\mu -> e\gamma\nu\bar{\nu}$
 - Neutrinos are invisible 
 - Accidential combinations
 Experiment with 
 - High muon rate
 - High resolution 
	 - Energy/momentum
	 - Timing 
	 - Pointing
	### MEG Experiment (Slide 25) (2009-2013)
	- At the muon energies - they are not MIPS anymore
	- Detect photons in Liquid Xenon photon calirometer
	- *in the beginning people where afraid, that positrons would get stuck in the detector for very long time*
	- Mono energetic photon and mono energetic positron
	- You can see, that they where scattered randomly and that energy is lost through neutinos
	- No signal found: 
		- Excluded the decay up to a many orders of magnitudes lower branching ratio than ATLAS
	- Upgrate to higher cabpabilities and higherer resolution
		- pixelated the timing counter
		- increased wire density
		- SiPMs on entrance surface of LXe
		- In operation since 2021: 
		- First results: - $B(\mu->e\gamma)$ < $2.2\cdot10^{-13}$  at 90% CL
		- $B(\mu->e\gamma)$ ~ $6\cdot10^{-14}$ SES
### $\mu^+-> e^+e^-+e^+$ at Mu3e  (Slide 33)
Signal
- 3 Body decays
- Same vertex, coincident, decay at rest
Background 
- Rare deacy $B(\mu^+-> e^+e^-+e^+\nu\bar{\nu}) = 3.4\cdot10^{-5}$
- Missing momentum due to neutrinos
- Need excellent momentum resolution
- Accidental combinations
	#### Tracking in the scattering dominated regime
	- Low-momentum affected by multiple Coulomb scattering
		- Energy loss and deflection 
	- Momentum reolution dominated MS
	- "Recover" momentum resolution
		- Consider scattering in track fit
		- Low material detector
		- Optimized - slide 39 
		- Have the particle to travel a hole circle
	- muon stop and decay on hollow target
	- Inner pixel detector - very thin inner and outer pixel layers
		- $\approx0.1\% X_0$
		- You don't want to hit your pixel detector with the muon beam
	- recovering scattering resolution 
		- extend the pixel layers - recurl pixel layers - scintillating fibres
	- Current limit: $B(\mu^+-> e^+e^-+e^) < 10^{-12}$ SINDRUM@PSI(1988)
### $\mu^-N->e^-N$ Conversion 
- Conversion within the muonic atom
Signal: 
- Mono-energetic $e^-$ ~ 105 MeV for N = Al
Background: 
- Muon decay in orbit
- Neutrinos invisible
- Beam-related backgrounds
	- ex. muon decays in-light, antiprotons, pions
- Cosmics
- Current limit: $B(\mu^-N->e^-N) < 10^{-13}$ SINDRUM@PSI(2006)
- Pulsed muon Beam
	- Muonic Atom with long lifetime $\mu^- N$, ex. T( $\mu^- N$)=864ns
COMET Experiment 

# Friday, 12th September 2025
## dLFV with Muons: Golden Channels
- Golden Channels 
- MEG-MEGII search for $\mu -> e\gamma$ 
- Mu3e for $\mu^+-> e^+e^-+e^+$
- M2e and COMET for $\mu^-N - > e^-N$
### Muons at Low Momentum
- High-momentum muons are MIP
	- pass through large amounts of material
- Low-momentum muons (1MeV-10MeV) have high dE/dx 
	- can easily be stopped in thin material layers
### Why do we look at Muons Decays at Rest? 
- Muon decay at rest
	- Every muon arriving at the experiment decays in the experiment 
	- High rate
	- Additional background from interactions with material
	- At most electrons and photons
	- No problem is lower p
- Muon decays in flight 
	- Most muons fly through the experiment
		- lower rate
		- muon dump
	- Decay products are boosted
		- Transformation to rest frame 
		- Vertexing more difficult
		- Higher track density per volume
### $\mu^-N->e^-N$ Conversion Mu2e and COMET
- forming a muonic atom 
- mono energetic $e$ ~105 MeV for N=Al
	- but you only see the electron
- Background: 
	- Muon decay in orbit
	- Neutrinos invisible
	- Beam-related backgrounds
		- ex. muon decays in-light, antiprotons, pions
	- Cosmics (1 per day)
	- Current limit: $R(\mu^-N->e^-N) < 7\cdot10^{-13}$ SINDRUM@PSI(2006)
	- This is not a decay it is a conversion 
		- Conversion rate $$R_{\mu e}=\frac{\Gamma(\mu^-Al->e^-Al)}{\Gamma(\mu^-Al->\nu_\mu-Al)}$$
	- Beam related backgrounds:
		- Pulsed muon Beam
		- Muonic Atom with long lifetime $\mu^- N$, ex. T( $\mu^- N$) = 864ns
	### COMET experiment
	- produce pions 
	- COherent Muon to Electron Transition 
	- Pion production:
		- Intense proton beam pulse on production target: $p -> \pi$
		- 1.2$\mu$s time in between the bunches
	- Decay $\pi -> \mu$ with 90° transport solenoid (no 'line-of-sight')
	- Phase 1
		- 90° transport solenoid between production and stopping target
		- CyDet detector surrounding stopping target
		- Sensitive to $R$ ~ $10^{-15}$
	- Phase 2
		- 180° transport 
		- seperation between stopping target and detector
		- Sensitive to $R$ ~ $10^{-17}$
	### Mu2e Experiment
	- Transport solenoid
		- seperating production and stopping target
		- S-shape
		- Transported along helicies 
	- Stopping target in front of the detector
	- The detector tracker and calorimeter is a "tube"
		- No hits in a region that you are not interested in 
	- Cosmic veto - one conversion electron per day
		- You need to build scintillators all around your detector 
	- Phase 1
		- Sensitive to $R$ ~ $10^{-16}$
	- Phase 2
		- 10x more protons with PIP-II 
		- Detector upgrates 
		- Sensitive to $R$ ~ $6\cdot 10^{-17}$ at 90% CL
How can you bound the $\mu$ in the atom?
Would would we learn if we see something? 
- Tool of choise: **Effective field theories** 
- if you change your target material you might see something different
- conversion mediated via different potential BSM interactions shows dependence on target material N
- Repeat the experiments
	- Limited choise of target materials: Ti, V, Li (in Mu2e)
		- choice due to life-time 
	- Years of beamtime per target
- Exploid the three-body decay kinematics of $\mu^+-> e^+e^-+e^+$
	- resonances
	- asymmetry ratios
	- **Dalitz plots**
- øπ@altPerformanceFirstFullSize2024; @christophemulleschCharakterisierungKostenguenstigenWellenlaengenschieberbeschichteten2023