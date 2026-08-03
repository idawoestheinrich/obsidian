[ROOT Reference Guide](https://root.cern.ch/doc/master/classTH1F.html)
**1-D histogram with a float per channel (see [TH1](https://root.cern.ch/doc/master/classTH1.html "TH1 is the base class of all histogram classes in ROOT.") documentation)**\
A ROOT class representing a 1D histogram:
- **T** = ROOT class
- **H1** = 1-dimensional histogram
- **F** = bin contents are stored as `float`

[[TH1 Class Reference]]

**`*`**  
The object is passed or returned as a **pointer**, common in ROOT/C++ for dynamically-allocated objects.

`TH1F*` refers to a **pointer to a ROOT histogram object**, specifically a **1-dimensional histogram with float (32-bit) bin contents**.
A `TH1F*` gives you a histogram that has:
- **One axis** (typically x = time, ADC value, or charge)
- **Float bin values**
- Standard ROOT histogram features (axis labels, plotting, statistics, integrals, fits…)


## [◆](https://root.cern.ch/doc/master/classTH1F.html#a958c4845a7cc935bae03b5578c4267c0) TH1F() [2/6]

| TH1F::TH1F                                                                                            |           |
| ----------------------------------------------------------------------------------------------------- | --------- |
| [const](https://root.cern.ch/doc/master/TCollection_8h.html#ab36279cd943b06d94ecec8a2a10110f7) char * | _name_,   |
| [const](https://root.cern.ch/doc/master/TCollection_8h.html#ab36279cd943b06d94ecec8a2a10110f7) char * | _title_,  |
| [Int_t](https://root.cern.ch/doc/master/RtypesCore_8h.html#a2f6a60bd1cf0af65f2bcef4098d623b8)         | _nbinsx_, |
| [Double_t](https://root.cern.ch/doc/master/RtypesCore_8h.html#ab9b5334647b78ec4256db251e3ae1fc6)      | _xlow_,   |
| [Double_t](https://root.cern.ch/doc/master/RtypesCore_8h.html#ab9b5334647b78ec4256db251e3ae1fc6)      | _xup_ )   |

Create a 1-Dim histogram with fix bins of type float (see [TH1::TH1](https://root.cern.ch/doc/master/classTH1.html#a3e45a923ef725a537b4f08709aff6aaa) for explanation of parameters) 

Definition at line [10256](https://root.cern.ch/doc/master/TH1_8cxx_source.html#l10256) of file [TH1.cxx](https://root.cern.ch/doc/master/TH1_8cxx_source.html).