---
tags:
  - context/HEP_Herbstschule2025
  - topic/particle_physics
  - type/lecture
aliases:
---
# 10th September 2025
Lance Dixon [Lecture 1: QCD and jets at LHC]()
## LHC is a QCD Machine
- It is mostly considered as background
	### Inclusive jet cross sections
	- Jets over 30 orders of magnitude
	- 2000 events/second 
		- 1000 events per second is the output rate 
		- You only need a fractions
		- At the highest $p_T$ 5 events per day (1/3 of the proton energy)
	### Hardonic interactions with mater
	- typical hadronic cross sections are order 10s of miillibarns
	- **Hadronic showers** are irrgular and much harder to simulate
	##### At LHC outgoing hadrons -> jets
	### Particle flow (PF) methods for jets
	- if you have a charged hadron you can use the tracks to recover that 
		- charged pions - very good resolution on the momentum 
	- You have to be sure that you don't dubble count the energy of the charged hadrons 
	- PF removes cal energy deposits that are connected to tracks- the cal is used for the rest - neutral hadrons
	- Dramatic improvement in jet energy resolution for low momentum jets
	- 60 GeV jets is about 5-10 times worse than photons
	- Energy calibration is a big issue Slide 8
	##### Typical LHC collision from F.Krauss
	- One hard interaction 
		- Not always from the proton directly 
	- Lots of other stuff going on 
		- Multi parton interactions
		- A lot the secondary stuff
	- *Everything gets bigger when things get **soft** and everything gets bigger when things are **collinear***
	- When you go to larger distances - QCD undergoes a phase transition 
	- We don't understand that phase transition very well 
	- There is a calculateable part
	### QCD as a Yang-Mills Theory 
	- require local gauge invariance under a non-abelian gauge group Slide 10
	- Number of colors = components of quark field $\psi$
	- Constructing the Field strength with the commitator of the covariant derivatives
	- the resulting Lagragian is invariant and contains 3 and 4 gluon selfinteractions
	### QCD interaction
	- Gauge-fermion interactions, just with a matrix color charge
	- Triple gluon vertex is new, changes everything 
	### Asymptotic Freedom, 
	Gross, Wilczek, Polizer (1973)
	- Quantum fluctations of massless virtual particles
	- Gluon self-interactions make quarks almost free, make QCD calculable at short distances: $g_s^2/(4\pi) = \alpha_s(\mu) -> 0 $ asymptotically as $\mu -> \infty$  (large $\mu$ corresponds to large distances)  
	- $\alpha_s(Q)$ is precisely known (Bethke)
	van Ritbergenm Vermasern, Larin 1997,
	- confining 
	#### Standard Model Total Production Cross Section Measurements from ATLAS (Slide 15)
	- $W$ and $Z$ mass - NNNLO predictions
	- $t$ top mass - NNLO pedictions
	- The more complicated processes are only calculated NLO
	- Later: Structure of the QCD corrections
	- Experimental results - b-quarks and neutrinos that are hard to detect
	### Slide 16 - Most important slide in this theories
	## QCD Factorization & Parton Model
	Drell, Yan (1970s): 
	- Imagen the proton as something that has many partons in it - we can not resolve that in soft interactions
	- Asymptotic freedom guarantees that at short distances (large transverse momenta) partons in the proton are almost free
		- Sampled "one at the time" in hard collisions
		- QCD improved parton model
	- calculate before the quarks can form into hadrons
	### Producing Higgs boson at LHC Slide 17
	- dominantly produced in gluon fusion, at one loop level - mediated by top quark 
	- how close are you to the top threshold (top+antitop)
	- t couples strongly to both gluons and Higgs
	### Pertubative Short-Distance Cross Section Slide 18
	- Two gluon couplings to the top - and you square the $g$s 
	- Plot of the Higgs gluon fusion cross section at LHC vs. CM energy 
	- *In Short: LO always sucks*
		- Poor convergence of expansion in $\alpha_s(\mu)$ necessitates high orders!
	- If you want any precission at all you need higher order corrections
	### Z cross section Slide 19
	Baglio, Duhr, Mistlbergerm Szafron, 2209.06138
	- Much better behaved than Higgs production 
	- Z + uncertainty increases with $n_{jets}$
	### Overall structure of higher-order QCD corrections
	- Example of $Z$ production at hadron colliders
		- infrared divergences in NLO between virtual and real
			- Dimension regulation $D = 4 - 2\epsilon$
			- Quark radiates a gluon, 
			- Gluons splits into a quark, antiquark
			- It is independent of where the gluons go
			- divergencies on the left and the divergencies on the right cancel
		- NNLO - virtual corrections with 2 loops, 1 loop + 1 partoon, tree + 2 partons
			- indicate (1/$\epsilon^4$) IR concellations
	### Soft and collinear Divergences
	- Collectively called *infrred*, because they correspond to very small virtualities
		#### Soft (Gluon) divergences
		- Emission of a soft fluon off a quark line
		- To make gauge inveriant combine off another colored particle (could be a gluon) with momentum $p_T$
		- **Eikonal factor** at amplitude level 
			- Its square (cross section level) only depende on direction of emitters 
			- *Extra collinear* inhancement for $k_s||p_a$ or $p_a$
# 11th September 2025
Lance Dixon [Lecture 2: QCD and jets at LHC]()
## The Tail of the Mantis Shrimp:
- communication through helicity formulism
- Helicity formalism
### Helicity Formalism Exposes Tree-Level Simplicity in QCD
- Many helicity amplitudes either vanish o are very short
- *Parke-Taylor formular*
- Analyticity
	### basic variables: two-component spinors & spinor products
	- Use spinor products instead of Lorentz productio=s
	- If momenta $k_i$ are real, the are complex sqare roots of $s_{ij}$ 
	- Make sense of most basic process with all 3 particle massless
		- $s_{ij} = 2k_i\cdot k_j = (k_i+k_j)^2 = 0$
	- real (singular) and complex(non-singular)
### Most famous (simplest) Feynman diagram
- We spend most of our time to think about the kinematic part
- add helicity information, numeric labels
- Use *Fierz identity* 
	### Symmetries for all other helicity config's (Slide 9 )
	- Reweight helicity amplitudes -. electroweak/QCD processes
### Next most famous pair of feynman diagrams
(to a higher-order QCD person)
- It looks almost the same as the orignal form that we had
- for fundamental singularities - amplitudes are exposed
- Lets go soft
	- Soft gluon behavior - *gluons are always green*
	- Universal "eikonal" factors for emission of soft gluon $s$ between two hard partons $a$ and $b$ 
	- Soft emission is from the classical chromoelectric current: indipendent of parton type - only depends on color change
- Collinear behavior
	- Universal collinear factors, or splitting amplitudes depend on parton type and helicity 
	- Time-like kinematics (fragmentaion), space-like (parton evolution) related by crossing
	- Collinear limits (cont.) 
	- Applying C and P
	- Simplist pure-gluonic Amplitudes
	- [MHV(maximum helicity violating)](https://en.wikipedia.org/wiki/MHV_amplitudes) amplitudes with massless quarks
		- Verify soft limits
		- Extract collinear limits 
	- Space like splitting 
	- Similary for gluons
### "Suitable" final state, and infrared divergences in QCD
- use dimensional regularisation  
- soft singularities
- collinear singularities
- virtual soft/collinear singularities
### Infrared safety 
- Infrared-safe obersvables $O$
# 12th September 2025
## Parton evolution 
- Partons in the proton are not quite free: the parton distributions envolve as scale $\mu_F$ at which they are resolved varies. 
	- larger $\mu_F$ - closer to hard collision 
- parton destributioms are nonperturbative 
- must be measured experimentally - $ep$ collision at HERA (DESY)
- Evolution at $\mu_F>2\,$GeV is pertubative
- DGLAP equation 
### Precison PDFs:
- from DIS experiments, especially HERA, other experiments and LHC data
- **Essential imput for all LHC predictions**
### Still few % differences between groups
- NNPDF-MSHT, 2411.05373
- Differences at large $x$ 
- PDFs available via [LHAPDF interface](https://www.lhapdf.org/)
### Infrared safety
- Infrared-safe observable $O$
	- Behave smoothly in *soft* limit as any parton momentum -> 0
	- smoothly in *collinear* limit as any pair of partons -> parallel (||)
- Cannot predict pertubativly infrared-unsafe quantities, such as:
	-  number of partons in event
	- observales requiring no radiation in some region 
- Examples of IR safe quantities at LHC:
	- most kinematic distributions of "electroweak" objects, W,H, Higgs
	- jets, defined by cluster or suitable cone algorithm
	- **jet cluster algorithm**
		- Construct list of objects, starting with particles $i$, plus "the beam" $b$
		- Define "distance" between objects, vanishing in soft/collinear limits
	Jets are very. powerfull
	### "Catchment area" for soft particle depends heavily on jet algorithms
	- Cacciari, Salam, Soyez 0802.1189, anti-$k_t$
	- *anti-$k_t$* picks up soft radiation from underlying event more predictably 
		- easier to correct the underlying event 
 ### Drell-Yan process - simplist hadron collider process
 - LO partonic cross section 
 - LO hadronic cross section 
 - **rapidity distribution**
	 - rapidity $$Y = \frac12\ln\frac{E+p}{E-p}$$
- NLO OCD corrections *it gets more complicated* (Slide 12) Quark channel 
	- extra soft gluon singularity 
- QCD corrections to DY 
- DY/Z now known at N3LO
	- Total cross section
	- Differential distributions
	- Experimental uncertainties much smaller than theoretical uncertainties
### Real radiation in general case
- Cannot perform the phase space integral analytically in $D=4-2\epsilon$ 
- 2 Solutions 
	- Slice out
	- Substract method for more complex, differntial processes
- Two different types of substraction methods slide 17
	- Start with collinear approximation
	- Start with soft radiation pattern
Some answers 
### Soft-gluon/Sudakov resummation
- A precalent theme in QCD whenever one is 
	### Examples Hadron Collider Experiments
	- p_T(Z), p_T(W) latter needed for m_W measurement
- Threshold Resummation 
	- Can see the first threshold log in the NLO corrections to Drell-Yan/W/Z productions
	- Double-log expansion
- $gg->H$ Gluon distributions 
- Fast falling pdfs -- worse for gluons
- Sudakov suppression
- NNLO far prevered to NLO - LHC production of TTR
	### Massless internal 2 -> 2
	- NNLO 2->2 enabled by understanding 
	- Top pair production 
	- at subleading color at 2 loops (NNLO) 
	### NNLO 3 jet production 
	- State of the art: much computing power required
	- NNLO energy correlators for $a_S$
	- Asymmetry in transverse energy-energy correlator (ATEEC)
	### Conclusions 
	- Higher experimental precision coming with HL-LHC so theory must try to keep up 
	- *in order to find new physics we need to understand the old physics*