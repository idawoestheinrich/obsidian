Lattice QCD calulations are Marcov Chain MC Calulations
- Most of the time solving Dirac Equations- millions of times 
- Compute nearest neighbors differences 
- Space time is distribute to many processor
	- Transition from CPU to GPU 
	- 100.000.000 core hours 100t in CO2 emission
	- GPUs can substantially lower the carbon footprint - needs significant work 
CPU a few 10 cores and very large main memory 
- Fast clock speed
- Carfull memory access
GPUs are quit e differnt - 16 000 cores with limited memory
- The cores have lower clock spee
Structure the problem in a way that all of these cores are busy all the time 