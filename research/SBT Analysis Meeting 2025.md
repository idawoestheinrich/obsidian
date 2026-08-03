---
tags:
  - status/wip
  - type/meeting/weekly
  - topic/ship/sbt
aliases:
  - SBT Software & Analysis
date:
---
Say in the beginning of the meeting: My task was - Andrii has a really nice way introducing what he ist doing



# 20251217
- Check for feachers in the noise
![[Screenshot 2025-12-17 at 09.34.11.png]]

![[Screenshot 2025-12-17 at 09.30.09.png]]

![[Screenshot 2025-12-17 at 09.24.28.png]]

![[Screenshot 2025-12-17 at 08.48.14.png]]

![[Screenshot 2025-12-17 at 08.47.04.png]]



- Implement current geometry - 2-3 month - best installations in FairShip
# 20251210 

Fast Simulation - talk to Alessia 

Upload 
#### Fairhurst
- Put a cut on the integrated yield which was 50 
- Perfect case for AI
- Stakt histogram 
	- instead of markers
- Reconstructtion possibility 

#### Andrii
- integrate 20ns before till 100ns after
- Shows time distribution 
	- Shorter than what we see in data
	- We integrate a lot of noise
- Alessia said that the wavefrom was not shorter - Horst would be suprised because the readout board influences the length of the waveform
- Channel heatmap - for a single muon in the center
	- It seems not to do what we would expect
		- for one event 
	- Large veriations from event to event 
	- For 1000 events it looks good
	- For the two muons 100 events
	- digitalisation 
![[Screenshot 2025-12-10 at 08.24.49.png]]



# 20251203
#### 4-cell prototype paper 
- We should not show the old layout of SBT -Horst
#### Andres
- Temperature dependency of the Light Yield
- Gain dependency on temperature
- Horst suggested that it is not due to the SiPMs
- 10 kOhm boards behave differently from the 0Ohm boards
- Factor of the amplifier? Slow drift due to change in room temperature
- Testbeam data Cell B - measurement 12 hours later drop of 2 degrees - light yield changed
![[Screenshot 2025-12-03 at 08.13.25 1.png]]
- When andres tried to refill the cell with nitrogen
- If you pump in the nitrogen into the cell you can not get it out anymore
	- You can not make this mistake twice
- Temperature correction to a calibrated temperature of the board

#### Annika
- in may we played around with different thresholds

#### Fairhurst
- regarding the paper
- In the simulation we do not have the hadron contamination 
- Even if we put in the cherencov detector we have hadron contamination 
- Cut out the really high events 
![[Screenshot 2025-12-03 at 08.30.46.png]]
- At T9 there is no Cherencov detetor
- Some Hadrons shower some do not 
	- Showering hadrons
- We can ruffly estimate the fraction of hadrons that produce a shower
#### Shiva 
- has nothing presentable yet
- Digi-hit tells you when a cell is firing 

# 20251119 
### Andrii Pachkov
- no access to his work computer

### Jasmin Weiß
- Looks at muons passing through the UBT
- Physical Muon weights
- Mass revers to invariant mass of the vertex![[Screenshot 2025-11-19 at 08.08.45.png]]
 - ![[Screenshot 2025-11-19 at 08.08.40.png]]
- ![[Screenshot 2025-11-19 at 08.11.13.png]]
- ![[Screenshot 2025-11-19 at 08.08.27.png]]
- do not hart code it - have the geometry of UBT as variable 
- How often do these Muons produce DIS
- UBT does not cover the whole SBT entrance window
- We have not seperated where in the SBT the DIS take place
- We need a larger muon sample
- It looks like we add a bit more DIS event inside and not outside
- Choose always the same x and y axis
- Reduce the background by not instrumenting the first meters on the side
### Normalisation problem
- Does the normalization problem also influence the other studies on muons?
- What Anupama quoted in the overleafe - not the anti-muon neutrinos - we dont have the same number of pi+ and pi- 
- Background is larger by ~50%
- Average Neutrino energie 2.5 GeV, Cross section/ Energy is a constant 
	- At 2.5 GeV DIS is a 15% effect - mostly we have interactions on nuclei
	- We don't have the script in hands from Yaguslava
		- Pretty sure that everything is included but we do not understand what we are doing
	- Yaguslava said she did it the same way as Antonio
### Heiko 
![[Screenshot 2025-11-19 at 08.44.43.png]]
- Why is it symmetric if the neutrinos come from charged particles
- Main muon neutrinos flux comes from pions and kaon in rest stopped in the hadron absorber
- Electron neutrino - some charm 
- Tau from b-mesons and mostly charm
- Heiko guesses that this plot has a cut on the energy of neutrinos - above 0.5 GeV
	- Pion does not decay in rest but in flight 
	- Then it should have a direction 
	- Maybe it is counter balanced by the fact that we have more neutrinos than anti neutrinos
- Do we really see only 10% of the full neutrinos flux in the decay volume
### Alessia
- on the paper
- Should we put another plot on the positions - caption x means 0 degree and o means angle
	- Used for the likelyhood method Alessia applied
	- Rotated in both directions
	- Work with open markers for simulation 
	- Closed dots for data points
	- LIght and darker feights
	- Harmonise the plots 
# 20251105
#### Tykhon
- Rewrited the code and fixed the bugs 
- will show something tomorrow 

#### Andrii Pauchkov
- looked at the simulation for 2 muons hitting the detector at the same time
![[Screenshot 2025-11-05 at 08.07.45.png]]

- The reflectivity was set to 0.8
- Check for individual events 
	- maybe there are very similar because we average
 ![[Screenshot 2025-11-05 at 08.12.53 1.png]]
 - Digitalization part 
#### Katharina
- Is sick 
- did not finish the weight adjustment 
- Discussed the skript with Darja and Jasmin
	- PID required for the final state particles? NO

#### Darja 
- Run the Neutrinos as CDCondor on multiple computers
- SBT veto thresholds 
	- Runs the version where you have different thresholds on the walls

#### Alessia
- on 4 cell prototype
# 20251022
#### Andres
- WOMs are 2mm,  not 3mm WOMs 
	- if possible put both Which of the WOMs 
- The rings are not positioned right 
- We agreed to move the ring 
- 3.5mm distance WLS 
- Similar photograph of the old ones - 4 cell WOMs
- Other WOMs - older WOMs long term performance 
- we could use the magnetic properties of the Ring 
- Bubbles: ![[Screenshot 2025-10-22 at 08.07.15.png]]

#### Paul Luther
- Berlin Counter improves the position reconstructions
- Make an edge scan in this testbeam as well 
-  Beam diameter seams to align with the Berlin counter 5cm 
![[Screenshot 2025-10-22 at 08.23.17.png]]

### Fairhurst Lyons
- added more to the paper
- Standard deviation looks very large, due tue the landau tail 
	- Mention that in the paper
- Likelihood correction - use open squares
- Simulation for one of the cells 
![[Screenshot 2025-10-22 at 08.45.40.png]]
- Standard deviation so large - why?  - Mean fits but sigma does not
- If the error is 10% does it remain after scaling? 
- Is it due to the landau tail? 
- Will show Histogram tomorrow - 
### Alessia Brignoli
- Comparison of the expected arrival time vs. monte carlo
- 


# 20251015
#### Andrii Paichkov
- Two Beams arriving at the same time? 
	- We need the photon arriving time for the two WOMs seperatly
![[Screenshot 2025-10-15 at 08.06.15.png]]
#### Testbeam next year
`chronos -[2026-07-08~2026-07-22] #pink Testbeam? T9`
- incapsulate
- Until when do we have tightness
- Which electronics do we place inside
- Cell C - Fire below? When does it explode
# 20251008
#### Katharina
- will report tomorrow
#### Alessia
![[Screenshot 2025-10-08 at 08.13.37.png]]
- Check what the time difference is - is there a shift for one WOM? 
![[Screenshot 2025-10-08 at 08.18.19.png]]
- Do we see the same shift for all cells? 
	- Is it cable length? coinsidence box?
	- Did we move the teleskope? Maybe a centimeter
### Fair
- will continue to put text into the paper draft
#### Testbeam
- Andres and Fair started discussing which measurements we should do
- Large detector? 
	- Concentration on the 0 degrees as this gives the smallest light yield
	- Different angles and points to understand the detector response
	- Focus on rotation around the y- axis 
	- 2 WOM setup or 3 WOM setup?
		- Be able to compare the measurments
		- If we do the grid - 45 points the compairison would take 4 days 
	- For the right hand side we can not measure the whole detector
![[Screenshot 2025-10-08 at 08.33.09.png]]
# 20251001
## Testbeam
- Eurolabs
	- Files - responsible for the testbeam Heiko
	- we have to decide on the Co - Responsible
- Do we have the Foils
- The reason why nobody 
- The DESY table hangs to one side 
	- Effect will be even larger, as the Cell is bigger (1.8m wide)
	- The desy table hight 445 cm 
	- Horizontal movement with rails
![[Screenshot 2025-10-01 at 08.18.47.png]]	- 
- Do we plan to place the Cell upside down
		- No
- Same coordinate different rotations
- Who plans the positions and how
- Turn tables - 
- More fine angle resolution ? 
	- 15 degrees should be okay
- Everything has to be done manually 
- One or two of these tables
- Detector material - Aluminium
	- Should be delivered 15th September
	- Welding should be done on Monday the 6th
	- Distributer had problems with the polishing 
	- The flat material should be done delivered tomorrow 
	- *Jemand muss das Land retten, wir arbeiten natürlich auch am Wochenende* - Person from the Welding Company 
	- If everything goes well the detector will be in Freiburg on Friday 12th
	- Difficulties with Polishing can lead to higher costs
- The flunshes and everything is already produced
- SiPM Boards arrived in Freiburg 
	- Plugging and unpugging more difficult
	- Andres and Tillmann are preparing the glueing to the WOM
		- Very precises glueing
		- Testet with dummies - Felicitas
		- Glue Epothec 301/2 - also used in the dark detector
			- best refrective index
			- transparentsy in the UV/blueish
		- Tilmann is preparing the setup
			- normalisation
			- temperature
	### The WOM tubes 
	- remainders on the WOM ends, 
	- The way we transport 
		- Look into this with Constantin 
		- How to savely transport the WOMs to Freiburg 
		- Meet in the Middle between Chemniz and Berlin - Dresden

## Testbeam 2026
- needs to be discussed
- Very late is end of July 
- Early is Feburary 
- Ask for one second half of march
- German Spring Meeting week 16. March 
- Feburary 23rd for the Collaboration Meeting 
- 2nd week of July - Heiko is at CERN anyway but not good for Heiko 
- Place
## Analysis
- 
# 20250924
### Andrii Pauchkov
- What is in between the cells: Nothing - Andre 
- 6 cells which are combined together 
- It depends on what to simulate 
- Muons that hit one cell? 
- Different angles - center 
- Zero Angle but different combinations where the muons hit the cell 
- [Annikas Talk](https://indico.cern.ch/event/1516350/contributions/6386944/attachments/3029341/5348333/2025-03-11_ship-infrastructure-ls-sbt_.pdf) 
- Infrastructure Workshop?
- From the testbeams we have certain crossing points
	- Choose combinations of these points 
	- And next step: Non zero angles
- Already simulated some events, not high statistics
### Horst 
- Suggested to turn on the camera
### Paper
- What we can do we should do
	##### Alessia Brignoli 
	- Send an Email regarding the reconstruction 
	- Already include the plots into the paper draft  ![[Screenshot 2025-09-24 at 08.19.02.png]]
	- Paul remembers that the channels were swiched 26th March
	- No correction of Light Yield applied yet 
	- From the distribution 
	- Is it easy to calculate the difference in time of flight?
		- It should be easy 
### Analysis of the last Testbeam
- Fairhurst looked at the Dark Count - we should apply cut at 800 mVxns like in the DESY prototype
	 - Dark count looks similar to DESY
	4 cell prototype: 
	![[Screenshot 2025-09-24 at 08.30.13.png]]
	DESY
	![[Screenshot 2025-09-24 at 08.31.07.png]]
	 - We should cut sufficiently high enough - so that we have definetly no dark counts - what is for short pass length 
	 - What is the signal in the Center? 
	![[Screenshot 2025-09-24 at 08.38.57.png]]
	- Signal on the bottom? iy00lowwoms
	![[Screenshot 2025-09-24 at 08.40.44.png]]

# 20250821 
- In the Lab while fixing rotation Motor
- new cooperation with Kiew 
- Anupama and Lukas(?) showed their results
# 20250828
- Possible exercises for the people in kiew
### Alessia Brignoli on Reconstruction
- 90 degree likelyhood ![[Screenshot 2025-08-28 at 12.06.54.png]]
- Reconstructing the angle by combining the information from several Cells![[Screenshot 2025-08-28 at 12.17.10.png]]
- The fact that you don't see information in Cell A exclude big rotations around the x-axis 
- Positions means x-y and angle
- You gain precicion
![[Screenshot 2025-08-28 at 12.24.22.png]]

- Run reconstruction with more than 4 cells? Multicell detector
	- Could be an interesting task for Kiew
	- They also need to implement the creation of the waveform with the simulation
		- Waveform includes the smearing
## Paul Luther
- Chose a threshold that was to low
	- That was why there was a second peak
- Berlin counter lower -50mV? Does this effect also happen with the beam telescope - Used only one channel 
	- Also shows a population that show up later? (Some events where the trigger reacts earlier) 
	- Smearing on the right side - could happen due to a second particle?
	- Why is there a defined time difference between the two?
	- Two particles ns apart passing through - one of them only passing through 2/4 detectors - the other one passes though 3/4 and triggers an event
- why do we have two populations 
- Cherenkov photons in the light guide? 
	- Would also explain why we don't see that for the timing measurements in Berlin?
	- We observed in the lower one and the upper one - Light guides are wrapped in Tyvek Foil 
	- Does it happen in any orientation - Yes
	- Respect to the trigger? With respect to a reference time? With respect to WOM5!
	- Deexitation time of 1-2 ns - Cherenkov is emitted promptly, the decay time of the scintillators causes a delay 
	- This should be taken into account - cut out this effect in the analysis? 
	- Alessia sets threshold on the charge 300mV on the first one with a window of 120ns - Quite long for the PMT signals 
		- Check likelyhood analysis uses time difference between WOM signals 
		- Does not matter to the likelyhood
		- Only the plot on timing performance will be influcenced
	
	- Paul had another importent finding: Log Book of the testbeam - 
		- 26th of March - the trigger seemed to be swiched - Berlin up vs down?
		- On the day before the detector was emptied for dark count measurements - PS was off for 3 days
		- Amplitudes Switch at some point? 2-4mV differences
	- Amplitude in order of millivolts 
## Shiva
- Context: Is Working on HNL decay -
- HNL vector would point in the opposite direction then the z-axis
	-  Production vertex - decay vertex 
	- The plot shows that there is something not correctly done in concept
- Sanity check - are they parallel? 

## Anupama
- There is no way to access the coordinate system in fairship 
- Coordinate System has been shifted from the center and the origin 
- wants to talk about solving conceptual issues
- Calculations the amount of DIS in Helium $10^8$  with  a cross section 5 mbarn  possible combinatorial muon background depending on the muon shield designs with assuming that each muon passes through 50m of helium - Muons
	- given the myon one track rate 100kHz - one order of magnitude more
	- What reaches the tracker without SBT? 
- Anupama calculated $10^5$ with 0.0075 millibarn ($2.4\cdot10^4$) 
