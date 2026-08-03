---
tags:
  - status/wip
  - topic/ship/sbt
  - context/testbeam
aliases:
date:
---

`chronos - [2025-10-28~2025-11-12] #pink {Travel} Testbeam T9 CERN East Area | [[Testbeam Autumn 2025]]`

- [Google docs](https://docs.google.com/spreadsheets/d/1--IHXtxXU9OQmgVviuZBge8MqW36Gogqm0hBpD76ZjQ/edit?gid=0#gid=0)
- [Google docs Testbeam May 2025](https://docs.google.com/spreadsheets/d/1cTjGtLSBq0H9ZXTXufFUjhQVva08nDkLJAKWjn5IfYk/edit?gid=781128248#gid=781128248)
-
- order a adapter for the Schweiz 
C6 18 3 [[
]]### Things to discuss
- Alperen Dosimeter Claudio?
- Positions Cell L
- Cell A with new WOMs? yes and with new SiPMs 
- New Configuration measured  Cell L 0Ohm
- all photos in git/cern box 
## [[Improvements for the Testbeam]]
## [[Testbeam information to be saved]]
## [[Testbeam Analysis]]

- Testbeam on the spot analysis: 
	[Alessias code](https://cernbox.cern.ch/files/spaces/eos/user/a/abrignol/wavecatcher-analysis-TB25)
	- What is the light yield in the two WOMs depending on the particle position
		- old testbeam vs new testbeam
		- What version of christians code did Andres use
			- write an email to andres 
- measure with the WOMs and optical grece 3days 
- Measure with glue for 3 days 
- After 5-6 days we remove LAB and replace the two WOMs with three WOMs
- 3 days with optical grece 
- 3 days with glued WOMs 
- After that we will put the cell up right and measure Angels 

*Why does the voltage change sign when going from a higher to a lower resistor? *

With the reference cell A 
- 35 points 
- after that exchange the SiPM board 
- Andres and Tillman apply more grece 
- And exchange electronics 
### What do we need:
- Plastic Bags 
- Wasserwaage
- Q-tips 
-  langes lineal - Grid on the cells 
- gluing gun? 

To install the SiPMs
- SiPM Board
- Optical paste 
- Sponge - goes on the top of the SiPM 
- Q-tips 
- Gloves
- Paper towels 

Cell A Top SiPM Board Fell down


**Reference Detector A with optical paste**
- Clean SiPM boards and WOMs
- Put the WOM into the Vessel
    - it has to klick 
- Put the plastic ring on the WOM tube
- Apply optical paste
   - little dots first 
   - Go around another time and spread the paste
- carefully place the board on the WOM
   - the number 1 has to point up 
   - Add the sponge and than close the vessel 


**Installation Electronics**
- Set up two laptops and two WaveCatcher a 
- Two power supplies for the SiPM 
- Computer need Ethernet cables 
   - bring adapter from your room so Alessia can take hers 
- Emusic boards connected to the SiPM boards while wearing a Erdungsband 
- Which cable belongs to which channel is written in the book 
- 
For the triggers 
- check the polarity of the Channels to be Negativ for PMTs, positiv for SiPMs
- look at the trigger wavecatcher 
- You can turn and Klick to select and change stuff 
- set V_max to something reasonable (1500V )

Trigger electronic- coincidence reported by andres

There are some scratches in the SiPMs
- maybe check what channels 

#### Measurements 
- Measure the grid positions 
- Measure for certain points the rotation

##### Alessia: 
Two important measurements to do are: 
1. **center of all the WOM**s that you can reach. You can use them to check how the channels are working and you can also check if it is Saturanting the signal (it should) 
2. **Dark counts**.  You can trigger on internal trigger or something else that you like and take many events like 100k 200k. The cells have to be far from the beam. Best even if you can take them when the cells are empty. I would take them before and after changing the WOMs
- **How to decide on measurement positions**
	- Not to close to a WOM - for rotations
	- One corner
	- Test the reconstructions by choosing symmetrical positions (left/right)
- Do a small measurement in the same Position every day 
### Horst:
L-detector: Focus characterize the new detector to the same level of A- and B-detectors
=================================

- Detector  lying on its long side (2 central oriented WOM equipped)
	- [x] 3 days: 2 WOM, not glued, plastic rings, SiPM V2, eMUSIC readout  35 Grid points 
	- [x] 2.5 days: 2 WOM, glued, SiPM V3, eMUSIC
	- [x] Drain LAB and replace WOM vessel position, center and 2 outer flanges equipped with WOM
	- [ ] 2.5 days: 3 WOM, glued, SiPM V3, eMUSIC
	- [ ] Test how the cell behaves in position -30 without the Berlin trigger 
	- [ ] 3 days: 3 WOM, not glued, plastic rings, SiPM V2, EMUSIC 
Latest 08.11. (morning) rotate detector and place it on its legs.  **APPLY THE BELT BEFORE FILLING!!!**  - sonst wird der Druck der Flüssigkeit unten in der Zelle zu hoch 

- Detector standing up (2 central oriented WOM equipped)
-  **Important: Measure from the side at different angles**
- [ ] 3 days: Depending on the light yields of the above measurements, 2 or 3 WOM, not glued or glued. 


A-Detector: Focus  Scan for comparison with previous measurements
=====
 - place A-Detector on its legs
	- [x] WOM, SiPM, and EMUSIC unchanged from spring
	- [x] Compare detector performance with spring. 
	- [x] 4 days: measure from the side at different angles
              Important: Measure from the side at different angles
- 03.11.(Monday morning): rotate Detector and place it on its long side
	- [x] 3.5 days: measure grid from spring, including a few inclined measurements
- Second week: A-Detector Electronics tests
	- [ ] Test random position and 3cm away Zelle A (evl. auch Zelle L)

##### Andere Komentare
	- Zum Quality Control Set up: es wäre gut, wenn wir den ring nichtmehr verschieben müssen 
- Measure Cell A with new WOMs/ or Cell L with old WOMs
- In Cell A **NO GLUED WOMS** - do not fit with the holding ring

Am Montagabend oder Dienstagvormittag (hier muss Tim sagen wie lange er braucht) baut ihr die WOM aus Detektor A aus und ersetzt sie durch 2mm WOM. Die 2mm WOM in Detektor A werden mit denselben SiPM V2 und eMUSIC8 boards, die am Anfang in Detektor A an den entsprechenden WOM-Vessel eingebaut waren, ausgelesen. Damit untersuchen wir den Unterschied zwischen 2mm und 3mm WOM, d.h. außer den WOM muß alles andere gleich sein. Bitte darauf achten, dass die WOM und die Elektronik wieder an ihre alten Positionen kommen.  
  
Bei allen dann erfolgenden Messungen an den Detektoren A und L bitte nur solche Koordinaten wählen, die schon einmal mit 20000 events gemessen wurden. Auch jetzt wieder 20000 events aufzeichnen, d.h. wir können ca. 10 Messungen machen. Davon sollte eine in einer Ecke und eine in der Mitte sein. Die anderen würde ich so wählen, dass sie sich möglichst wenig in Ort oder Entfernung zur Mitte gleichen.
### Tim 
- Tested FastIC+ -  Electronic Configurationen mit zwei verschieden 
- Mittwoch 05.11 - im Zentrum 2h test mit den alten SiPMs
	- 20 Messungen mit 500 werten
	- Verschiedene Positionen
	- WOMs wechseln zu den neuen SiPMs
- SiPM board ohne Verstärker, ohne shaper - sehr klein, aber die echte Waveform evl. in Cell A
- Modifiziertes FastIC board - wo zwei negative Ausgänge sind 
- Alte WOMs mit alten SiPMs - FastIC+
- Freitag: 
	- Neue WOMs geklebt mit neuen SiPM boards - eMusic - Kontrol-Messungen
		- Währenddessen macht Tim Analyse
	- Neue WOMs geklebt mit neuen SiPM boards - FastIC+


**Removing everything** 
- Remove the SiPM board slowly so that you can see the imprint after 
- Take pictures 
- It’s great if everything comes out together 
- Clean after you took it out 
- remember to remove the cables that connect the channels to the internet 

