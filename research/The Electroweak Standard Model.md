---
tags:
  - topic/particle_physics
  - type/lecture
  - context/HEP_Herbstschule2025
aliases:
---
Steffen Schuhman 
# Wednesday 3rd September 2025
### Motivation 
- Theory not a model
	- construction paradigms
		- We can apply it in different frames
			- Lorentz covariant
			- gauge symmetry of Lagrangian, interactions
			- consistent with QFT
			- renormalizable
			- Occam's razor - minimal/simples solutions
		- provides means to predict new experiments
- Particle physics can discribe the degrees of freedom in the very early stage of the universe
- Cosmology - indirect way to do particle physics
## Scrutinizing the Standard Model
- Huge amount of data - Cross Section Measurements
Gauge bosons production processes
- Triple-,quaric gauge-boson couplings, Higgs production & decay 
- Make predictions for multiparticle 'outputs'
### Outline 
- Note: SSB symmetry breaking, Saturday examples - **Monte Carlo Generators**
### QED basics 
- Lagragian: depends on coordinates and velosities
- Using scalar products to be Lorenz invariant - current conservation: continuity equation 
- Theory has a freedom: gauge transformation of vector potential 
	- Choose to ease the caluclations
##### Single Dirac fermion $\psi$, Lorenz-trafo: 
$$L_{Dirac}(\psi, \delta\psi) = \bar{\psi}(i\gamma^\mu\delta_\mu-m)\psi$$
- Euler-Lagrange equation yields covariant Dirac equation 
- Dirac field bilinears, transforming under Lorenz-trafo 
	- scalar $\bar{\psi}\psi$
	- pseudi-scalar $\bar{\psi}\gamma^5\psi$
	- vector $\bar{\psi}\gamma^\mu\psi$
	- pseudo-vector $\bar{\psi}\gamma^\mu\gamma_5\psi$
	- tensor 
- assign fermion a charge $q$ - *minimally couple*
	- Lagragian + $q\bar\psi\gamma^\mu\psi A_\mu$
	- *covariant derivative* - absorbing this new term $D_\mu=\delta_mu-iqA$
- coupled Euler-Lagrange equations of motion
- simultaneous transformation of spinor and vector field 
	- QED lagrangian invariant under such transformations 
	- just a phase transformation $\psi'=\psi e^{iq\chi}$
	- U(1) symmetry
### Quantization and Feynman rules
- impose commutaion relations 
	- for dynamical fields 
	- Does not work because the vector field has more fod than the physical field
		- You have to *fix the gauge*
		- Fermion propagator and photon-fermion interaction vertex
		- Setting the rules for the caluclation 
	### inputs and predictions
	- QED coupling strength set by **Sommerfeld's fine structure constant** $$\alpha(0)=\frac{e^2}{4\pi}$$ $e$ elementary charge
	- fermion masses 
	- QED predictions crucial for atomic physics & HEP precision experiments
		- **The muon anomalous magnetic dipole moment **
	- if you take the square it fufils the eqom of a scalar - 
		- Not for fermions 
		- Square leads to a magnatic moment of the fermion 
		- *B-field coupling to spin magnetic dipole moment* 
		- **gyromagnetic factor ** 
			- $g_f = 2$ in dirac theory 
			- with first order QED correction $g_f = 2 +\frac{\alpha}{\pi}$
		- Measure deviation from dirac - up to 5 loops
## An issue: Loop-momentum integrals **divergent** - need for renormalization 
- logartitmically divergent
	### Outline for QFT regularization & renormalization program
	- Analog example: (Slide 14 and 15)
		- infinite wire
		- electric charge next to that wire
		- potential at the distance $R$ 
			- logarithmically divergent
			- **but** not a physical observable
		- The electric field is **finite** - physical observable
		- Regularize integral though cut-off length $\Lambda$ 
			- intoduce a ne parameter fixes the problem 
			- well defined potential differences - 
				- full potentials are not meaningfull - potential differences are
	- Problem: I have to break the symmetry of my theory to get this - not translation inveriant anymore
		- Different approach *dimensional regularization* - does not break the symmetry 
		- Do the calculations in D- dimentions
			- valid regularization can safely remove regulator, however, *not* the scale - 
	- Works fir QED as well 
		- infinte renormalizations of bare parameters $m_0, e_0$ and fields $A_{0,\mu}, \psi_0$
		- divergences can be subtracted order-by-order
### Question:
- potentials are useful because we write the lagrangians in terms of the potentials 
	- gauge fields are handy but are not physical [[properties]]
	- renormalize them in a way that we can work with them on each stage 
# Thursday 4th September 2025
 [Lecture 2: The Electroweak Standard Model](https://indico.physik.uni-siegen.de/event/592/contributions/1438/attachments/624/1421/EWSM_L2.pdf)
### The road ahead Slide 1
- lift **gauge symmetry** to construction principle for weak and strong forces 
	- $SU(3)$ and $SU(2)$ symmetries
- "we lift what we did for $U(1)$ to $SU(2)$"
- QED is parity conserving - the weak force is not - distinguishes between left and right chiral states
### Towards EW SM: chiral fermions Slide 2
- consider massless Dirac fermion $\psi$ 
- define superpositions $\psi_{R/L}$ of definite chirality $\gamma_5\psi_{L/R}=\pm\psi_{L/R}$
![[Screenshot 2025-09-04 at 10.23.26.png]]
- Lagragian for chiral fermions
- invariance under *global* phase trafo
- **mass term breaks chiral symmetry** -> breaks $SU(2)_L$ gauge invariance, need different source for mass term
### Non-abelian gauge symmetry
- consider doublet $\Psi$ of fermions and a unitary ($U^†U = 1$ ) transformation $U$ 
- Employ traceless, hermitian Pauli matrices $\tau_i$: $[\tau_i,\tau_j] = 2\epsilon_{ijk}\tau_k$
- "*Goodie good*"
- define *unit-determinant* matrices $V$ with $det(V)=1$ - we don't want to change the norm 
	- note: $V_1V_2 != V_2V_1$ is **non-abelian**
- small local $SU(2)$ *space time dependent* $\alpha_i=\alpha_i(x)=\frac{g}{2}\omega_i(x)$
- Add terms that are linerar to the vector field to the derivative - minimal coupling to cector fields $W_1^\mu, W_2^\mu, W_3^\mu$
- *covariant derivative* has to be gauge invariant ![[Screenshot 2025-09-04 at 10.38.09.png]]
- We have a new term - the last one - as the commutator does not vanish 
- **Interpretation** spell out that Lagrangian $W_i^\mu$ propagator and gives rise to self interactions
	- with antisymmetric $\epsilon_{ijk}$ always three different $W$ components
	- 4 vertex
### Weak interaction 
- insert experimental knowledge helps to construct a candidate $SU(2)$ doublets
- We have 3 lepton ($e$, $\nu$) and 3 quark doublets ($u$, $d$) 
- **weak isospin** $I_\omega = \frac12$ - for left handed part, right handed fermions have $I_\omega = 0$
- interaction via minimal coupling 
![[Screenshot 2025-09-04 at 10.45.59.png]]
- "I did not try to merch leptons and quarks - no experimental results"
### The Glashow, Weinberg, Salam theory (1961-1968, slide 7)
- unification of weak and em interactions
- **weak Hypercharge *Y***
$$Y_\omega = 3(q_f-I_{w,3})$$
the flipping of the spin is reflected by the 3rd component, insert electric charge and substract 3rd component of weak isospin
- A doublet has a well defined weak hypercharge - f.e electron and electron neutrino
- weak isospin singlets of three fermion generations
#### The Electroweak Standard Model Lagragian Slide 9
- kinetic terms for gauge fields $L_{EW}^{gauge} = L_{SU(2)_L}^{gauge}  + L_{U(1)_Y}^{gauge}$
- kinetic terms for leptons, quarks and minimal coupling 
### Interlude: the fate of symmetries 
#### The various ways of symmetry breaking 
- *expicit* breaking - Proton and Neutron have different masses
- There is a little breaking in the masses 1.5MeV  - The proton is lighter - otherwise it would decay
- induced by symmetry 
- Symmetry might be *hidden*: Goundstate is not invariant, Lagragian is invariant
#### Hidden symmetry
- symmetry Charge Q
- if the groundstate has zero charged - vacuum is unique, symmetry
- What if the vaccuum changes to $\alpha$ not to 0, if I act with my charge operator on the groundstate
- Charge operator kommuts with the hamilton operator $H$ ![[Screenshot 2025-09-04 at 11.02.59.png]]
- Exitations of a groundstate are particels - massless if the groundstate is zero - **Goldstone Bosons** Slide 10 
#### Higgs mechanism
**Can not give mass to the neutrinos as there are no right-handed neutrinos in the standard model** - right handed neutrinos not strictly standard model
construct a complex SU(2) doublet 
- construct an SU(2) invariant form
- Couple Higgs to the fermions **Yukawa interactions with fermion fields** - same trick for the down type spinors
**Fermion masses**
consider electron contribution for definiteless - we pick a groundstate for the scalarfield here, where the lower component is not vanishing $v/\sqrt{2}$
- goundstate does not have an electric charge
- Find the minimum of the field to get the value of the groundstate 
3 of the 4 generators are broken - $\tau_1, \tau_2$ and $\tau_3-\frac12Y_\omega$
- only linear combination $Q = \tau_3+\frac12Y_\omega$ preserves vacuum state
**Gauge boson masses**
- Vector field masses from minimal coupling terms
- Note: $W^\pm$-to $Z^0$ mass ratio fixed by $$ \frac{M_W}{M_Z}= \cos \theta_W$$
**Gauge boson fermion interactions** Slide 14
![[Screenshot 2025-09-04 at 11.19.11.png]] 

**- Cabibbo-Kobayashi-Maskawa matrix**

**The Higgs boson** - exitation of the Higgsfield above the ground state
# 5th September 2025 
[Lecture 3: Standard Model precision physics](https://indico.physik.uni-siegen.de/event/592/contributions/1443/attachments/627/1442/EWSM_L3.pdf)
## Standard Model precision physics
- Recap Lecture II
	- Up to yesterday - classical field theory 
	- Now: quantisation and renormalization, virtial and real -emission, QED IR divergences, Next To leading order NTL
	### Parameters of the Standard Model: (Slide 2)
	- two gauge groups - two related coupling parameters $g_1,g_2$ vacuum experctation value $v$ : 
	- Fixing of the parameters (tree level relations:
		- Fine structure constant $\alpha$
		- Fermi weak coupling constant $G_F$ (derived from muon lifetime)
			- sets the scale of ew symmetry breaking 
		- Mass of the $Z$ boson $M_Z$ 
		- Higgs boson mass $M_H$, fixing the *quartic coupling $\lambda$
	- note: relations subject to higher-order corrections
	- different schemes to define consistent set of input parameters
		- You can decide what to set from what 
	- Higgs- fermion interactions
	- Up and down quarks can mix upon generations
		- CKM matrix - three mixing angles and one complex phase
	## Precision EW physics
	- search for unknown elements and inputs of SM
	- we have all the inputs! - within uncertaities theory fully determined
	Precision:
	- The aim to better determined the parameters - reduce uncertainties
	- We don't have experimental evidence for all SM processes , Higgs self coupling, rare decays
	- Seeking of BSM
	- perturbative caluculations 
	## Quantum Theory of EW interactions Slide 5
	- EW SM renormalizable
		- all UV divergences (Why are they called UV? - depending on the physical momentum scales that cause them) can be absorbed in renormalization constants
		- parameter and wave-function renormalizations
	- constistent OFT with quantum effects beyond the classical theory 
		- particle interpretation, interferences, $h/2\pi$-type corrections
		- scattering matrix elements
			- virtual & real-emission correction
	### Quantum Theory of EW interactions: gauge anamalies
	- classic SM lagrangian symmetric
	- SM features chiral femions 
		- proper cancellation needed fir theory to be free
	- consider triangle graphs
	- links quantum numbers of left- right-chiral fermions - Contrains
	- Example on slide 7 $0=\sum_[[Light yield|LY]]^2_{\psi_L}- \sum_RY^2_{\psi_R}$?
		- gauge anormaly cancels, symmetry preserved for all generations
		- *not much freedom to play around with the quantum numbers*
		- I can not only add one single particle - I need to add a family 
	- Another example Slide 8 **EW corrections on the muon magnetic moment**
		- physical result gauge independent, diagrams depend on gauge
			- non unitary gauges Goldstone bosons
		- EW corrections known up to two-loop order
		- reexpress your loop factor in terms of muon an W-boson mass
		- there a large number of two-loop contributions
		- *theory and experiment fully consistent SM uncertainty dominated by QCD*
	![[Screenshot 2025-09-05 at 11.58.14.png]]

	### Higher-order electroweak effects: real corrections
	- consider QED Bremsstrahlung to $\gamma*$->$\mu^+\mu^-$
	- assume photon is *soft *  $k^0 \ll p_1^0,p_2^0$
	- QED with massless photon features IR singularities
		- low energitic photons & collinear splitting of light paticles/photons
		- can be regularized 
	- collinear singularities also for initial-state emissions -
	### Higher-order electroweak effects: NLO corrections
	- total cross section IR finiete
	- real-emission singularities cancel against virtual corrections "soft divergencies"
	- For real emission of heavy particles - no soft divergencies
		- however inclusion of virtual EW corrections
	- automate NLO EW calculations 
		- set of tools `OPENLOOPS, RECOLA, MADGRAPH`
	- Example NLO EW results slide 13 - Corrections lead to 0.5-10% corrections
	- QCD corrections dominate at hadron colliders 
	- need to consider and combine EW and QCD corrections
		- combine in additive or multiplicative fashion
		- why $\sigma^{Born}$? 
	- **An example: NLO QCD+EW $pp$ -> $\mu^+\nu_{\mu}e^-\bar{\nu_e}j$**
	- consider full off-shell calcuclations, Born level 
	- apply veto on additional jets with $p_{T,j}>25$ GeV
	![[Screenshot 2025-09-05 at 12.16.04.png]]
	- - **Go differntial:**
	- QCD corrections clearly mdominate 
	- EW corrections also get sizable (~-20%) for high $p_T$/ large masses
		- emergence of EW *Sudakov-type logarithm*
		- if i am missing correction it might be possible that i miss a signal in that range
	![[Screenshot 2025-09-05 at 12.21.55.png]]
# 6th September 2025 
[Lecture 4: Standard Model precision physics](https://indico.physik.uni-siegen.de/event/592/contributions/1445/attachments/630/1462/EWSM_L4.pdf)
- Recap lecture III - NLO EW corrections - virtual corrections
- Up next: Cutting edge of doing NLO QCD & EW calculations
- MC simulations
- longitudinal gauge-boson production, from theory to experiment 
	### Predicting the Standard Model: [[Monte Carlo generator]]s
	- stochastic simulation of exclusive particle level events 
	- vital for realistic phenomenological and experimental analyses
	- adress breadth & deph of community needs/challenges
	- try to produce individual events, work hard to make these realistic, including NLO correction, check in simulations 
	- Field studies performed first in simulation
	### multi-boson production 
	- rare and subtle electroweak signal processes probing EWSB
	- triple, quartic gauge boson couplings, Higgs production and decays
	- two specific signatures  - diboson production, 
	- longitudinal production modes of massive gauge bosons
	### Including EW corrections
	- full NLO QCD+EW calculation: 
		- on-shell resonances - polariization studies
		- distinct kinematics - same final state but complettly different topology
		- particle-level simulations - QCD/QED showers
		- Consider EW, QED and mixed corrections 
	- Tools for all of these purposes (slide 4)
	- Software packages to accomplish these corrections
	- more than one tool, to estimate the uncertainty
	### Pushing the limites: multileg NLO calculations
	- **full NLO calulations for 2 -> 6 processes**
	- Consider like-sign W-boson scattering $pp$ -> $e^+\nu_e\mu^+\nu_\mu jj$ - defines the final state 
		- Try to take into account all feynman diagrams that can lead to the final state
		- Interferences of the different amplitudes (QCD and QCE)
		- Each order adds a power of $\alpha$ for EW or an $\alpha_s$ for QCD corrections
		- consider VBS Vector Boson Scattering event selection cuts - in particular a high invariant mass $M_{j_1 j_2} > 500\,$GeV 
		- full off-shell calculations vs, VBS approximation 
		- VBS/DPA with few % **What is DPA? - slide 6**
		- $\alpha^7$ dominates tails *EW Sudakov logarithms*
		- You can also consider *inclusive triple-W phase space*
			- Many $\mathcal{O}{(\alpha^6)}$ contributions $WWW, WH, WZ,$ VBS
		- **Totally different correction** if you choose different processes 
		- full off-shell calc vs. incoherent sum "the different processes don't talk to eachother"of on-shell channels (Slide 8)
		- "It is complex" Slide 8
		- inclusion of QCD parton showers, accounting for multiple QCD emissions
	### Taming the tails: EW Sudakov logarithms 
	- **universal high-energy enhancements**
	- Condider EW one-loop amplitudes in high-energy limits
	- all invariant masses much larger than $M_W$
	- dominace of scale-ratio logarithms
	- approximation to full NLO EW collections, possibly resummation of logs
	- extensive validation for OPENLOOPS -Slide 11
	## Probing EWSB: vector boson polarizations
	**The case for polarized weak bosons**  - recall lecture II
	- absorb oldstone bosons, fields have 3 polarizations - transverse $\lambda = \pm1$ and longitudinal $\lambda = 0$
	Study polarized vector-boson production and scattering 
	- Only if you include the Higgs interactions the diagrams are physicals 
	- We need the higgs boson 
	- $W_LW_L$ -> $W_LW_L$ 
	**Predicting vector-boson polarization fractions**
	- consider decay of on- shell massive gauge boson
		- first on-shell approximations 
		- Consider inclusive & fiducial phase spaces
		- Start to measure the fractions of the various componends to your observables
	- NLO EW for polarized $pp$ -> $W^+W^-$ diboson production Slide 14
	**A real-life application: first evidence for $W^\pm_LW^\pm jj$ from ATLAS** 
	- [paper](https://arxiv.org/pdf/2503.11317)
	- Stringent test of the SM EWSB mechanism
	- theory calculations facilitating precision physics
		- close and fruitful theory/experiment collaborations
	- **Proof of EW symmetry breaking!!!**
	**Accounting for (dominant) EW corrections**
	- Closing remarks
	- We just enterd the SM precision era
	- light fermions acuire through Higgs Yukawas? - besides electron, dominated by hadronic decays
	Is it possible to predict the sign of the NLO corrections? 
	- in the bulk of the phase space it is not possible
	- sometimes you can make predictions
	- NO SHORT CUT
	Evidence in a simpler process? WW is most interesting This is the place where the longitudinal polarisation plays a role