---
tags:
  - status/wip
  - topic/ship
  - "#type/todolist"
  - topic/orga
aliases:
priority: 5/10
---
# PhD 
- **[[Prioritätenliste PHD]]** 
- [[PhD Content]]
To find papers on [[SHiP]] go to [CERN document server](https://cds.cern.ch/search?ln=de&sc=1&p=SHiP&action_search=Suchen&op1=a&m1=a&p1=&f1=&c=Articles+%26+Preprints&c=Books+%26+Proceedings&c=Presentations+%26+Talks&c=Periodicals+%26+Progress+Reports&c=Multimedia+%26+Outreach&c=International+Collaborations)

*At every meeting, I talk about what I've been doing, what I'm working on, and what the goal is.*

**It's better to keep it brief than to talk too long.** 

Ask about uncertainties, look at coordinates of the plots

*Don't take on too many things at once. Prioritize well.*

### Notes
07.08.206
- [ ] next step: - compute grouped_mean so that it can act on all the different qc.integrated data, etc. 
- [ ] Apply for Physikerinnen Tagung 
- [ ] Apply for Collaboration meeting? 
04.08.2026
Quality Control and WOMs:
- [ ] Sicherung für den PMT, Abdeckung - Dicht - 3D gedruckt
	- [x] Maik fragen
- [ ] Temperatur des Motors
	- [x] Maik fragen
- [x] Compute a temperature dependent heatup function
	- [ ] Test this function
- [ ] Neuen PCB - Temperatur stabilisierte SiPMs
	- NTC kompensiert die Temperatur 
- [ ] WOM coating lernen
	- [ ] Neuen Kunstoffreihniger bestellen
	- [ ] Neues Tolorol
	- [ ] Irgendwann neue Komponenten für Farbe (reicht noch für ca. 2L)
	- [ ] Coating speed aktuell 500mm/min - einfach geraten nicht vertifiziert
	- [ ] Untere Farbe entfernen - automatisiert - auch mit dem Dip coater?
		- [ ] Deckel mit eingebauter schale - die ebenfalls einen Deckel hat
	- [ ] Dipcoating platte designen
- [x] Matthias bitten die Widerstände von den Preamplifiern anzupassen.
- [ ] wom_quality_control repository füllen
	- [ ] Doku
	- [x] Heatup
	- [ ] Temperature Korrekturen implementieren
	- [ ] Kalibrierung des PMTs und der SiPMs
- [ ] Konfiguration SiPMs und PCBs und Preamplefier optimieren
	- [ ] Evl. Filter hinzufüge- [https://www.uqgoptics.com/wp-content/uploads/2019/08/UQG-Schott-UG1.pdf](https://www.uqgoptics.com/wp-content/uploads/2019/08/UQG-Schott-UG1.pdf) 
	- [https://www.edmundoptics.com/p/ug-1-uv-254mm-dia-colored-glass-bandpass-filter/6536/](https://www.edmundoptics.com/p/ug-1-uv-254mm-dia-colored-glass-bandpass-filter/6536/)
- [x] Table of WOMs - with what is similar and what was similar - measures tec.
- [ ] Camera in the setup 
- [ ] Monitor High Voltage on PMT
	- [ ] Messungen mit verschiedenener HV PMT +- 10V 
- [ ] Protection for the high voltage supply 
- [x] Maik - dichte abdeckung für den PMT?
- [ ] Heiko über Matthias Erfahrung mit [[FPGA chips]] berichten
- [ ]  Webinterface
- [ ] Bei Bestellung SMA stecker mitbestellen - 
	- [https://www.reichelt.de/de/de/shop/produkt/sma-stecker_rg174_316_gerade_crimp-157321](https://www.reichelt.de/de/de/shop/produkt/sma-stecker_rg174_316_gerade_crimp-157321)  
	- [https://www.reichelt.de/de/de/shop/produkt/adapter_sma-kupplung_auf_sma-kupplung-235616](https://www.reichelt.de/de/de/shop/produkt/adapter_sma-kupplung_auf_sma-kupplung-235616)

ALPs
- [ ] Paper lesen von Matei 
	- [ ] [Detector performance at SHiP for cascade-produced long-lived particles](https://arxiv.org/pdf/2606.07743)
		- [x] 1 mal 
		- [ ] 2 mal
	- [ ] [Dark fluxes from electromagnetic cascades](https://arxiv.org/pdf/2401.06843)
		- [ ]  1 mal
		- [ ] 2 mal
- [ ] Phlex
		- [ ] [Talks on Phlex](https://indico.cern.ch/event/1714340/contributions/7211279/attachments/3322331/5948592/Phlex-SHiP-2026-07-31.pdf)
		- [ ] [github](https://github.com/Framework-R-D/phlex/releases#release-v0.3.2)
- [ ] SHiPSoft - [Onboarding](https://shipsoft.github.io/Documentation/first-steps/)
	- [ ] [github](https://github.com/ShipSoft)
	- [ ] [Wie SBT implementiert ist](https://github.com/ShipSoft/Geometry/tree/main/subsystems/DecayVolume)
Orga:
- [ ] Physikerinnen Tagung 2026
- [ ] Abrechnung Juli 2026

18.06.2026
Orga:
- [x] Ordner sortieren 
- [ ] Zeitplanung optimieren - nicht alles gleichzeitigmachen 
	- [ ] Dokumentation mit einplanen
- [ ] Write a Documentation in Obsidian ?


- [ ] Neuen Computer einrichten
	- [ ] Neuer Computer Zotero Integration, Milena, Jule Tips
- [ ] Start to have a longterm time plan 
- [ ] Safe stuff from notability and delete it - cancel the abbo
- [ ] Work into Claude [[Tips for agentic coding 2026]] - get paid version?

Other stuff:
- [ ] Sign up for a Spanish class with Jon 
- [ ] Improv theater with camilo
 - [ ] lernen wie man CAD designs vernünftig macht - PCB
 - [ ] Die Prasentation fur Beschleuniger nochmal bearbeiten?
- [ ] Wenn ich Quality Control SetUp fertig habe
	- Fairship - Signal Kanal analyse?
		- Oliver - swiching to a different program
		- Beam is 1.2 s 
		- Darja - bisherige Neutrino Untergrund Abschätzung völlig unbefriedigend 
			- Für den SBT Ist die konservative Abschätzung völlig unbefriedigend 
			- Das was Antonio jetzt neu macht, auch für das Zerfallsvolumen
		- Jasmin soll die Hitrate, die der SBT sieht mit der neuen production machen.
			- Hoffung dass die Hitraten runter gehen.
			- region dependent thresholds 
	- Two different studies - muon halo 
	- Magnatic field Partially swished of 
		- SBT in Fairship völlig unrealistisch - aber das sollten wir nicht in FairShiP noch korregieren
		- Digitization im neuen Framework 
			- Anders als in Fairship 
		- Untersuchung mit einem GAP auf der Seite des SBTs - da wo die Muonen den SBT hitten würden 
			- Support Strukur in FairShiP
			- Untergrunderzeugung, den ich nicht taggen kann 
				- Kleiner Detektor an der Stelle? 
			- Extrapolation Veto 
			- Wenn einer der Tracks in die Umgebung der Träger zeigt ausschliesen
			- Wir fragen nur nach dem Vertex kandidat 
				- nicht nach dem anderen Tracks

	- Monte Carlo Simulationen?
	- Funding 
		- SND project - Geld
		- BFD Antrag mit Freiburg und Mainz - ist im Entscheidungsprozess - könnten wir im Mai wissen
		- Stipendien in Berlin finden ist extrem schwierig 
			- Hannes vielleicht? 
			- Nicht attraktiv - eigentlich ein Schlag ins Gesicht 50% und man muss sich noch selbst versichern 
		- Förderung in der nächsten Periode


- [ ] Do [git lab tutorial](https://docs.gitlab.com/tutorials/)
- [ ] Copy data to new directory 
	- [ ] Simulation data


### **Communication**
If you give a talk thank for the invertation and if you ask questions to a talk thank for the talk first!
- [ ] Klima Kurs mit Jugendlichen
- [ ] Neue Video Reihe mit Erklärvideos? -[[Heikos Video Ideen]]
- [x] Könnten wir eine Simulation in Fusion machen? - Teilchen durch SHiP folgen - Pablo Santos Diaz
- [x] 28.05 Masterclass mit Heiko reden

#### Possible participations: 
- Humboldt Graduate School 
	- [booking platform](https://hu.opencampus.com/de/alle-workshops)
- **[Writing Wednesdays: Monthly space for academic writing](https://fakultaeten.hu-berlin.de/en/mnf/wisskar/center-for-career-development-adlershof/writing-wednesdays)**
	- Wednesdays
- ##### **[S](https://fakultaeten.hu-berlin.de/en/mnf/wisskar/center-for-career-development-adlershof/scicomm-lab)[cience Communication and Generative AI: How to gain digital visibility and use GenAI responsibly](https://fakultaeten.hu-berlin.de/en/mnf/wisskar/center-for-career-development-adlershof/scicomm-lab)**
	- 22.April
- [**Diversity Conference Adlershof**](https://sweapevent.com/b?p=diversityconferenceadlershof) [](https://sweapevent.com/b?p=diversityconferenceadlershof)_powered by differences_. Under this motto, the next Diversity Conference will take place in Adlershof in May. The program is available online, and registration is now open.
	- 7 May 2026 | Adlershof  
###  **Orga**
Hier werden Organisatorische ToDos festgehalten
- [[SHiP Collaboration Meetings]]
- #### Young Scientist in SHiP
	- [x] Infrastructure for Problems (Sexism, harassment)
### SHiP Outreach
- [x] SHiP outreach coordinator? 
- Science Slam 
- International Confrences
- Have one design for SHiP talks
- #### CERN
- #### Schools
	- [x] Talk to Heiko about the schools
	- [ ] 17th/18th Pisa Meeting on Advanced Detectors? 
	- [ ] [[DESY terascale statistics]] - [indico](https://indico.desy.de/event/51468/)
	- [ ] **EDIT Instrumentation Schools 2027** - [indico](https://indico.cern.ch/event/1472419/overview)
		- [[EDIT school 2026]] - [[Non weekly meetings schedule and zoom links]]
	- [ ] [[D.TECT school]]? [Indico](https://indico.desy.de/event/51237/) in parallel with the collaboration meeting 
	- [ ] SLACK? - Califonia
	- [ ] ICHEP — International Conference on High Energy Physics? 
	- [ ] Python Course 
	- [ ] [CERN Computing School](https://indico.cern.ch/event/1646431/overview)
	- [x] [[Beam Telescopes and Test Beams Workshop|BTTB workshop]] [Indico](https://indico.cern.ch/event/1594436/)?  
	- [ ] [[Wisskomm Kolleg Toepfer Stiftung]] - Bewerbung ab Dezember
`chronos - [2026-03-16~2026-03-20] {Travel} DPG-Frühjahrstagung`

### **Labor und Analyse**
- #### [[Lab To Dos]]
- Alles als PDF speichern
- [ ] I also still need to write the calibration for the PMT
- [ ] Constellation anschauen
- [ ] Webinterface QC
- [ ] Christians calibration methode anschauen
	- [ ] Umsetzen mit [wavecatcher methoden](https://github.com/cscharf-hub/wavecatcher-analysis/blob/master/examples/cosmics-fit.ipynb), [PMT funktion](https://mattermost.web.cern.ch/ship/pl/8e81asgustnmxb5fp8n5zj9gkw)?

- [ ] Holdingrings measurements and analysis 
- [ ] Homogenity of the PMT 

### **Strukturieren**
- [ ] Masterarbeit in [[Obsidian üben|Obsidian]] einarbeiten
	- [ ] Webclipper
- [ ] Projects Time Schedule find best way to note this down and  
- [ ] Slides für die Meetings erstellen - seiten zahl mit der gesamt zahl - Layout
	- [ ] Style sheets mpl style  - python, Grid nach innen
- [ ] Look into base to get overview \
- [ ] Dataview anschauen
- [x] Community erweiterung "fit"
- [ ] Base anschauen 
- [x] Excalidraw plug-in to draw with Apple Pencil 
### **Programmieren**
-
- [x] [Testbeam Analysis](https://gitlab.cern.ch/ship/ship-sbt/testbeam-analysis) with Hannes
	- [ ] Does a change in position of 3cm make a difference
	- Use Fairhurst Color scheme
- [ ] [[ROOT@CERN|ROOT]] besser verstehen
- [ ] FairShip lernen
	- [ ]  How to FairShip in [[Obsidian üben|Obsidian]]
	- [ ] Documentation Doxygen - FairShip https://shipsoft.github.io/FairShip/classvetoPoint.html
- [ ] Git integration https://gitlab.cern.ch/groups/ship/ship-sbt-/wikis/general-how-tos
	- [ ] Git tutorial?
	- [ ] Take the control over the git from Anupama?
- [ ] Get used to bash 
	- [ ] Exercise! Have a go playing around with this script to get some practise! Idea: What does $0 do
	- [ ] What happens if you run: $ bash testScript.sh
	- [ ] How about: $ bash testScript.sh something
	- [ ] Try: $ bash testScript.sh something else
	- [ ] Maybe: $ bash testScript.sh “something else”
### Lehre

### **Einlesen**
- [ ] Paper!!!!
	- [x] SHiP - understand how they will achieve 0 background 
- [ ] Anupamas Dissertation lesen 
- [ ] Physics Case Paper
- [ ] Olivers Thesis lesen
- [ ] Fairhurst thesis lesen
- [ ] Alessias Thesis lesen
- [ ] Read Matei's thesis
- [ ] Hebeckers Arbeiten vollständig lesen
- [ ] Ice Cube Ergebnisse lesen  - Qulaity Contol
	- [ ] Yuriy
	- [ ] John Rack-Helleis
	- [ ] Philipp Jeremiah Kern
- [ ] Hannes Bachelorarbeit 
- [ ] Do the "[[Good Research Practice for Doctoral Researchers]]" - course https://isis.tu-berlin.de/course/view.php?id=41545
	- [x] Chapter 1
	- [ ] Chapter 2
	- [ ] Chapter 3
	- [ ] Chapter 4
	- [ ] Chapter 5
	- [ ] Chapter 6 
- [ ] Fehlerfortpflanzung in [[Obsidian üben|Obsidian]] - routinierter werden
- [ ] Read Background Estimation from Cosmic Air Shower Muons in the SHiP Detector
	- [ ] For the cosmic background generator





