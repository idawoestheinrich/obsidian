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

## Wednesday 20260520
- Do we need one or two WOMs?
- Do we have loss?
- Documents? CAD files, pdfs, etc. Die CAD 
	- EDMS - wird zur Speicherung von CAD files genutzt


# Wednesday 20260512
- **WE NEED A LIST OF CONFIGURATIONS THAT WE WANT TO IMPLEMENT**
	- Could a container with 6 cells be the smallest unit to enable? 



# Wednesday 20260505
#### Tim 
- WaveCatcher mit Glasfaser auszulesen - erhöht
- Analogen FastIC sind wir bei 300ps - 
	- Johannes Wenks Laser Setup - mit dem Laser eine bessere Performance 
	- Zeitverschmierung durch den WOM
	- 
#### Hannes
- Testbeam results - no saturation measurement in November![[Screenshot 2026-05-06 at 08.03.47.png]]
- Wenn das muon nur durch das Plastic durchgeht bekommen wir ganz wenig Szintillationslicht 
	- Cherenkov licht
	![[Screenshot 2026-05-06 at 08.14.56.png]]
	
	![[Screenshot 2026-05-06 at 08.16.20.png]]
	- Wir haben möglicherweise einen leichten bias in der Beam - position 
		- Wir können wir das testen?
	- WOMA1 - bei 0 Grad![[Screenshot 2026-05-06 at 08.22.39.png]]
		- Haben wir einen systematischen Fehler in der Rotation?
		- Simulation? Strahlprofil wäre gut
		- 800mVxns beim ersten Peak
		- Aus dem 2. WOM können wir schließen, was passiert
	- WOMA2 bei 180 Grad![[Screenshot 2026-05-06 at 08.25.26.png]]
	- Der unterste Peak dürfte nur ganz wenige Darkcounts enthalten 
	- Wir können es nicht verstehen, ohne Simulationen
- Vergleiche irgendeine Position für 0 und 180 Grad
# Wednesday 20260429
#### Matei 
- How can we check if the material is correct in root? 
	- Jasmin is on it

#### Jasmin
- Computing workshop: 
- Control what we do with the LED
	- What would be monitor the LEDs - length of the signal? It should probably be slow control 
	- 
#### Shiva
- how many good candidates do we have at a certain z-position
![[Screenshot 2026-04-29 at 08.05.12.png]]
- the condition is that the vertex is in the fiduatial volume
# Wednesday 20260408
#### Jasmin 
![[Screenshot 2026-04-08 at 08.03.27.png]]
![[Screenshot 2026-04-08 at 08.05.53.png]]
# Wednesday 20260401
- Wir brauchen mehr 3mm WOMs 
- 2mm WOMs mit einem kleineren Äußeren Radius?
	- Electronics mit einem größeren Durchmesser
	- No need to adjust the machanics
- We need the Quality Controll Compairsion 
- New 3mm WOM tubes
- Should we temper after DipCoating 
#### Jasmin 
- Kyrill and Anne-Marie
- Can Matei give feedback? 
#### Tilman ![[Screenshot 2026-04-01 at 08.29.50.png]]
# Wednesday 20260311
### Hannes 
 - Increased light yield with longer operation of the Cell
 - Ratio of the center/corner changes
![[Screenshot 2026-03-11 at 08.50.20.png]]
![[Screenshot 2026-03-11 at 08.57.49.png]]
![[Screenshot 2026-03-11 at 08.58.33.png]]

#### Tim

#### Jasmin 
- two events
- efficiency of a mass cut?
- Distance between the UBT and the entrance of the decay vessel? 
	- It is 19m/15m in the simulation
#### Darja 
- GNN is trained on timing, x,y,z position of the cells, and energy deposition and the vertex x-y-z position
	- any other features that could be used to train? - no more features
- Is the network really trained on the most dangerous background
	- Not well trained on excitation of an atom? 
	- 
# Wednesday 20260304
### Wer hält den Vortrag beim SHiP collaboration meetings?

#### Tim : 
- WOM 1/2 from our Testbeam
- Johannes said 10min war 
- Charge ratio
![[Screenshot 2026-03-04 at 08.07.07.png]]

![[Screenshot 2026-03-04 at 08.10.12.png]]

![[Screenshot 2026-03-04 at 08.11.35 1.png]]
![[Screenshot 2026-03-04 at 08.13.56.png]]

#### Tilman 
- fit the square root of the 
![[Screenshot 2026-03-04 at 08.28.20.png]]
- not including shift of the emusic
- difference of 0.1V on the overvoltage - leads to a difference of 2 percent 
	- Gain dependence?
	- Ruffly linear - but depending on the slope
- DC offset 100mV would be 30 bit times 2 % 
![[Screenshot 2026-03-04 at 08.36.05.png]]

# Wednesday 20260225
#### Jasmin 
- f stands for factorisation 
- Compare percentes to see if the cuts are independent of eachother
	- If they are independent we can estimate how much background is left for a bigger sample
-  Basic cuts do not include UBT - looks like the UBT does not influence the Events in Helium 
	- UBT veto
- IP cuts are not very efficient 
- Background from the SBT itself? 
#### Shiva
- Calorimeter - Splitcal is the E-Cal 
- Use up to date implementation 
- B sub C is interesting because it has a much higher mass as the other 
- 27 GeV center of mass energy 
	- We do not know the production rate 
	- Normal B-Meson 5.3GeV

#### Tim 
- log book and data
- Table - Apperently SiPM and e-music pairs were not matched to the boxes 
	- Operation with two WOMs, and 3 WOMs when there were greased
	- Test with different configurations
	- test position 2 vs 4
	![[Screenshot 2026-02-25 at 08.43.44 1.png]]
![[Screenshot 2026-02-25 at 08.52.25.png]]
![[Screenshot 2026-02-25 at 08.52.51.png]]
![[Screenshot 2026-02-25 at 08.53.17.png]]
![[Screenshot 2026-02-25 at 08.53.50.png]]
# Wednesday 20260211
- it would be ideal - if the rings could have individual names 
	- do you have a laser engraver
- Should we buy a Climate Chamber

#### Hannes showed the same results again
- should plot the ratio 

# Wednesday 20260204

#### We have to provide a Slide for SBT going to TDR till Friday
- Detector works - testbeam
- Readout electronics
- Eurolabs is importent
- Ingeniering - Integration
	- Installing Bottompart
	- Horst assumes the side walls will be installed first

#### Darja 
- should do a presentation in the Background taskforce
- implement the scimming 
- write out the candidates that are dangerous

#### Jasmin 
- implemented the cut on the first 5m yesterday 

# Wednesday 20260128

`chronos >[2026-03-16T16:00] {Meeting} SHiP infrastructure document update : SBT |  [[SHiP SBT infrastructure document update]]`
[[SHiP SBT infrastructure document update]]
I am still working on the QC setup 
-  loose connection with the inner LED
- Two weeks ago I had to fix a short circuit in the setup
	- SiPM Boards are ready to be operated now. 
	- I hope that I will finish the new setup next week 

### Hannes
- Reflectivity 
	- Agreeing with Old Measurments
	- 2 WOMs with a larger distance to the corner 
	- Ratio between Corner Measurement and Monte Carlo 
### Tilman
- L Cell fokus of Tilman
- Mechanical Calulations
- A-Cell spring - in the Center they agree in the corner they doen't
- First on the L-Detector

### Jasmin 
- Z- dependent IP cut leads to a almost a reduction of a factor of 2 
- Next step: Larger distance cut to the Wall 
- SBT does not cover the full decay volume
- Coverage of the Volume by a veto detector - is simulated by some person (guliamo)
	- It takes out of our hands how to motivate the detector
 
### Alessia
- no new results
- Comparison of the light yield in the Monte Carlo digitized compared to the data
	- Digitization is not the same as in real life - transferfunction of the electronics i
- We have to change some sentences in the Paper draft
### Andrii
- General difficulties, + not much time