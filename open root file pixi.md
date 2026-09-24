```
pixi run root -l <filename>.root
```
Load file in root:
```
root [1] auto df = ROOT::RDF::FromRNTuple("events", "<filename>.root");
```
Display the variables safed in that fule
```
root [2] df.Describe().Print();
```