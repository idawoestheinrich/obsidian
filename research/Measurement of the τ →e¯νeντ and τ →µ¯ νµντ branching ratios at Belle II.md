Richard Volk
### Lepton flavor universality and branching ratios
- Weak leptonic decays of the tau can b precisely calulcated in the SM
- Allow for precise test of lepton flavor universality 
- Belle II currently lifetime and mass 
- Decrease uncertainty 
- Light lepton universalty Ratio $$\frac{B(\tau -> \mu\nu\bar{\nu})}{B(\tau -> e\nu\bar{\nu})}$$
- but no normalization 
### SuperKEKB
- data from 2020-2022, 400fb$^{-1}$

### Analysis strategy: Theory
- Produce two taus
- Selected and normalization topology 
- Calculate the number of producted tau pairs
- to calculate BR 
	- number of signal events
	- number of tagged tau events
	- efficiency of the detector and software
- Train your BDT (Neural network) on monte carlo and apply later to data
	- MC needs to be correct -
	- Preselection -
	- Background substraction 
	- unfolding (because you reduce your phase space - for the BR you don't care in what direction so you need to get back to the whole phase space)
- Backgrounds from different processes (not exhausive) and how to cut them out. 
	- Tau decays that decays in some other mode - particle identification and photon cut 
### Analysis strategy: Backgrounds before and after BDT
- Tautau sample composition after BDT - 75% signal
	- Purity of 91%
BDT discriminator value of 0.7