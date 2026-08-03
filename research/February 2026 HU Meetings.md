---
tags:
  - status/wip
  - topic/ship/sbt/woms
  - type/meeting/weekly
---
# 23-27.February
# Topics to discuss
## Software
### Organisational stuff
- How was your meeting last week and when will we know the outcome?
	- End of June hand in - positive or negativ next spring 
- DFG - Generic detector R&D - indirect funding 

- Is there anyone from the SBT who can take on the role of the liaison/contact for the computing?
	Be reachable, regularly attend software meetings, and make sure that information flows between SBT<->Computing.
	Furthermore, it would be good to keep track of issues related to the SBT and nudge people occasionally to make sure they get solved.
	The main responsibility is to represent the interests of the SBT in the computing WG - For now it's everyone doing anything with the software. Everyone in the computing WG is also in physics or one of the subsystems.

## Hardware
### Climate Chamber
- Santiago - min 90°C
- Vessel Crack because of the stress without tempering 
	- The Vessels should not be tempered by us
- We should discuss with Freiburg which Tubes we want to use in the next testbeam 
	- We should also run aging test on uncoated WOMs without UV light 
	- 
- Does the humidity matter for tempering? - Proba
- Homogenity besprechen
- 

# Monday Analysis Meeting  
What was discussed in the Meeting?

#### Hannes
- Light Yields of all the measurement points on the grid 
	- CellA, CallL - 3 WOMs
![[Screenshot 2026-02-23 at 13.08.24.png]]
- Had a meeting with Tim today - About asymmery 
- Horst - said its due to the tuning - SiPM arrays and E-music boards have to be matched 
![[Screenshot 2026-02-23 at 13.18.18.png]]
- Tim measured difference to be 0.4% - much smaller that 7-8 percent
	- Same e-musics than in the testbeam ? 
		- One with right configuration and the same e-music with the wrong configuration 
	- Matching must be tested more quantitativly

	
#### Shiva
- Something is wrong with the HNL production
- It would be good to understand what the motherparticles of the HNL are
	- B-Mesons - which decays of them produced the HNLs
		- Lepton + HNL
		- Not large branching ratios
- I did not understand what the two muons refer to - to the HNL decay? - Particle that were seen in the detectors
- Where does the second muon come from? - a pion can decay to a muon 
	- Should also be visible in the other files 
- Might have set something on the roh decay 
#### Eduard 
- Geney behaves weird with tau neutrinos
- If you scale up the blue plot (muon neutrinos) you really have to cut into the signal 

![[Screenshot 2026-02-23 at 12.38.35.png]]


![[Screenshot 2026-02-23 at 12.50.38.png]]
#### Jannis 
- showed his results so far


# Tuesday Hardware Meeting 
What was discussed in the Meeting?
- Quality Control
- Agingtests
- Climachamber
#### Jasmin
![[Screenshot 2026-02-24 at 08.52.03 2.png]]

# 16-20. February 2026
# Topics to discuss
## Software
## Hardware

# Monday Analysis Meeting  
What was discussed in the Meeting?
#### Shiva
- Succsessful Candidates
	- What selection cuts did you apply 
	- 
#### Hannes
- Cell A does not show the same
- The 3 WOM meausurement show the same - it is the e-musik board

#### Darja reported - Neural Networks
# Tuesday Hardware Meeting 
What was discussed in the Meeting?

# 9 - 13.Februrary
# Topics to discuss
## Hardware 
- show webinterface and program
- Contact Christian Applet About how to do the webinterface
- it would be ideal - if the rings could have individual names 
	- do you have a laser engraver
# Tuesday Hardware Meeting 
What was discussed in the Meeting?
- Für SHiP SBT suchen wir bestimmte Personen
- Kontakt Person für Safety 
	- Email von der Safety Gruppe 
- Integration Person 
	- Contact person about the integration of the SBT in to ECN3
	- Organisation 

**We should start aging tests**
- [[Climate Chamber]]] - one is used in the ITK project
- Should we buy a Climate Chamber
- Oven - that is broken 
	- How much is the repair
- How far are we on


#### Constantin 
- What do we want to do with the fixing of the tubes
- Collect what we have as material 
# Monday Analysis Meeting  
#### Hamamatsu
- might come over in April 
- Do we have topics to discuss
- Rectangular sipms? 
#### Hannes 
- Compared different positions and saw that WOM1 is underperfoming
![[Screenshot 2026-02-09 at 12.16.39.png]]
- How does the calibration work? 
	- Would it work to look at the Saturation? 
![[Screenshot 2026-02-09 at 12.20.09.png]]
![[Screenshot 2026-02-09 at 12.31.43.png]]
#### Darja
![[Screenshot 2026-02-09 at 12.44.32.png]]

# 2. - 6.  February, 2025 
# Topics to discuss
- Do we know the budget now? Than I would like to order some equipment for the lab - as we discussed at the end of last year
- Lab setup  
	- Currently working on the installation of the SiPM integrated setup and changing and improving the code/ implementing a web interface, PMT calibration 
	- implemented a dryrun setting, that works without the hardware
	- Can I use some of the extra MMCX cable we have for the CheapCal set up? 
	- The voltage supply for the sipms in cheapcal is now next to my set up, but I guess it should stay next to the CheapCal BlackBox?
	- I need a voltage supply that delivers 6-7V can I use this one from the laser setup?![[IMG_2802.jpg]]
#### Christian
- We will have to go to Hamburg to pick up the sensors 
## Software
#### Shiva
![[Screenshot 2026-02-02 at 14.01.33.png]]
#### Jasmin 
 - Signal vs Background 
 ![[Screenshot 2026-02-02 at 13.08.45.png]]
 - Answer some questions from last week  ![[Screenshot 2026-02-02 at 13.10.19.png]]
	 - we loose some signal but not much - expected
	- How does the background change if we skip the first 5m of the detector
![[Screenshot 2026-02-02 at 13.11.35.png]]
- could this be an effect of the low muon statistic?
- Setzt voraus, dass die Cuts von einander unabhängig sind
	- Multiplikation von den Cut Effizienzen 
	- Effizienz: Ein Cut auf alle Events anwenden - nachher/vorher 
#### Hannes
- shows some testbeam analysis for the center positions
- WOM II shows a lower response for glued and greased WOMs
	- Caused by vessel transparency?
	- Caused by geometry 
	- Reflectivity not the same everywhere? 
- Ratio of Sum and Individual Sum 
- Andres looked into what? 
- Used a clean as possible filter
	- Cherenkov cut is important 
 ![[Screenshot 2026-02-02 at 12.03.41.png]]
![[Screenshot 2026-02-02 at 12.09.02.png]]
## Hardware
#### Jasmin 
- Aktuelle Implementierung des Detektors ist sehr unrealistisch
	- Zu viele Zellen, viel zu viele zwischen Aluwände
#### Katharina 
- Innenwand, Außenwand und Scintillator
- 
# Monday Analysis Meeting  
What was discussed in the Meeting?
# Tuesday Hardware Meeting 
What was discussed in the Meeting?