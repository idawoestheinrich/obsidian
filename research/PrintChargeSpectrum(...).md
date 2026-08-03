---
tags:
  - topic/coding/cplusplus
aliases:
date:
---
This function:`void ReadRun::PrintChargeSpectrum(...)` is part of a C++ class called `ReadRun`.  
Its goal is to **analyze and plot the “charge spectrum”** (a histogram of measured charge or amplitude values) for multiple readout channels of a detector (like SiPMs or PMTs).  
It can also **fit** those histograms with physics models (Landau–Gaussian, SiPM, PMT models, etc.), and then store them in a ROOT file.

So conceptually:
> It takes waveform data → computes charge per channel → builds histograms → fits models → saves the results.

## ⚙️ Function signature
```C++
void ReadRun::PrintChargeSpectrum(     
float windowlow, float windowhi, float start, float end,     
float rangestart, float rangeend,     
int nbins, float fitrangestart, float fitrangeend, int max_channel_nr_to_fit, int which_fitf, bool use_log_y)`
```

That’s a lot of parameters!  
Here’s what they mean:

| Parameter                      | Meaning                                            |
| ------------------------------ | -------------------------------------------------- |
| `windowlow`, `windowhi`        | Integration window for the signal (in time)        |
| `start`, `end`                 | Time range to look at in the waveform              |
| `rangestart`, `rangeend`       | X-axis range for histograms                        |
| `nbins`                        | Number of bins in the histogram                    |
| `fitrangestart`, `fitrangeend` | Range of data to fit (subset of histogram)         |
| `max_channel_nr_to_fit`        | How many channels should be fitted                 |
| `which_fitf`                   | Which fitting model to use (0–7 different options) |
| `use_log_y`                    | Whether to use a logarithmic Y-axis on the plots   |
## 🧩 Step-by-step (Python-style explanation)
### Step 1. Data check and setup
```C++
checkData(); cout << "Creating charge spectrum ..." << endl;
```
- `checkData()` makes sure data is loaded.
- `cout` is like `print()` in Python.

Then it configures the [ROOT plotting style](https://root.cern.ch/doc/master/classTPaveStats.html):
```C++
gStyle->SetOptStat("ne"); gStyle->SetOptFit(1111);
```
→ These control what info appears on ROOT plots (statistics, fit parameters, etc.).

### Step 2. Prepare canvas for drawing
ROOT draws graphs on canvases (like matplotlib figures).
```C++
auto chargec = new TCanvas(ctitle.c_str(), ctitle.c_str(), 600, 400); Helpers::SplitCanvas(chargec, active_channels, plot_active_channels); 
```
- `TCanvas` is like `plt.figure()`.
- The helper splits it into subplots for different channels. [[SplitCanvas]]

### Step 3. Parallel histogram creation
Here’s an interesting bit:
```C++
map<int, shared_future<TH1F*>> h1_future; 
for (int i = 0; i < nchannels; ++i) {    
	if (PlotChannel(i)) {         
			h1_future[i] = async(launch::async, [this, i, ...]() {             return ChargeSpectrum(i, ...);         
			});     
	}}
```
This is [[C++ multithreading]] — similar to using `concurrent.futures` in Python:

```python
from concurrent.futures import ThreadPoolExecutor futures = {i: executor.submit(self.ChargeSpectrum, i, ...)}
```
Each `ChargeSpectrum()` call creates a histogram (`TH1F`) for one detector channel.  
So this part computes histograms **in parallel**, speeding up processing.