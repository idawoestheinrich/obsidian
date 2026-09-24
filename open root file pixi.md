```
pixi run root -l <filename>.root
```
Load file in root:
```
root [1] auto df = ROOT::RDF::FromRNTuple("events", "<filename>.root");
```
Display the variables safed in that file:
```
root [2] df.Describe().Print();
```

display the values of specific variables for 10 events: 
```
df.Display({"variable1", "variable1"}, 10)->Print();
```
