---
Title: Software validation
Year: 2026
Authors: Valerii Kholoimov
Tags:
---
Zotero PDF Link: [SHiP_software_validation.pdf](zotero://select/library/items/RQV79EQ5) 

 
### In-text annotations
###### What do we have today? [Page 2](zotero://open-pdf/library/items/RQV79EQ5?page=2&annotation=WFRYW9I2)
- Fixed target simulation [Page 2](zotero://open-pdf/library/items/RQV79EQ5?page=2&annotation=VHWFDJUM)
- General Simulation  (does not validate physics results, only checks that the simulation runs successfully) [Page 2](zotero://open-pdf/library/items/RQV79EQ5?page=2&annotation=YGE9RFG3)
- Tracking Benchmark  (since ~2 weeks ago) [Page 2](zotero://open-pdf/library/items/RQV79EQ5?page=2&annotation=DHGH5YCK)
###### Physics benchmark [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=KKZIDMZ2)
- Define a list of O(~30) benchmarktests [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=BU4ZSPF5)
- Run them once per PR before merging [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=5MXHNIR7)
- Check that key physics results remain stable (!) [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=U9VXVZSB)
- Detect unexpected changes early [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=6UNDP7JR)
- If results change, verify that the change is understood and expected [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=R2JRDTLK)
- Physics impact from code change is often small [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=UAX4DPM2)
- Changes may not be immediately noticeable [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=R3MQVSKI)
- Small shifts can accumulate over time [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=CBC7U4HL)
- Hard to detect without systematic checks [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=6GRW9VPK)
- Software stack is complex and highly interconnected [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=NNPUT63A)
- A small change in one place can affect unrelated components [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=6XNQHEQU)
- Bugs can be introduced without being immediately visible [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=LZAY4CGS)
- Failures may appear far from the source of the change [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=J8CUJ49A)
- Hard to manually track all side effects [Page 3](zotero://open-pdf/library/items/RQV79EQ5?page=3&annotation=P4S93E4D)
- What was done since presentation on a Physics meeting [Page 4](zotero://open-pdf/library/items/RQV79EQ5?page=4&annotation=AABN9KXF)
- Extra validation for FairShip [Page 4](zotero://open-pdf/library/items/RQV79EQ5?page=4&annotation=CT7HZ7UB)
- pytest added to shipdist [Page 4](zotero://open-pdf/library/items/RQV79EQ5?page=4&annotation=9FU8QVZL)
- Minimal example with different simulation user cases [Page 4](zotero://open-pdf/library/items/RQV79EQ5?page=4&annotation=VPWMVFGF)
- New extra --validation flag for FairShip [Page 5](zotero://open-pdf/library/items/RQV79EQ5?page=5&annotation=KMTUDP3Q)
![[research/valeriikholoimovSoftwareValidation2026/image-6-x21-y34.png]]
###### Reference file generation [Page 9](zotero://open-pdf/library/items/RQV79EQ5?page=9&annotation=9LBX5AFM)
- Reference can be regenerate by one simple line: [Page 9](zotero://open-pdf/library/items/RQV79EQ5?page=9&annotation=KMTN6L82)
- FAIRSHIP_REGENERATE_REFERENCES=1 pytest -vv -s -k pythia8_summary tests/test_simulation_references.py [Page 9](zotero://open-pdf/library/items/RQV79EQ5?page=9&annotation=TIWYGGC8)
- The command will do everything automatically for you, run your script, catch the output in a same way as it’s done during the test, save it where reference should be stored. [Page 9](zotero://open-pdf/library/items/RQV79EQ5?page=9&annotation=V7SQDBQM)
###### Current Minimal Version [Page 10](zotero://open-pdf/library/items/RQV79EQ5?page=10&annotation=63JZBCBX)
- pytest was added to shipdist [Page 10](zotero://open-pdf/library/items/RQV79EQ5?page=10&annotation=GP9NT3F8)
###### “Can I run the test already?” [Page 11](zotero://open-pdf/library/items/RQV79EQ5?page=11&annotation=SDZTWG7K)
- Not yet: [Page 11](zotero://open-pdf/library/items/RQV79EQ5?page=11&annotation=CE9DLCJT)
- 1. Ideally testing will require pytest in cvmfs env [Page 11](zotero://open-pdf/library/items/RQV79EQ5?page=11&annotation=HH67K2DU)
- 2. Still some minor issues to be fixed [Page 11](zotero://open-pdf/library/items/RQV79EQ5?page=11&annotation=AMZM8ZF5)
- (e. g. Simulation RunID, it could be manually set in run_fixedTarget.py, but not in run_simScript.py) [Page 11](zotero://open-pdf/library/items/RQV79EQ5?page=11&annotation=FB2MKKI6)
###### (possible) Road ahead [Page 12](zotero://open-pdf/library/items/RQV79EQ5?page=12&annotation=TENDSRUL)
- Implement minimal version with different technical tests for different  user cases (so we can be sure that at least all generators can be run) [Page 12](zotero://open-pdf/library/items/RQV79EQ5?page=12&annotation=7VYZ3LXL)
- Have it available for testing in PRs [Page 12](zotero://open-pdf/library/items/RQV79EQ5?page=12&annotation=Z9F6HSLI)
- Implementation of Physic validation (e.g. KS0 production,  reconstruction and analysis chain) [Page 12](zotero://open-pdf/library/items/RQV79EQ5?page=12&annotation=FI8I5EZC)
- Note: currently due to dependency management multithreading was not configured (total runtime ~10 mins for now), probably has to be reconsidered in future. [Page 12](zotero://open-pdf/library/items/RQV79EQ5?page=12&annotation=DEBBURGH)
