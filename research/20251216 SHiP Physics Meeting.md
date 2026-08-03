---
Title: "Neutrino simulation and particle decay simulation chain in FairShip. Current status and ways to update them" 
Year: 2025 
Authors:  
Tags:  
---
- [indico](https://indico.cern.ch/event/1594362/)
## Neutrino simulation and particle decay simulation chain in FairShip. Current status and ways to update them
Zotero PDF Link: [genie_pythia.pdf](zotero://select/library/items/DQ9EG8JT) 

Related::  

### Persistent Notes 
%% begin notes %% 
Write notes here! 
 %% end notes %%

### In-text annotations
- <mark class="hltr-yellow">Neutrino and particle decay  simulation in FairShip</mark> [Page 1](zotero://open-pdf/library/items/DQ9EG8JT?page=1&annotation=AQ5JMQZ6)
###### Problem #1 and #2 [Page 5](zotero://open-pdf/library/items/DQ9EG8JT?page=5&annotation=9BR8RIHG)
- <mark class="hltr-yellow">All of them have quite different sigma</mark> [Page 5](zotero://open-pdf/library/items/DQ9EG8JT?page=5&annotation=GLBHMALB)
- <mark class="hltr-yellow">MPV of the P distribution is 2.5 MeV which is ~max  of the RES scattering channel</mark> [Page 5](zotero://open-pdf/library/items/DQ9EG8JT?page=5&annotation=6M92KWLB)
###### Problem #3. Pt is not defined for P > 50 GeV [Page 6](zotero://open-pdf/library/items/DQ9EG8JT?page=6&annotation=3EL8M93R)
- <mark class="hltr-yellow">In such cases Pt for P < 50 GeV  is used to sample Px,Py</mark> [Page 6](zotero://open-pdf/library/items/DQ9EG8JT?page=6&annotation=CAXKWXJ2)
- <mark class="hltr-yellow">The whole procedure is not  transparent at all!</mark> [Page 6](zotero://open-pdf/library/items/DQ9EG8JT?page=6&annotation=24LCTF7V)
###### Problem #4 [Page 7](zotero://open-pdf/library/items/DQ9EG8JT?page=7&annotation=8SCFU7XG)
- <mark class="hltr-yellow">All this time we’ve been using the neutrino-Fe56 scattering  everywhere.</mark> [Page 7](zotero://open-pdf/library/items/DQ9EG8JT?page=7&annotation=69JIKP9W)
- <mark class="hltr-yellow">Overkill for neutrino background, not correct for neutrino signal  studies, neutrino yield calculations and so on.</mark> [Page 7](zotero://open-pdf/library/items/DQ9EG8JT?page=7&annotation=8EJJHEM8)
###### Fix the issues [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=UAW2VPHA)
- <mark class="hltr-yellow">SND@LHC approach</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=3MLSIHQ3)
- <mark class="hltr-yellow">Pythia pN collision,  Geant4 propagation in the  target</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=4XRINXWS)
- <mark class="hltr-yellow">Ntuple of neutrinos</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=6ZNMG4XF)
- <mark class="hltr-yellow">GENIE nu-N scattering  simulation and scattering  position sampling</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=SPQECVMJ)
- <mark class="hltr-yellow">Output is a standard  Genie file with all the  information about  kinematics and  sampled event  position</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=BYWDDCIW)
- <mark class="hltr-yellow">Scattering nucleus is  sampled based on the  geometry file passed  as an input</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=WGNCS2NT)
- <mark class="hltr-yellow">FairShip particle  ropagation</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=QW573N9Q)
- <mark class="hltr-yellow">Output is weighted  events</mark> [Page 9](zotero://open-pdf/library/items/DQ9EG8JT?page=9&annotation=M56I5S3G)
- <mark class="hltr-yellow">All mentioned above issues are harmful for signal study and  overestimate background signal.</mark> [Page 11](zotero://open-pdf/library/items/DQ9EG8JT?page=11&annotation=ZTHWKN5I)


%% Import Date: 2025-12-16T10:34:11.014+01:00 %%
