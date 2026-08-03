---
tags:
  - status/wip
  - topic/ship/sbt/woms
  - type/meeting/weekly
theme: simple
height: 566
margin: 0
maxScale: 45
aliases:
  - SHiP SBT
---
Upload your stuff to [indico](https://indico.cern.ch/e/1570742)!! 
# 20251218
### Physics analysis coordinator (eher jemand mit einer festen Stelle? )
- Walter bunivento
- Maxim
- Costas
#### Tykhon 
- Email contact with Horst
## Hardware news?
#### Tim Molzberger
- Time resolution of the last testbeam 
- different modi 
- Different setting of the preamplifier in red 
![[Screenshot 2025-12-18 at 14.40.53.png]]
- Effects visible
- Analog similar to the e-music
- Energy measurement measures the amplitude encoded as the width as a digital signal 
- Two digital pulses that are ToT
- Why has green such a small standard deviation at 150
- When you do the Analog - 20% of the amplitude
- 100mV for ToT and Energy Meas. 
### Software news:
- [[Oscillations in the waveforms]]
	- Caluculate the difference to the trigger time and look at this again 
# 20251211
### Testbeam
-  Is one week enough for us? 
 - Two Testbeam request from SHiP
 - Can we merch the two requests from Calorimeters
- [Indico](https://indico.cern.ch/event/1584075/)

# 20251204
#### Tykhon 
- Misunderstood something
- Teaching term
- Can connect to the set up in freiburg

### Santiago
- Filling the Cell 
- At TU Berlin they are performing longterm tests - with plastic holding rings
	- They did not survive the 60 degrees
- Due to pressure and deformation 
	- Bubbles
	- 5mm detector L without belt
	- We had some bubbles in the corner 
- In the real detector such a cell would have much thicker walls
- Connect the Cell Walls on the inside with an 8mm thick *pulished* "string" 
	- Check in Simulations if we can reduce the Material budget 
	- How many photons do we loose in that case?
![[Screenshot 2025-12-04 at 14.53.56.png]]


#### Tilman
- Designed a Transportbox 
- It makes sense to remove the WOMs from the coating structure and put them in a more space efficient box
- Electronics
- Foam from below - should not put any pressure on the WOM
- The ring needs to be moved up in Berlin 
- The position of the ring is not super important
![[Screenshot 2025-12-04 at 15.09.32.png]]
- Slove the QC optical coupling problem?
- Expensive to build such a box
	- Produce only the lid and fix it to a commercial box
- We will need to have an additional Foam around this to reduce the pressure on the  box 
# 20251113
#### Testbeam 
- 4 Million events with many different positions
- Eurolabs - submit data sheet 
- Report 
	- We have listed what we want to do 
	- Horst will take a look at it 
- Annika the expert- Heiko gets paperwork 
- 6 am stopped data taking 
	- cleared the area by 9:15
- Small wheel did not count correctly 
- 68 cm movement range - the floor is uneven as well 
- Measurement devise which gives the degrees

- Check if Berlin files are uploaded and create folder for logbook 
- Upload pictures
- Scan if all data is uploaded

#### Testbeam analysis
 - Compare
	 - optical gel vs glue
	 - 3mm vs 2mm tubes
	 - Paul has looked into the timing - effective drift speed 
	- Compare 2 vs 3 WOM configuration 

#### Collaboration Meeting 
- Never reported in detail on the alanod - Andres? 
- Report on testbeam
	- Detector A is stable over the last year
	- Light yield for the L cell for 3 and 3 WOMs 
		- Spectra - larger cell and two WOMs one could operate
		- Light Yield itsself is large enoigh - far corner
- What was tested with the electronics - some results - Tim
	- Analog read out and digital read out 
	- 3 measurements in one position with different configurations 
	- quite precise energy measurement 
- Progress on the QC example measurements

**NOT THIS:** 
-  Neutrino and DIS studies?
 - Anne Sophie last time - do not repeat 
- Slide on what are our Goals for the next testbeam 
	- Avoid descussion in the collaboration meeting
	- electronics 
	- unpurified LAB + PPO 
#### Heiko 
**Long meeting with Anupama** 
	- Helium only and SBT only 
	- Numbers partly off by an order of magnitute
	- Normalize to the number of neutrinos per spill 
	- And the total is correct 
	- You have to know how many neutrinos are placed in that part 
	- For the SBT - we have to take into account the room angle 10% of the Neutrinos completely 
	- SBT not only liquid scintillator 
	- Anupama wants to test weather what we have now is really correct
	- For Muon DIS this issue is smaller 
	- Can we fix this on a small time skale 
	- It might make sense not to present this at the collaboration meeting 



### Shiva
- 


### Annika
**Equipment:** We cannot buy 250000 liter tank ? 6000 more likely 


# DSBT 
#### Tykhon Kurkin


# 20251106
#### Tykhon Kurkin
- Programming the read out 
- AuroraTxModule - Understanding the program
- Serializer module![[Screenshot 2025-11-06 at 14.36.16.png]]
- Timing - fifo is full - check for almost full
### Tim on FastIC
- Very big ampitude compared to the Emusic
- Look at the Noiselevel 

## Fairhurst
![[Screenshot 2025-11-06 at 15.12.12.png]]
### Alessia

Shows results from TB 4Cells

# 20251016

#### Things to show 
- [[LED emittance over time]]
- [[Testbeam Autumn 2025 WOM Measurements]]
- WOMs have been send - UPS Trackingnummer
	- [**1Z75A0396869465521**](https://www.ups.com/track?loc=en_DE&requester=ST/trackdetails)
### Santiago Ochoa
- Testbeam - detector 160mm long, 5mm thickness of the Walls - security 
- Cleaning 
	- At the moment only Helium 
	- Polished and covered by foil until the welding
	- Welding dust
	- Closer picture of the welding seems
- Which company do we want? 
- Constant
- Detector A - has the same "scratches" - and we were happy with that 
- The current detector has scratches in one direction 
	- the must be a prefered direction 
	- In the raw material we also have a prefered direction
### Tykon Kurkin Aurora link progress report
- no deserializer needed

### Tilman Rock optical coupling between the WOM and the SiPM array
- Build a little a machine 
- Showed real time
- We want to evacuate - how to do that? 
- WOM tubes are never perfect
- *Regarding the diameter of the WOM - the smaller inner diameter of the rings never fitted for the testbeam WOMs*
- The SiPMs are also placed by hand with uncertainties
- Glue dummies? How can we have a good dummy for the sipm array
- How do we determine the right amount of glue

### Tim Molzberger
- Status report 
- Labortory from Johannes Spenk with a Laser in a Dark box in a vacuum vessel and the read out on the outside
- Tries with the new SiPMs and FastIC+board, 40.3pc LAser
- Figuring out the Signal shape 
- Signal length is longer than the one from the Emusic board
	- We send this through a shaper and this shortens the signal 
	- Transaperance amplifier - emanuals thesis

### Testbeam
- LAB has arrived at CERN
- next Testbeam 8 - 22. July 2025
- Safety inspection between 3 and 5 in the afternoon - taking data during the night 
# 20251002
## Testbeam
- prepare the grid for the cells cell A and cell L
	- Who does that Andres, Fairhurst, Alessia
	- Spread sheet send by Fairhurst 
- Insert a new WOM reference measurements
- with the e-music board

## Fairhurst
- Mean Detetcted Photons
- Attenuation length at 380nm 
![[Screenshot 2025-10-02 at 14.04.02.png]]
- Simulation of the Aluminium cell (A)
- Raw LAB, not Raw LAB+PPO
	- Horst has seen plots from Annika on the attenuation length (we need to purify) - [indico](https://indico.cern.ch/event/1565821/contributions/6595477/attachments/3098119/5489571/2025-07-03_ship_ls-sbt-retreat.pdf) page 11.
	![[Screenshot 2025-10-02 at 14.09.13.png]]
	- It could be that there is an optimum in light yield 
- Same plot for the corner position?
- Person power - looking in this kind of simulation 
	- Can't you run in the beginning without purifying 
	- Could we start with repurifing 
# TU Berlin 
- Application for Funding for the injection molding for the PMMA vessel
- Finalize the design 
	- we stay with 20cm thickness
- UV transparentcy? 
	- Molded plastic from china 
- The end of the WOMs could be rounded up so that it is really round 
- We should send uncoated tubes
	- Rounded
	- Tempered
	- Tests in quality controll set up
- Aging test with a well defined procedure
	- 340 UV light at the same time with temperature (well defined)
	- For the PMMA 
	- For the WOM tubes
		- Uncoated WOM tube
		- Coated WOM tubes
		- Photobleaching 
	- More than one tube
- Measure the coating thickness 
	- Thickness of the plate 
- Ida: Get back to Dirk to send to him the coated WOM
	- How about the photobleaching 
	- Which ring 
- The ring is better than the WOM
- We need to have more companies to apply to wirtschafts ministerium 
## Tykhon Kurkin 
- Aurora link progress report 
- AuroraTxMock Usage


# 20250821
## Santiago  ![[Screenshot 2025-08-21 at 09.50.11.png]]
## Discussed Ring Structure

# August 28th, 2025
- Time schedule must be set - when will we finalize the detector?
- Collaboration Meeting Monday 3pm Parallel Sessions
- Meetings starting from 2:30?
	- Last days of the week are dedicated to traveling 
### Hardware:
 - Large Aluminium Cell has been ordered - Second week of Oktober (Week 41)
 - Late due to delivery times and vacation 
 - Horst and Santiago will do the tests and bring the box to Freiburg (9th, 10th)
	 - Leakage 
	 - Latest on the 14th October
	 - PMMA vessel will be installed in Chemnitz
	 - Shipping by a Company to CERN
	 - Material for new PMMA vessels also ordered
### Electronics 
- Fastic plus PCB 
- C-Max board that collects the information from the Fastics Boards
	- Transition board in production
- Assembly of the new SiPM boards will start next Monday 1st September 2025
- After that Fastic plus PCB 
- Barcelona group:  Chips where supposed to be shipped before the summer vacation
## Tykhon Kurkin
- Ran into problems with the simulation: What simulation?

## Efficiency of the WOM tube
- Mainz Ice Cube people 
	- Efficiency over distance 
	- We should not have an absorber at the end - we can not compare direction 
	- Bastian Keßler did it last 
	- One single measurement with an absorber at the end
# Topics to discuss
- How will we do the optical coupling? 
	- Some gel? Will that be easier

# Quality Control:
- Measure several times with one Tube with no optical coupling and glycerol to check reproducebility 
- Standard deviation of the Light yield 
- Remove the top and use a different color coating
- In the future compare to SiPM
- Write to the company with the silicon pads
- Measurements first - good WOM tubes
	- Three WOM tubes for the last detector
# Summary Slides 
- Main activities - Summary slides that are self explaining for the Collaboration Meeting 
## Different Rings (Luis Thesis):
- Light Yield Comparison 
- Steel is basically the same as Aluminum 
- Steal 3.2mm pol - Confirming these would be great 
	- Touching - we could make the inner ring non circular
	- Make the surface less flat - having a wavy inner circle 
		- like a Rohrzange but not as extreme
- Confirm that the los is only 3-4% 
- Confirm these Measurements 
- Measure in different positions of the ring (within 1 cm)
	- Does it have a large effect?
## Testbeam
- Originally new WOMs and SiPMs glued to the WOMs
- The transport box must take into account, that the SiPM Boards need to be transported to CERN glued to the WOM
---
<!-- slide template="[[tpl-con-2-1-box]]" -->

::: title
### **WOM Quality Control**
:::

::: left
![[Screenshot 2025-08-25 at 13.53.40.png|630]]
:::

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right
### **Detector response measurment**
- **Pulsed** **UV** **LED** lighting the WOM wall from the side
- WOM optically coupled to **Photomultiplier tube (PMT)** to detect **emitted photons** transported to the end of the WOM
	- Need for reproducible, easy to apply and remove optical coupling
	- Options: Glycerol, silicon pads

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->

--
<!-- slide template="[[tpl-con-2-1-box]]" -->

::: title
### **LED Movement**
:::

::: left
![[Screenshot 2025-08-25 at 14.10.45.png|600]]
:::

::: right
![[Screenshot 2025-08-25 at 14.35.42.png|200]]
:::

--
<!-- slide template="[[tpl-con-1-1-box]]" -->
::: title
### **Measurement without WOM** 
:::

::: left
![[Pasted image 20250825151403.png]]
:::



::: right
![[Pasted image 20250825151356.png]]

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->

::: source
:::

--
<!-- slide template="[[tpl-con-1-1-box]]" -->
::: title
### **Uncoated WOM no coupling**
:::

::: left
![[Pasted image 20250825150823.png]]
:::



::: right
![[Pasted image 20250825150829.png]]

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->
::: source
:::

--
<!-- slide template="[[tpl-con-1-1-box]]" -->
::: title
### **Thin-coated WOM no optical coupling**
:::

::: left
![[Pasted image 20250825150319.png]]
:::

::: right
![[Pasted image 20250825150014.png]]

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->


--
<!-- slide template="[[tpl-con-1-1-box]]" -->
::: title
### **Thin-coated WOM optical coupling with Glycerol**
:::

::: left
![[Pasted image 20250825150101.png]]
:::

::: right
![[Pasted image 20250825150049.png]]

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->

::: source
:::



---
