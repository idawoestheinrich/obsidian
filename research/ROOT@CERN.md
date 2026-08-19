---
tags: 
aliases:
  - ROOT
  - root
  - Root
---
# ROOT@CERN usefull commands
1. Load a [[RNTuple]] into [[RDataFrame]]
```root
auto df = ROOT::RDF::FromRNTuple("events", "gun_output.root");
```

2. Book the 1D histogram: ("name", "title;X-axis;Y-axis", n_bins, x_low, x_up) 
```root
auto h_energy = df.Histo1D({"h_energy", "Particle Energy;Energy [GeV];Particles", 100, 0.0, 50.0}, "mc_particles.energy"); 
```
3. Open a new ROOT file and write the histogram  
```
auto outFile = TFile::Open("energy_histogram.root", "RECREATE"); 
h_energy->Write(); 
outFile->Close();
```


db->GetParticle(11)->GetName()
```
ROOT prints returned values automatically

> To run it from Python:
> 	import ROOT
db = ROOT.TDatabasePDG.Instance()
print(db.GetParticle(11).GetName())  # Output: e-



ssh [idwoesth@lxplus.cern.ch](mailto:idwoesth@lxplus.cern.ch)



43eaa15c95e261fc684c24fe2fe7652a