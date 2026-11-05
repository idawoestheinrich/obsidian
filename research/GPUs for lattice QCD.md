---
tags:
  - context/Particle_Physics_Workshop_2026
aliases:
date:
---
Stefan Schaefer

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
- The cores have lower clock speed
Structure the problem in a way that all of these cores are busy all the time 
Single instruction multiple threads

Streaming Multiprocessors
- Memory access is organised in requests of 32bytes.
- The accesses of all threads from a warp are **coalesced** together.

Code to port 
- from one big loope aver all data to launching many threads (N_blocksxN_threads)

Strategy
- be carful that they don't interfere 
- If you start from a CPU code - check interation for iteration
Is it worth it? 
- For the QCD lattice very efficient kernels have been implemented
- New GPUs code uses 1/10 of the energy 
