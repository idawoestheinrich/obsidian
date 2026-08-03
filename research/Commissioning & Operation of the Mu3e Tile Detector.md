Erik Steinkamp
- indico [Abstract](https://indico.physik.uni-siegen.de/event/592/contributions/1511/attachments/613/1483/Erik_Steinkamp_Summary.pdf)
## Motivation : 
-  find lepton flavor violating decay µ+ →e+e−e+
- No SM background signal (purely leptonic decay)
- Intensitive muon decay 
- Vertex and outer pixel 
- Scintillating fibers ($\sigma < 500ps$)
- Scintillating tiles  (5x5x5mm) coupled to SiPMs
### Beamtime June 2025
- 3 of 14 modules installed and commissoned
- First beamtime with all subdetectors in magnet
- First clusters and coincidences were observed
	- Between different detector systems
#### Offline Calibration - a framework
- Store calibration factors in central database
- Timewalk correction (Also in Masterthesis)
- Time alignment
#### Timewalk Correction: Timewalk and Jitter
- **Why not CFD?**
- Slope in distribution of time difference over energy due to time walk
- Take mean of each energy bin and use that as corrections
	- "As a lookup table"
- Look at distribution of time differences 
	- Uncorrected  vs corrected - **the corrected is not centered**
### Time Alignment 
- Time delay in each channel is different - need to correct that
- Using the time difference between two hits in neighboring tiles
- Idea: Sum over time differences on a closed loop should be zero
- reduced offset to $\pm15\,$ps
- Additionaly - Correlate distant tiles using cosmics