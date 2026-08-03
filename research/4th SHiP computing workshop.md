[indico](https://indico.cern.ch/event/1677488/timetable/#20260508.detailed)
# Thursday
- [[New framework integration]] - Matei
- [[Timestamping with phlex in the UBT]] - Matei
#####  Future framework considerations - Oliver
- Phlex prototyping status
- What is usable? 
	- Geometry (service)
	- Simulation
	- Data Model
-  How to integrate GEANT4 - has a very specific way to work
- Currently the bottleneck is building stacks, once done, usable for everyone without building everything 
	- Automate this process?
	- CVMFS? 
	- People can use standard library but own analysis tools
##### Timeline
- Technology decision imminent *- AMBER - Hadron Spectronmy?* (END of month)
	- Will be anounced in Bristol?
- New studies that do not need to be compared with old studies to help shape it 
	- Fixed on target studies
	- Ask about specific signals - HNL - intermediate files 
	- EventCalc in c++ 
	- Converting from one Model to another - but with Agents it is easy

#### Aegir 
- Fixed target minimum bias is ready for vertification 
	- ATLAS has been workling hard to decouple GEANT4 from Gaudi 
- Do we want to have the entire tool chain in a single go? *In a single framework!*
- Geometry service 
- use `mp_units` where possible?
	- `mp_units` is a modern C++ library for **type-safe physical quantities and units**. It lets you represent things like meters, seconds, kilograms, volts, etc., directly in the type system so the compiler can catch unit mistakes at compile time.
#### Data Model
- For now MC truth is implemented

#### Gaudi and Phlex
- Gaudi is moving more and more into the direction of Phlex
	- OOP to functional 
	- TED to data flows
- Algorithms basically interchangeable as long as functional 
#### Politics and social aspects
- SHiP as stakeholder (key4hep?) - in Phlex we would have weight - DUNE is on it
	- DUNE is the elephant in the room as Phlex will have to adapt to there requirements
		- If we become stakeholder, we can contribute and therefore change stuff 
		- We discuss what we need with them
	- Gaudi is in maintenance state
	- Every collab has its own documentation 
	- Navigating can be tricky? 
- key4hep one-size-fits-all fit? 
	- It is very fitted for collider physics
		- FCC assumptions do not hold for us
		- Software of the 
	- CMS have some parts running - as an analysis frame work
- *OPEN SOURCE SOFTWARE*

### New Geometry into the new framework
- [[Geometry of SBT]]
- Darjas Talk on “Neutrino Background Suppression with a GNN using the SBT: Goals and Work in Progress” - similar to DPG Talk 
	- Zotero PDF Link: [PDF](zotero://select/library/items/3H8ADNY2) 
	- [[Neutrino Background Suppression with a GNN using the SBT - Goals and Work in Progress]]
	- All the loops in python are really slow
		- Build a computation graph 
		- R-Dataframe is the way to go 
- *How can we detect photons in the SBT?*
- [[Reconstruction of the Heavy Neutral Lepton (HNL) decay into lepton +]]
- [[Muon Background 2026]]
### Reconstruction
- [[Reconstruction kickoff]]
- [[Data SBT 2026]]
# Friday 
- ### [[Software validation]]
-  [[SHiP Starter Kit for Summer Students]]
	- Summer Students into shifts for SBT test beam?
Interviews today?:
- **Valerii**
- Ida
- **Eduard** 
- Maik
- Yulia
### (Mis-)adventures of stack automation and related topics - Oliver
#### Basic aliBuild usage (same for bit and aliBuild)
( is a build and package management tool developed by the ALICE Collaboration for managing large scientific software stacks.

You can think of it as something between:

- a package manager
- a build orchestrator
- a reproducible environment manager

It is heavily used in high-energy physics (HEP), especially around the ALICE experiment at CERN.)

- Build on openstack machine right directory 
- Sync to CVMFS publishing machine 
- #### modulfiles
 #### Reproducibility
- aliBuild supports reusing pre-build packages
 #### S3 remote store
 - can download pre-build packages from S3
 AliBuild can check your code
- #### Phlex and aegir in nightly repo 
- cvmfs/ship.cern.ch
- cvmfs/ship-nightlies.cern.ch

### [[Introduction to Ganga]]
- Tiny bit of a learning curve - documentation - can you add this to the general documentation - 

# WILL PROBABLY BE REALLY USEFUL!
- [[Workflow management 2026]]
- [[Tips for agentic coding 2026]]
