[GitLab](https://gitlab.cern.ch/ship/ship-sbt/testbeam-analysis)
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
**When you look at the SiPM charge you should see NO (very little) "empty" events 


Read documentation 

```shell
xrdcp 
```
### List of basic functions to implement into the repository 

- Charge Spectrum of the eventwise sum of several channels
- Filter for two particle at the same time - *pile up*

- Plot the histogram of each channel ? Maybe as heatmap with SiPM Position?
- Function to plot several measurements? 