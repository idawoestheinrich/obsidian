```chronos
@ [2024-05~2026-03] #orange {Quality Control} Quality Control Set Up Construction 
- [2026-01-12~2026-01-16] #orange {Quality Control} SiPM board finishing
- [2026-01-13~2026-01-31] #orange {Quality Control} QC diagnostics and improvement 
```
Notes: Maybe the inner measurements don't show as nice results as the outer measurement, because the system is still moving while they are performed


Every second waveform is empty - does the trigger not work? and why does my if .. statement does not prevent that?

How to use the reference measurement? - ask in the [[September 2025 HU Meetings]] on Monday
Why is the standard deviation sometimes for one point factor ~3 higher?
- Check that 
## Programming 

- [x] Write a code that takes the waveforms and calculates the integral and than compares it to the integrated safes
- [ ] Connect Lab computer to git 
- [x] Measure in one position until 20 waveforms are measured
- [x] Include standard deviation of the [[Light yield]] into the automated plots
- [x] Write a code that can read and plot the bin flies
- [x] Better intergration method 
	- right now simson- but to complicated just add up the bars
	- [x] integration Riemann sum
	- [x] test the method
- [ ] Improve efficiency of the code 
- [ ] Web interface
	- [ ] What must the Web interface include
	- [ ] What could the Webinterface include
- [x] Write code to perform transmission measurement
- [ ] Choose an integral window relative to the maximum of the peak
- [x] Include the Heatmap production into the code - 
	- [x] Start measurement - get plot
	- [x] Start measurement - safe waveforms
	- [x] testen, ob code das tut, was er soll
- [ ] Am besten sollten im WebInterface Bespiel Waveforms zu sehen sein, während die Messung läuft, damit kontrolliert werden kann, ob alles klappt
- [x] Calibrate Coordinate system
- [x] How to safe the data files: 400 positions x 30 waveforms x 2048 datenpunkte
- [ ] Make it possible to display and safe parts of a measurement 
- [x] Add threshold to integration
## Tests
Perform reference measurments - Statistiscs_one_position before and after each measurement
- [x] test [[Optical Coupling]]
	- [x] Cling foil 
	- [x] nothing 
	- [x] Glycerin
- [x] Holding structure - will I be able to remove the structure from the [[PMT]] after all? 
	- [x] try with optical gel
		- [x] is it tight?
	- [x] Not to thin not to thick? 
	- [x] How long does the Glycerin stay in the holding structure
		- Started first "measurement" recording the behavior of the [[Optical Coupling]] on 20250813 at 4pm
		- [x] Record the same with aluminium ring and [[WOM]] tube inserted
- [ ] Test 395nm [[LED]]
- [ ] Test Stability of the current LED and PMT over time with one pulse per second at the current pulse length 
- [x] Test inside vs outside LED
- [x] Perform a measurment without WOM
- [x] Perform a transmission measurement again : 
	- Findings: 
		- Value measured in the sensors depends on rotation
		- No full rotation was Performed - only 144 Degrees
- [ ] Temperature dependence PMT/SIPMs/LED?
- [ ] Set up a new transmission measurement, after the problem has been fixed
	- [ ]  Perform another efficiency test - than transmission than the same
- [x] Measure several times with one Tube 
	- [x] With thin film of [[Glycerol]] (4Vpp)
	- [x] with no [[Optical Coupling]] 
	- [x] glycerol to check reproducebility 
- [ ] What is a *good* WOM tube? 
- [ ] **Measurements with the Holdingrings** 
	 - [[Luis Bachelorarbeit- Holdingring measurements|Luis Bachelorarbeit]]
- [x] Measure WOMs with the rings
	- [x] 5 different materials
 ## Hardware
- [ ] preamplifiers
	- [x] get back to Martin
	- [x] talk to thomas again 
- [ ] Distance between LEDs needs to be increased -
	- [x] contact Mike
- [ ] Bigger outer circle to hold WOM with holding structure
	- [x] contact Mike
	- [ ] Does it make sense to place the holdingstrukure in the Glycerol? Will we be able to remove the Glycerol from the ring and from the spaces between the WOM and the Ring?
- [x] Make sure that the cables don't hit the WOM while moving
- [x] There is some electrical issue with the rotation motor
## To be purchased
- [x] pipettes
	- ask Frau Farnauer for an idea
- [ ] something to clean and dry the WOMs and other devices used with glycerin

