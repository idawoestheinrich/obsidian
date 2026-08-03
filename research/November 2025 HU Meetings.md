---
tags:
  - status/wip
  - topic/ship/sbt/woms
  - type/meeting/weekly
aliases:
date:
---
# 25 November 2025 Hardware Meeting
- [[SBT Overview Talk]] rehearsal
# 24 November 2025 Analysis Meeting 
#### Jasmin
- Reproducing Anupamas results
- nEvents in 15 Years comparison
![[Screenshot 2025-11-24 at 12.07.24.png]]
- Tried to implement [[HTcondor]] - but it is not working yet 
- Is it a problem of the Generator? 
	- Or it is missing events
![[Screenshot 2025-11-24 at 12.19.32.png]]
- smaller binning - when a photon is converted into electron positron?
-  We don't use particle tracking - we do not know if its a muon, pion or photon
- If you do not know anything about a charged particle - you would assume that it is a pion 
	- 100MeV binning 
- IP cut of 10 cm - no events 
![[Screenshot 2025-11-24 at 12.23.17.png]]
- Peak at 1.5 GeV - Very Ugly - WE NEED more muon statistic
![[Screenshot 2025-11-24 at 12.24.57.png]]
#### Darja
- we expect more background on the salev side not on the jura side
- We don't know if Anupama has implemented what katharina did 
- Implement this in the extrapolation window
- HTConda
- The way we are doing this is not clever enough
- Histograms do not contain the other information anymore
- More clever: Write out the events that pass the selection and than only run on these events
- GNN graph neural network - must be trained - with the different [[Surrounding background tagger|SBT]] thresholds 
	- Performance will decrease 
	- Maybe we can recover by lowering the threshold on top and bottom 
- first normal graphs and then also without the first 5m 
- The NN is for the neutrino background much better than for the muon background 
	- If products do not hit the SBT we can not use it
	- Where the SBT fires we can use GNN
	- Can I train a specific network to reject muon DIS
- Change name: do not say DIS but inelastic scatering for neutrinos 
- Nucleon and a pion, multiplicity in the final state
	- Eduard: technically, it is 50:50 for excitation and dis
	- Totally different final states 
	- Train GNN 
		- on IS with exitaton of the nucleon 
		- On DIS - Dis will work much better, as it is not garantied that it hits the SBT
		- we can not measure momentum with SBT
		- If we combine tracker and SBT for DIS
	- Muon in final state - overestimated 
	- We have to give a presentation in the SHiP Physics meeting 
### Eduard
- also now we have info of the type of event that neutrino had
- so we can find out which parts of sbt are more dangerous either for res or dis
- it’s also always scattering on iron, which is also an overkill
#### Heiko: 
- What a mess
- Yaguslava produced events calling the Genea-Generator 
- We take events from preproduced Gene4 file 
- 2.6 GeV - [[Deep Inelastic Scattering|DIS]] is only 15% of the cross section 
- In- transperent what we are doing 
#### Shiva
- This looks much better to Heiko
- reconstructed pion, 
- You can not reconstruct photons
- Reconstruct the pi0 only one of the two methods work really well and the other does not
- FairShip - command vet track ID? 
- Photon sorting 
- Photon mother tack?
![[Screenshot 2025-11-24 at 12.53.59.png]]


# 18 November 2025 Hardware Meeting
- Hardware will need a it longer
	- Matthias said that he will order in a way that it will be paid this year
- We should understand what the geany generator does, what are the uncertainties on the neutrino yield
- Oliver - if its not in git we can not say what was done
- Neural Net approach - together with Will from Zürich

# 17 November, 2025 Analysis Meeting
#### Shiva
- Solved the problem? What problem? and how did he solve it? 
- [ ] Abstract DPG Meeting March 20 in Erlangen
	- [ ] Me: Quality Control Set Up!
	- [ ] Someone: [[Testbeam Analysis]] (Hannes)
	- [ ] Alessia can report on 4cell prototype 
	- [ ] Disentangle the work from Katharina, Jasmin and Darja
	- [ ] Shiva - its clear 
	- [ ] Deadline December 15 
	- [ ] Found DPG - apply to Haereus foundation before the conference 
	- [ ] Register for the conference
	- [ ] Don't miss the deadline for the early bird fee 
	- [ ] Hotel reservation 
	- [ ] DB Ticket buchen - sometimes it is possible to book
	- [ ] Reembursment for the Bahncard 25 
	- [ ] Membership in DPG!  Christian Scharf
### We have overestimated the neutrino background - Anupama
- Only a fraction of neutrinos produced hit the SBT (10%)
![[Screenshot 2025-11-17 at 12.44.47.png]]
- The b-/ mesons - decay at low momentum - due to the hadron stopper
- Probably also overestimated the muon background 
- Average neutrino energy is 2.57GeV - mean 
- DIS - is more likely than exiting a nucleon to a higher energy level 
	- If all are generated - conservative
	- If we have not generated the excitement of nuclei ? At this energies important?
	- We are not going into nuclear effects
- Usually the code is the documentation 
- There is some documentation from 2015
- Disscussing questions
- Anti-muon neutrinos? Different cross section 
- A factor of 6.5 below what we had so far
- Only the muon neutrinos
![[Screenshot 2025-11-17 at 12.35.01.png]]
![[Screenshot 2025-11-17 at 12.36.02.png]]
![[Screenshot 2025-11-17 at 12.38.06.png]]
- Electron/ tau neutrinos only at percent level
- Conversion of photons to electrons is negligible
- Talk to Eduard or Antonio  - An expert on this
![[Screenshot 2025-11-17 at 12.48.46.png]]
- We simulate as many as we expect?
- You should be able to pull it by tomorrow

- We reuse a muon many muons several times for the background estimation  - final weight that you get, should be the weight of the initial muon
- 
- Look at the TDR document to see the definition of the weights
# 29 Oktober - 12 November Testbeam at CERN
- [[Testbeam Autumn 2025]]
# 03 November, 2025
Maik can not contribute for a while - might take longer/ we can not build the objects 


## Topics to discuss
### Hardware
- Silicon pad offer and ask Yulia if we have the money 
- Meeting in December to design the transport box
	- Can we not produce a transport box that is big ne
