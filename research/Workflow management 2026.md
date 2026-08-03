---
Title: "Workflow management" 
Year: 2026 
Authors: Eduard Ursov 
Tags:  
---
Zotero PDF Link: [PDF](zotero://select/library/items/BRS9W9NX) 

 
### In-text annotations
###### Introduction [Page 2](zotero://open-pdf/library/items/BRS9W9NX?page=2&annotation=593ZBRF8)
- In HEP, to get results, we usually have a bunch of programs we launch step  by step: [Page 2](zotero://open-pdf/library/items/BRS9W9NX?page=2&annotation=UGHF3YZ7)
- Data production -> Simulation -> Reconstruction -> Analysis [Page 2](zotero://open-pdf/library/items/BRS9W9NX?page=2&annotation=898GWKN9)
- For testing cases, the bash/python script is enough to simulate it step by step [Page 2](zotero://open-pdf/library/items/BRS9W9NX?page=2&annotation=ZTVDBH6Q)*automatisation would be great* [Page 2](zotero://open-pdf/library/items/BRS9W9NX?page=2&annotation=ZTVDBH6Q)
- To get statistically robust results, one has to batch this pipeline into separate  parts [Page 2](zotero://open-pdf/library/items/BRS9W9NX?page=2&annotation=LVWVAVFY)
###### HTCondor [Page 3](zotero://open-pdf/library/items/BRS9W9NX?page=3&annotation=GS5UB2Y9)
- Easy to use: sub file + bash script with pre-defined environment and bunch of  instructions [Page 3](zotero://open-pdf/library/items/BRS9W9NX?page=3&annotation=U3YIFJYS)
- python as a steering wheel is deeply integrated [Page 3](zotero://open-pdf/library/items/BRS9W9NX?page=3&annotation=UHBNSRY5)
- Usage can be upgraded to DAGman mode [Page 3](zotero://open-pdf/library/items/BRS9W9NX?page=3&annotation=XXCDPJ9K)
![[research/ursovWorkflowManagement2026/image-3-x220-y7.png]]
###### Example: full pipeline for the SND@LHC upgrade [Page 4](zotero://open-pdf/library/items/BRS9W9NX?page=4&annotation=NIU9B7NE)
- Can be found here [Page 4](zotero://open-pdf/library/items/BRS9W9NX?page=4&annotation=TXAU23RX)
- from gevgen_fnal to digitized output file with event builder [Page 4](zotero://open-pdf/library/items/BRS9W9NX?page=4&annotation=MJAWYESB)
![[research/ursovWorkflowManagement2026/image-4-x20-y107.png]]
- many-to-many [Page 4](zotero://open-pdf/library/items/BRS9W9NX?page=4&annotation=6G42HPQI)
![[research/ursovWorkflowManagement2026/image-4-x370-y12.png]]
###### Pipeline structure [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=5BXY2EW4)
- python launcher: [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=UC8986Z6)
- creates the DAG instructions [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=ERDSVKVE)
- catch errors before submission [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=UPZCN8V8)
- defines which pipeline to launch [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=H25H37IB)
- scalable – add a custom step is trivial [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=783QU26M)
- one-to-one and many-to-many options [Page 5](zotero://open-pdf/library/items/BRS9W9NX?page=5&annotation=6IQBVDGV)
###### HTCondor DAGman [Page 6](zotero://open-pdf/library/items/BRS9W9NX?page=6&annotation=PQP7T9DM)
- Manager of the htcondor sub files [Page 6](zotero://open-pdf/library/items/BRS9W9NX?page=6&annotation=4LTMFV95)
###### python will handle it! [Page 7](zotero://open-pdf/library/items/BRS9W9NX?page=7&annotation=AQBZ5RYZ)
- It’s better to create the parent-child relation via python that will create the dag instructions in the end [Page 7](zotero://open-pdf/library/items/BRS9W9NX?page=7&annotation=STWHMNDA)
###### What covers the launcher [Page 8](zotero://open-pdf/library/items/BRS9W9NX?page=8&annotation=V6B498VI)
- User’s choice: ● type the arguments values in the  shell ● pass the yaml file with the values [Page 8](zotero://open-pdf/library/items/BRS9W9NX?page=8&annotation=W3ZHX22P)
###### Reproducibility: Yaml cards for the launching parameters and the markdown file in the output folder [Page 9](zotero://open-pdf/library/items/BRS9W9NX?page=9&annotation=L3T8I86R)
- Reproducibility is the main advantage given the very random way of how the  lxplus shell memorizes commands [Page 9](zotero://open-pdf/library/items/BRS9W9NX?page=9&annotation=PUWJBUNG)
- Another reproducibility wall – automatic creation of the output markdown file  in the output folder: [Page 10](zotero://open-pdf/library/items/BRS9W9NX?page=10&annotation=BXAVCEMI)
###### Typical usage [Page 11](zotero://open-pdf/library/items/BRS9W9NX?page=11&annotation=SNI5BB3B)
- the –flow key specifies which sub (and sh) files should be launched and their  order [Page 11](zotero://open-pdf/library/items/BRS9W9NX?page=11&annotation=7NAL3RBL)
- example of many-to-many option [Page 11](zotero://open-pdf/library/items/BRS9W9NX?page=11&annotation=9Q68VTYR)
###### Example of a sub file [Page 12](zotero://open-pdf/library/items/BRS9W9NX?page=12&annotation=YNNBR4N5)
###### Configuration information [Page 13](zotero://open-pdf/library/items/BRS9W9NX?page=13&annotation=IYKTPFW2)
- The python launcher does not allow to launch simulation w/o specifying the  simulator path and the condor folder path: [Page 13](zotero://open-pdf/library/items/BRS9W9NX?page=13&annotation=B5U2Y42J)
- The information about the input and output files of each step is stored in the  config.sh file that launches in the beginning of each bash script. Some of the information is taken from the python launcher script, some is hardcoded (file names) [Page 13](zotero://open-pdf/library/items/BRS9W9NX?page=13&annotation=4EU2BG3L)
###### Snakemake [Page 14](zotero://open-pdf/library/items/BRS9W9NX?page=14&annotation=SI6MUSMX)
- As far as I understood, the HTCondor  support of Snakemake looks weird: snakemake launches the jobs with the rules in the pipeline and waits for them to be finished (?) [Page 14](zotero://open-pdf/library/items/BRS9W9NX?page=14&annotation=RBS2P2NR)*Did not success* [Page 14](zotero://open-pdf/library/items/BRS9W9NX?page=14&annotation=RBS2P2NR)
- SHiP neutrino simulation pipeline [Page 14](zotero://open-pdf/library/items/BRS9W9NX?page=14&annotation=L43WN7RJ)
