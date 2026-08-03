---
tags:
  - context/Research_Seminar
  - type/talk
  - topic/detector_physics
aliases:
date: 2025-10-23
---
# **Humidity Studies on** **ATLAS ITk Strip Sensors**
- Ilona Ninca

### Particle Physics and the LHC
- Dark Matter
## Inner Tracker Upgrate ATLAS
- Pixel detetcot
- Strip detetor
- Petals and Staves
- Cooling and Powering 
#### Silicon Strip Module
- n-in-p 
- Hybrids - polyimide flex circuit board
- readoy chips
- control chips
#### ATLAS ITk Silicon Strip Sensor
- 6-inch waver Hamamatsu
- Humidity effects
- Bias ring - stips are at the same potential
- Edge ring and guard ring 
- Backside with the p-implant used to apply bias voltage
### Humidity Study Motivation 
- Large area sensors showed humidity sensitivity - early breakdown
- *Why is that relevant in the detector - vacuum/controlled enviroment?*
- Mini Diodes 
	- Same substrate properties
	- MD8 Geometry 
##### Humidity Mechanism 
- water vapor present in air
- relative humidity
- +/- ions - changing electrical properties
	- What ions? 
		- enviroment - the water 
		- with high humidity you increase the cunductance of the surface 
	#### Challenges and Mitigation 
	- Early breakdown of sensors might destroy them
	- Propose new geometies
### Top-Transient Current Technique Set-Up 
- Humidifier/Dry air
- Rasperry Pi board 
- Laser scanning 
### Measured Transient Currents
- Fast Component - slow component

### Charge Profile over the ITk - $\micro m$
- V_bias = 900 V
- independent
### Prompt Currents

### Technology Computer Aided Design (TCAD
- Synopsys
- physics-baded semiconductor simulation 
- Poisson+ continuity+transport equations
- **Challenge** humidity implementation 
	- modify surface resistance
### First Check 
- leakage current increases with humidity
	### Simulated Electric Field Distribution 
	- Absolute electric field cutline along x-axis underneath the surface
	### Simu. electron density
	- low density electron channel between ER and GR in dry conditions
	### Hole density 
#### Conclusions and Forward
- Maximum prompt current matches simulation
	- induce charge multiplication of drifting electrons
- Future:
	- Thicker passivation layer
	- Kodak protoresist

How do you get the shape? 
 - Flat due to aluminum , electric field build up between ER and GR
### Time scale - why does it take so long? 2500 s
- Waiting time >> 10 min? Not related
- Why do you have these steps in the first 900s - in the ramping
- Could this have an effect on the results? 
	- 500s steps does not refer to any meaningful event? 
