---
tags: []
rating: 2025-07-03
---
# SHiP SBT Meeting Freiburg July
## Summary
https://indico.cern.ch/event/1565821/
## Thursday 3rd July
#### Paul Luther - 4-cell prototype analysis, Timing, comparing electron and muon beam data
 - How do you smooth the waveform
 - Rising edge linear fit - for constant fraction discrimination
 - Fits the timing distribution and the width is the time resolution 
 - Compared CFD values for all positions (best between 10-25% should deliver the smallest sigma)
 - Direct photons - depending on the distance to the cell wall
 - Warum ist die Reaktionszeit kleiner je weiter die Position von der WOM weg sind? - Signal wird von der triggerzeit abgezogen, nicht anders rum
 - Difference to trigger time 
 - Linear fit of the timing vs. the distance
 - If a WOM is in the way of the direct photons, there is a significant difference
 - The speed is significantly lower then expected 7.67+-0.06ps/mm - photons are reflected from the backwall/ several times? 
 - The higher the light yield, the smaller the standard deviation, but the signal arrival time does not depend on the  light yield (at least in the center)
 - Electrons vs. muons - charge of the muons?
Heikos questions: Waveform changes slope- how does that look for different positions? Depends on the position
- we can not reproduce this with Monte Carlo 
- if the direct photon fraction is small, its not because of direct photons
- Some photon transport information  missing in Monte Carlo?
How can we implement this in electronics? 
- Some body could look into into the same for the new runs - more photons
#### 4 cell setup Angle Analysis
- Calculate the pathlength in the cell
- calculate total light yield
- Looked at the dependence of the light yield on the path length - tryed to perform a linear fit
- At 75 degrees we shoot through both WOMs  - the distribution looks very different (much longer tails)
	- What is the integration window?
	- Double peak (two different amplitudes)
- Light yield depends on the positions
- Light yields in WOMs c and d
If you can estimate the path length it would be nice to reconstruct the angle

### Liquid Scintillator
#### LS Absorption Simulated Fair
- Attenuation length  - Oct 2022, Mar 2024, Nov 2024- Peak at 500nm and 550nm (can we trust these measurements at such a high attenuation length?)
- Cell 1 shows a smaler integrated Yield than cell 2 although they are the same size
- Cell1 and Cell3 have a "bad" performing WOM each, probably bad coupling.
	- in all cases, WOM2 is a little bit worse, but it is probably a coincidence (maybe do to increased performance due to small airgap - total internal reflection?)
	- filling scheme?


### Cost of the detector
- Apparatus:
	- LAB costs? What is a realistic price tag? We have to contact a company 1650 Euro per ton/ - 2tons in 2023 over 3380 Euro/tone
	- Varies with the Oil price - Annika asks and Heiko in cc. 
	- Ratio between oil and LAB? Factor or fixed amount 145m^3 is 128.14 tons
	- Where should the trucks be stored for the LAB? Do we need storage tanks?
- Filling the detector in a go or do we do it in steps, how do we get the air out?
	- Fill each container first and then store it. 
	- Install and then fill the cells individually - requires to get the air out
		- We need a slope of 2 degrees
- Mark: How about a hole: Screw in the I- beams and drill in the expansion vessel into 
- Combination T and I beams - we want a symmetric 
- What is with pipes that point down on the inside? Can not be emptied - if we can empty the expansion vessel it can!
- T beams 
- Emptiing? 
- New Person power with the new symmetry 
- Photontransport simulation
- What slope is required to get the air out 
- PMMA vessels to look into the Container

## Friday 4th July
- The bottom of SBT should be discussed in a seperate meeting
- Sealing vor the WOMs - would it be possible to combine the sealing with the [[electronics]] box
	- Seperate discussion of the incapsulation 
#### Heat production SiPM boards tilmann
-  additional cup - temperature rise of 4 degrees 
- with a copper wire connecting it to the aluminium box cools it down to 28 degrees
	Additional cooling system with CO2
	Heatpipes could also be an option?
- Simulation should be tested experimentally.
- How big should the cup be? Cup over [[e-music]],
#### Fair 3 Cell testbeam November 2024
- Light yield over size and reflectivity of the cells
- In the corner, we see the improvement in transparency
This raises the issue of [[Purification]] of the [[Linear alkylbenzene]]
- 2 good cells (polished aluminium and PTFD (?)) both [[WOM|WOMs]] show essentially the same signal
- Different sizes of WOMs diameter of 3cm/6cm/9cm - signal scales with the number of SiPMs
### LAB Purification
Annika shows her work since to 2017
https://indico.cern.ch/event/1565821/contributions/6595477/attachments/3098119/5489571/2025-07-03_ship_ls-sbt-retreat.pdf
### Electronics FastIC TB 05/2025 Tim Molzberger
https://indico.cern.ch/event/1565821/contributions/6595474/attachments/3098125/5488801/Tim_July_Meeting_Talk.pdf
- [[FastIC]] to replace the [[eMUSIC]] ASIC
- returns digitized Time Arrival measurements and Energy 
- Shapes and amplified waveforms 16+ch wavecatcher trigger + Berlin counter