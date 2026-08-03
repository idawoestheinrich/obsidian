---
Title: "Reconstruction kickoff" 
Year: 2026 
Authors: Mark Smith 
Tags:  
---
Zotero PDF Link: [PDF](zotero://select/library/items/R6SXEFLX) 

 
### In-text annotations
- Gather exactly what information each subsystem is providing to  the reconstruction [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=EECTE4RZ)
- What other pieces of information do we need [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=AQI3A2NN)
- Understand the line between “simulation” and “reconstruction”  matters - i.e. which pieces are identical for real data and MC [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=Q7BKQ7DM)
- This is thinking about the new software framework - no plans to  radically change FairShip [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=R8SDB6WG)
- Not for today but another time: [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=GDV4H3WY)
- Time window / event model - informed by today’s discussion  and technology choices [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=UHA5RTSP)
- Alignment (spatial and time) [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=TYVPDVEQ)
- Outputs for physics [Page 2](zotero://open-pdf/library/items/R6SXEFLX?page=2&annotation=CI6JPCPW)
###### Bits and pieces [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=XU5N3WVD)
- Tracking [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=7RJ9NKKF)
- ACTS - well advanced plans (James) [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=7T8Y8BD5)
- Conditions database [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=WXUZDDV3)
- Implementation well underway [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=SM8PPWW5)
- Will need to implement reading/writing (including for simulation) [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=ZLK8BGN3)
- Today we should start thinking about what goes in it from each  detector [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=6YWD8U6E)
- Other metadata [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=RZWZEMH6)
- This needs to be propagated from initial data to final product [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=RMQE8BD9)
- Must have everything to know the provenance of the [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=T59ZYII4)
- file/data/reconstruction/processing [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=NJVDMQDS)
- Technology  ○ Looks like phlex is likely? [Page 3](zotero://open-pdf/library/items/R6SXEFLX?page=3&annotation=QUJ2YERV)
*Reconstruction: ● Tracks, PIDs, veto matching ... - Physics / Process for STL output and physics and analysis
- Save raw data and than safe reco data.
Detectore readout - Turn detector signals into hits etc.* [Page 5](zotero://open-pdf/library/items/R6SXEFLX?page=5&annotation=2T3RGB7N)![[research/smithReconstructionKickoff20260507/image-5-x1-y3.png]]
- Detectors should implement their own object class (Detector readout) [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=Q595IME4)
- Ideally inherit from a generic SHiP reco object [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=AHPJPJUJ)
- Stores inputs [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=6WE3QGXN)
- Stores reco objects [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=R4FRUX2N)
- Reconstruction collates this [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=ZWIH4WTI)
- Track/vtx reconstruction, timing matching, vetoing probabilities ... [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=EQR2Y9LV)
- Data format? [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=JC5MRR8Q)
- ROOT works for things within SHiP framework [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=J4BX2E9H)
- Within the framework could be anything that stores tuples of C++  objects [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=7P69L2C5)
- For the final physics output do we want something else? [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=MABXIGPB)
- Save as python data frames / numpy arrays? [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=FGEHDZFC)*What would be the advantage?* [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=FGEHDZFC)
- Make a SHiP analysis (pure) python package for translation into  useable formats? [Page 6](zotero://open-pdf/library/items/R6SXEFLX?page=6&annotation=GLIQL669)
###### Plan [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=2HQ393U7)
- Based on information from today I will construct a framework pipeline for  reconstruction workflow [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=CALUABEY)
- Take in detector outputs [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=5EZMMK4N)
- Passthrough to output [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=NRR3QBFT)
- A placeholder for ACTS and other pieces etc [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=9ZEDHVDI)
- Modular and generic [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=TU562M6P)
- Save framework specific objects into files [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=V974M67U)
- Read output files and turn into useful physics info [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=JLT6XEYJ)
- STL structures only [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=TFXPKGZ5)
- Need help from the simulation/subsystem liaisons [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=ZZEETTGA)
- What exactly is implemented currently? [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=MGTF73QZ)
- How are you saving that information? [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=TE6C5IYJ)
- Aim: initial pipeline implementation in a month or two [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=GF23X22L)
- Then add the complications [Page 7](zotero://open-pdf/library/items/R6SXEFLX?page=7&annotation=XR8974P3)
