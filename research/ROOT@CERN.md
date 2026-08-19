---
tags: 
aliases:
  - ROOT
  - root
  - Root
---
ROOT@CERN usefull commands


```root
db->GetParticle(11)->GetName()
```
ROOT prints returned values automatically

> To run it from Python:
> 	import ROOT
db = ROOT.TDatabasePDG.Instance()
print(db.GetParticle(11).GetName())  # Output: e-



ssh [idwoesth@lxplus.cern.ch](mailto:idwoesth@lxplus.cern.ch)



43eaa15c95e261fc684c24fe2fe7652a