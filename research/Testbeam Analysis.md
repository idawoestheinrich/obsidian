[[Charge Spectrum of sum]]
`chronos @ [2025-11-13~2025-12-19] #pink {Analysis} Testbeam Analysis GitLab | [[Testbeam Analysis]]`
1. Charge Integral spectrum to cut the pedestral of the cherencov - 37
	- The integration window 1ns 
2. Some events where we see two peaks
	- Two particle at the same time - *pile up*
	- Alessia has a "ugly" function to filter this
3. Things to show
	 -  Charge of the cell 
		 - Integrate over each channel and sum for each event all sipms 
		 - Charge_of_multiple_channels(start channel, end channel )
	- Charge for the individual WOMs for the "center" position 
		 - should look similar (same distance)
	- Check the individual channel - sum over all waveforms 
		- They will look the same for the measurement where we hit the WOM center
	- Plot the histogram of each channel - and show the channels for the WOMs side by side
**When you look at the SiPM charge you should see NO (very little) "empty" events **

[[Basic functions for testbeam-analysis]]
- What is the light yield in the two WOMs depending on the particle position
	- old testbeam vs new testbeam
	- What version of christians code did Andres use
		- [x] write an email to andres - 


**Detector L for Collaboration meeting** [[SBT Overview Talk]]
- detector light light yield ecke
	 wom und alle kombinationen von vom
	alle, mitte und oben, mitte und unten
	- ly vergleichen 
	- für gleiche postionen in den ecken
	- spektrum und mpv
	- bestimmen verhältnis mitte und ecke für alle positionen
- zeitauflösung
- paul weiß wie
- zeitauflösung zwischen berlin left/up und sum und smoothig


**Check if the optical coupling is good**
Ch3 is a bit lower
Ch6, Ch7 greased much higher ~800mVxns than glued ~600mVxns

Ch8, Ch9, Ch10, Ch11, Ch12, Ch13, Ch14, Ch15  glued much higher ~1000mVxns than greased ~600mVxns

Ch16, Ch17, Ch18, ~850mVxns vs ~950mVxns
Ch19, Ch22, Ch23 similar
Ch20, Ch 21, 700 vs 900




### 1. Upload data to eos
- navigate to the folder where the files are that you want to uplpad
```shell
scp - r <filename> <username>@lxplus.cern.ch:<path to file where you want to copy it to>
```
put filename for an individual file and \* for all of the files in the folder you are in 

#### Testbeam Nov2025
```shell
scp -r <filename> idwoesth@lxplus.cern.ch:/eos/experiment/ship/user/sbt/SBT_Testbeam_Nov2025_CellA
```

#### 2. Do the analysis
You can find code examples 
- Alessia
```shell
cd eos/user/a/abrignol/wavecatcher-analysis-TB25
```
- Fairhurst
```shell
cd /afs/cern.ch/user/r/rlyons/public/SHiP/testbeam
```
But the best is to start with christians example file and work from there

**How to remove stuff from eos:**
- Only the person who uploaded the file has the permission to remove it
```shell
ssh <username>@lxplus.cern.ch
```
- You can check if you are the owner in the file’s metadata:
```
ls -l <path_to_file>
```
If you are the owner you can remove the file by running 
```shell
eos rm <path_to_file>
```

**How to remove full folders**
If you are the owner you can remove the folder by running 
```shell
eos rm -r(f) <path_to_file>
```

### Analysis Alessia
This is how I read in the different measurements:
```
// Opening the txt file where all the data name are stored fstream inFile; // file to read the data -- dataname + searching for the maximum windows string nameInFile = "/afs/cern.ch/user/a/abrignol/public/analysis/TB24/File_data_withWOM.txt";
    inFile.open(nameInFile.c_str());
    if (!inFile) {
       cout << "Unable to open file " << nameInFile.c_str();
       exit(1);   // call system to stop
    }
    string empty;
    // if you want to skip some data at the beginning 
    for (int j=0;j<j_end;j++) {
           inFile >> empty;      //j_end come from you
    }
    inFile >> dataname;
    inFile.close();  
```



