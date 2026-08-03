---
Title: "New framework integration" 
Year: 2025 
Authors: Matei Climescu 
Tags:  
---
Zotero PDF Link: [PDF](zotero://select/library/items/XUHGELFC) 

Related::  

### Persistent Notes 
%% begin notes %% 
Write notes here! 
 %% end notes %%

### In-text annotations
###### To build a factory framework [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=C74ASQ98)
- The main components of a software framework are [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=U3EBXVJ8)
- A simulation core [based on GEANT4/FLUKA and generators, see session yesterday with in  particular the talks but Hanae] [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=GIJVBDJ3)
	- *Building Blocks People can use for analysis*
- Geometry description [see further] [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=VTX2QJ6B)
- Digitisation: (Turning the raw physics information from G4 into detector responses) [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=9ZPF6NMF)
- Reconstruction: (Deriving physics knowledge from the digitised information )[Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=SUDY8HFB)
- Analysis tools: (The layer which allows one to use the physics information to obtain high-level  information) [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=XY7KXF2G)
- Data model: How are we storing the information at every level [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=YQKCVTG5)
- Other elements are also important and need to be accounted for: event displays - see my  talk yesterday, monitoring and other services [Page 3](zotero://open-pdf/library/items/XUHGELFC?page=3&annotation=38JYAQW3)
- The geometry description is the first step to get a proper description of our detectors [Page 4](zotero://open-pdf/library/items/XUHGELFC?page=4&annotation=GFTRTDA3)
- Geometry description needs to fulfill some requirements [Page 4](zotero://open-pdf/library/items/XUHGELFC?page=4&annotation=5B8Q6MKW)
- Simple to understand, maintainable [Page 4](zotero://open-pdf/library/items/XUHGELFC?page=4&annotation=TFH2Y88D)
- Fast [Page 4](zotero://open-pdf/library/items/XUHGELFC?page=4&annotation=2LPK2KFH)
- Configurable at run time [Page 4](zotero://open-pdf/library/items/XUHGELFC?page=4&annotation=GRP642KK)
- Easy to integrate to the rest of the chain [Page 4](zotero://open-pdf/library/items/XUHGELFC?page=4&annotation=W7MT84VU)
![[image-5-x7-y56.png]]
- How do we go from the left to the right? [Page 5](zotero://open-pdf/library/items/XUHGELFC?page=5&annotation=WJ67CXQX)
###### GEANT4 integration [Page 6](zotero://open-pdf/library/items/XUHGELFC?page=6&annotation=BBEJE54C)
- GEANT4 deals with propagation of particles through matter (again see Hanae’s talks from  yesterday, she goes into much more detail) [Page 6](zotero://open-pdf/library/items/XUHGELFC?page=6&annotation=3V4F2RAH)
- However, how we compute and extract the GEANT4 information is a physics choice [Page 6](zotero://open-pdf/library/items/XUHGELFC?page=6&annotation=FXZ5P8ES)
- Step size, sensitive materials, which truth information to extract, everything comes at a cost [Page 6](zotero://open-pdf/library/items/XUHGELFC?page=6&annotation=7KBTT3FZ)
- Important to know what we want and why [Page 6](zotero://open-pdf/library/items/XUHGELFC?page=6&annotation=N92S4SX5)
- So the geometry defines what is there and GEANT4(/FLUKA) simulation defines what  happens when a particle crosses the volume [Page 6](zotero://open-pdf/library/items/XUHGELFC?page=6&annotation=3APIFEFY)
###### The geometries that were built: SND [Page 7](zotero://open-pdf/library/items/XUHGELFC?page=7&annotation=YKNRWMQ5)
![[image-7-x4-y110.png]]
- SND has 3 main sections: veto, silicon tungsten and magnetised tracking [Page 7](zotero://open-pdf/library/items/XUHGELFC?page=7&annotation=EQMJ8FTX)
- Energy depositions are recorded as well as layer information, positions... [Page 7](zotero://open-pdf/library/items/XUHGELFC?page=7&annotation=3WPR5JIZ)
- Version with GENIE currently pending review from Antonio [Page 7](zotero://open-pdf/library/items/XUHGELFC?page=7&annotation=FS4N9IQT)
###### The geometries that were built: tile UBT [Page 8](zotero://open-pdf/library/items/XUHGELFC?page=8&annotation=42PU33DI)
- The tile UBT has responsibility to veto  backgrounds based on timing (see next talk) [Page 8](zotero://open-pdf/library/items/XUHGELFC?page=8&annotation=CTTVSGIR)vetos on timing [Page 8](zotero://open-pdf/library/items/XUHGELFC?page=8&annotation=CTTVSGIR)
- A Pythia8 implementation to test for DIS in the  PS (will perhaps also look at adding some iron in front of the system to mimic the MS) [Page 8](zotero://open-pdf/library/items/XUHGELFC?page=8&annotation=ARGMFYQN)Neutrino interactions [Page 8](zotero://open-pdf/library/items/XUHGELFC?page=8&annotation=ARGMFYQN)
- The option to use CUDA muons also present (see  next talk [Page 8](zotero://open-pdf/library/items/XUHGELFC?page=8&annotation=HYNKRPJT)
###### The geometries that were built: SBT [Page 9](zotero://open-pdf/library/items/XUHGELFC?page=9&annotation=5XP64YCA)
- By far the most challenging detector (to be) built: many cells, entanglement with the  supporting decay volume [Page 9](zotero://open-pdf/library/items/XUHGELFC?page=9&annotation=QJIZFBK9)
![[image-9-x8-y14.png]]
###### The geometries that were built: LHCB calorimeter [Page 10](zotero://open-pdf/library/items/XUHGELFC?page=10&annotation=USTK77ZP)
- Now we are looking at the physics of the detector  → the LHCB geometry was adapted to GeoModel with a Geant4 response [Page 10](zotero://open-pdf/library/items/XUHGELFC?page=10&annotation=CFBYABJQ)
- For PID studies, we are now integrating it to the  SST for more realism [Page 10](zotero://open-pdf/library/items/XUHGELFC?page=10&annotation=EVHGRAG7)
- 5 setups available [Page 10](zotero://open-pdf/library/items/XUHGELFC?page=10&annotation=VENQX349)meant to be flexible - Look at marteis talk in last Collaboration meeting [Page 10](zotero://open-pdf/library/items/XUHGELFC?page=10&annotation=VENQX349)
###### The geometries that were built: the best my favourite for the end: the calorimeter system [Page 11](zotero://open-pdf/library/items/XUHGELFC?page=11&annotation=TCQQ8WW7)
- A Split Calorimeter using 3 different types  of layers and a custom HCAL [Page 11](zotero://open-pdf/library/items/XUHGELFC?page=11&annotation=76MDRRFM)
- Comes with in depth truth information as  well as detailed digitisation, reconstruction, clusterisation and directionality reconstruction [Page 11](zotero://open-pdf/library/items/XUHGELFC?page=11&annotation=67RLKX2Z)
- Necessary for physics studies, performs  excellently in PID and is capable of vertexing neutral final states [Page 11](zotero://open-pdf/library/items/XUHGELFC?page=11&annotation=ZWEUIBEW)
###### ShipSoft Geometry [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=G6M6S2QH)
- Oliver has setup a geometry repository for the new framework’s geometry  I https://github.com/ShipSoft/Geometry [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=P9RCTF6L)
- merge in the calorimeter, the SST and the SBT [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=G96FYRU7)
- Your help is welcome to populate this repo! [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=KYAMIMMX)
- MS and target complex still missing [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=GIDES7QA)
- Improving the flexiblity of the existing detectors is also needed: allowing for us to better  modify/remove parts of our detectors based on physics requirements/funding [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=79ZI9G6Q)
- Moving to a standard configuration format (.toml or .xml) is another worksite [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=IJFX7NHJ).toml [Page 12](zotero://open-pdf/library/items/XUHGELFC?page=12&annotation=IJFX7NHJ)
###### Digitisation [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=3EVPWTZP) *WE NEED TO BE CONSISTENT*  [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=3EVPWTZP)
- Digitisation is a matter of philosophy, so far in FairShip, we’ve mostly performed hit  grouping [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=TP347NLF)
- digitisation yields the detector response: channel IDs, ADCs, TDCs... No  positions, energy quantities... [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=RWCSV6FP) *What the electronics will give you* [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=RWCSV6FP) - *SampIC, FastIC,...* 
- Everything above that is reconstruction [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=8W5JA5DZ)
- Problem: we need to know this information for each detector, not all are advanced enough  to provide a reasonable estimate [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=QYST39RY)
- It however is necessary to properly address the challenges of reconstruction (ex: strip vs  pixel geometry), is the best way to cross-check that we actually understand our detectors (ex: SND@LHC SciFi) [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=58HB855U)We know that the simulation of the digitalisation is incorrect [Page 13](zotero://open-pdf/library/items/XUHGELFC?page=13&annotation=58HB855U)
###### Reconstruction infrastructure: Gaudi and Phlex [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=5YXW3I6B)
- Data processing frameworks, meant to provide a consistent interface to digitisation/reconstruction  algorithms [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=GN95H2AI)
- Gaudi is a framework developed since 1998 at CERN and widely used in many experiments [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=5435W5GX)
- Works around the Transient Event Store [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=MCA5QPET)a central tree - [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=MCA5QPET)
- a tree which hold all of the data for the processed event [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=GQ29H73Z)
- User-written Algorithms read and write from the TES [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=82ZBWK5A)
- EventLoopManager [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=S2BAE6XU) *Central Manager which manages the data on event by event basis* [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=S2BAE6XU)
- Phlex is a framework developed in the US (FermiLab, Brookhaven and Stanford), much younger and an  off-shoot of DUNE [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=5LU49GSK)
- Algorithms are akin to plain C++ functions [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=LLWVVHI6)
- Providers and Preservers deal with I/O and intervene along the graph as needed [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=94N75G3E) - 
- Overall, Gaudi is liable to its event structure whereas Phlex is more nimble and reads time slices out [Page 14](zotero://open-pdf/library/items/XUHGELFC?page=14&annotation=4U745U7S)
- Reconstruction infrastructure: Gaudi and Phlex simplified views [Page 15](zotero://open-pdf/library/items/XUHGELFC?page=15&annotation=ZXYDN39I)
![[image-15-x28-y47.png]]
![[image-15-x260-y53.png]]
###### Physics driven data model [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=RI3ML4MA)
- While certain things (RNTuple, RUCIO) seem pretty set in stone the way we record information is  incredibly important as it provides [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=ASMSEUB6)
- SHiP is a triggerless experiment: [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=T6FS22UD)In ATLAS you have a clock that triggers on the crossings [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=T6FS22UD)
- we have no idea when data will come, [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=IMLYNHJW)for 1.2s we might get physics after the spill trigger [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=IMLYNHJW)
- we run in a push architecture: the  DAQ needs to be able to process the data detectors send to it [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=2W8GA5UG) - We to run dynamically [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=2W8GA5UG)
- We need to draw a consistent picture from scattered hits all over the experiment → they have to be stored  in dynamic vectors in my view [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=GHVZMEF6)
- The vector indices for a subcategory of events provide the needed matching: same index for two vectors of  the calorimeter: same hit (`vADC [i] = vTDC [i] = vchID [i]`) [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=J5M97FMK) - *ask later about it *
	- *Very similar to ALICE -similar but very different constrains - huge TPC*
- Portability would dictate that we keep these outside of classes but classes are a nice grouping option  [Page 16](zotero://open-pdf/library/items/XUHGELFC?page=16&annotation=VI2TUQRM)

- We are at a critical juncture where many crucial choices have to be made and implemented  into the new framework architecture [Page 17](zotero://open-pdf/library/items/XUHGELFC?page=17&annotation=MUZUFMMJ)
- The way we process our data will determine how usable our framework is [Page 17](zotero://open-pdf/library/items/XUHGELFC?page=17&annotation=9S4I9E7Y) we need to understand why we are doing things - Oliver is reaching out to other experiments [Page 17](zotero://open-pdf/library/items/XUHGELFC?page=17&annotation=9S4I9E7Y)
- The most immediate next step is to have a full geometry description available → PR  treatment will accelerate on the geometry repo [Page 17](zotero://open-pdf/library/items/XUHGELFC?page=17&annotation=8SZE7R7J)
- Information as to the detector output of the different subsystems is crucial here, MTC  and TUBT I can probably do on my own, everything else information must be made available [Page 17](zotero://open-pdf/library/items/XUHGELFC?page=17&annotation=F9EIUKVH)
- Help is very appreciated in digitisation algorithms, you can get the code of any subsystem  and get going, help is always on offer [Page 17](zotero://open-pdf/library/items/XUHGELFC?page=17&annotation=J7ETFY87)
- Friendship [Page 18](zotero://open-pdf/library/items/XUHGELFC?page=18&annotation=BNPBR2MA)


%% Import Date: 2026-05-07T10:04:11.169+02:00 %%
