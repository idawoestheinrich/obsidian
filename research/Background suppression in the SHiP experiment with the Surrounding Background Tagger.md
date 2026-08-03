---
tags:
  - context/Research_Seminar
aliases:
date:
Authors: Anupama Reghunath, HU Berlin
---
- Overview of the experiment ![[Screenshot 2026-01-15 at 13.02.23.png]]
- Fully reconstruction/ partiallly reconstructed![[Screenshot 2026-01-15 at 13.03.57.png]]
- Mentions all timing detectors
- Veto system 
- Key Sources ![[Screenshot 2026-01-15 at 13.08.43.png]]
- Foccus on the first two cases - Muon DIS, nuetrino induced backgrounds
- [[DOCA]] < 1cm
- Trac pair vertex position >5cm from DV inner walls, >20cm from DV entrance
- Track Momenta >1.0GeV/c
- Impact Parameter wrt to Target - pointing back to the target - fully recon. <10cm, partially reconstructed <250 cm 
- PID final state check - semi-leptonic/ leptonic - Costom simulation software, MC check on the final state 
### How do we simulatr the background in SHiP
- Work arounds 
![[Screenshot 2026-01-15 at 13.18.01.png]]
- Muon DIS 
![[Screenshot 2026-01-15 at 13.20.41.png]]
 - Vessel case vs he backgrounds
 - Are we increasing the background by the SBT itsself
 ![[Screenshot 2026-01-15 at 13.23.00.png]]
 - Limited muon statistics
 - Manually generate interactions and put them in the system. 
	 - Than they need to be weighted 
 #### Motivation for an Advanced SBT veto
 - Basic - veto any candidate 
 - @45 MeV threshold ~76% of the signal candidates are lost ![[Screenshot 2026-01-15 at 13.27.50.png]]
- GNN SBT Veto
- Event described as a graph ![[Screenshot 2026-01-15 at 13.31.17.png]]
- WIth Extrao. + GNN SBT Veto @45MeV threshold, 15,3 %of signal falsly rejectred![[Screenshot 2026-01-15 at 13.34.13.png]]
- Not that clear with muon DIS 
	- To reach les than one 
	- Quite a large uncertainty on muons
	- Even with perfect UBT coverge
![[Screenshot 2026-01-15 at 13.40.48.png]]
	- Conclusion 
![[Screenshot 2026-01-15 at 13.41.40.png]]

What is with the K-longs? Why is that not an important background - 12 interaction length + absorber of 7 m length and than magnet system - a lot of iron 
- K-longs produced in the target are not are problem
How is the timing information used - Timing of the SBT and the timing of the straw tracker 
- overlay of signal and SBT activity - 150ns time window 
- Time info was used in the GNN 
15% false veto for partially reconstructed - could be different for the fully reconstructed
- What is the Wall made of - at cern the density is a factor of 2 higher - which kind of concrete - for SND it wouldn't matter - shielding walls have iron 

How many of the events are partially and fully reconstructed events (branching fraction at low mass is high but is lower for higher masses)?

- Aim for 0 Background events what would be the limit of the coupling?
At the very end you quote this huge efficiencies - they are required because the SBT has material. 
- Partially operate the SBT - at the hot spots