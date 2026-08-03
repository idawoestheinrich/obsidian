This [page](https://wavecatcher-analysis.web.cern.ch/index.html) serves as documentation of the waveform analysis framework `wavecatcher-analysis` for WaveCatcher setups in the experimental elementary particle physics group at the Institute of Physics at Humboldt University of Berlin.   
  
You can find the documentation of the functions and variables at [ReadRun Class Reference](https://wavecatcher-analysis.web.cern.ch/classReadRun.html)
Installation instructions can be found at [https://cscharf-hub.github.io/wavecatcher-analysis/](https://cscharf-hub.github.io/wavecatcher-analysis/)
The source code is available at [https://github.com/cscharf-hub/wavecatcher-analysis](https://github.com/cscharf-hub/wavecatcher-analysis)

### Understanding Basic functions with ChatGPT
*ReadRun* is the main class for offline analysis of waveform data recorded with WaveCatcher (or compatible hardware) via wavecatcher-analysis. It handles reading raw binary data files, storing waveforms, and providing a wide array of functions for baseline correction, charge/time extraction, filtering, plotting, and data saving.

## 🔧 Key Methods / Functions in ReadRun
Here is a breakdown of many of the methods you listed — grouped by their purpose (baseline correction, waveform retrieval & time/charge measurement, filtering, plotting/diagnostics, I/O).
### Baseline Correction & Preprocessing
- **`CorrectBaseline(float tCut, float tCutEnd = -999)`**  
    Applies a simple / constant baseline correction to all waveforms: uses the mean in the time window from t = 0 to t = tCut (or between tCut and tCutEnd if provided) as the DC offset. Good for simple cases with low noise/background. [wavecatcher-analysis.web.cern.ch](https://wavecatcher-analysis.web.cern.ch/classReadRun.html?utm_source=chatgpt.com)
- **`CorrectBaseline_function(vector<float>& waveform, float tCut, float tCutEnd, int waveform_index)`**  
    Internal helper used by `CorrectBaseline()`. It applies the same baseline-correction algorithm on a single waveform (used internally). [wavecatcher-analysis.web.cern.ch](https://wavecatcher-analysis.web.cern.ch/classReadRun.html?utm_source=chatgpt.com)
- **`CorrectBaselineMin(vector<float> window, double sigma=0, int smooth_method=2)`**  
    More advanced baseline correction: searches (within a specified time range/window) for the region where the sum (or mean) of the waveform is minimal — i.e. finding a portion before the real signal where the baseline is “quiet.” This is useful when the baseline may vary or the signal arrival is not precisely known, or when there's a high dark-count rate (e.g. with SiPMs) which could distort a simple constant-baseline. [wavecatcher-analysis.web.cern.ch](https://wavecatcher-analysis.web.cern.ch/classReadRun.html?utm_source=chatgpt.com)
- **`CorrectBaselineMinSlopeRMS(vector<float> window, double sigma=0, int smooth_method=2)`**  
    Even more sophisticated method: searches for regions where both the slope and fluctuation (RMS) of the waveform are minimal. That is, it looks for the most “flat/constant” region before the signal, in a defined search window, for baseline estimation. Good in noisy conditions or when baseline isn’t stable. [wavecatcher-analysis.web.cern.ch](https://wavecatcher-analysis.web.cern.ch/classReadRun.html?utm_source=chatgpt.com)
- **`Using_BaselineCorrection_in_file_loop`** (public attribute / flag)  
    If set to `true` before reading data, baseline correction will be applied _during_ the file-reading loop. Good for automation so you don’t have to manually correct after reading

### Waveform Retrieval & Basic Access
- **`ReadFile(string path, bool change_polarity=false, int change_sign_from_to_ch_num=9, string out_file_name="out.root", bool debug=false, long long max_nevents_to_read=-1)`**  
    Core I/O: reads raw `.bin` files produced by WaveCatcher in the given path, optionally changing signal polarity for certain channels, converting and storing the waveforms internally into a ROOT file. You can also limit how many events to read (for testing). [wavecatcher-analysis.web.cern.ch+1](https://wavecatcher-analysis.web.cern.ch/classReadRun.html?utm_source=chatgpt.com)
- **`Getwf(int channelnr, int eventnr, int color=1)`** and **`Getwf(int wfindex)`**  
    Retrieve the waveform histogram ([[TH1F Class Reference|TH1F]]) for a given channel & event, or via a direct waveform index. Useful when you want to inspect individual waveforms.
- **`getx<T>(float shift=0.)`** (static / template)  
    Provides the time-axis (in ns) for the bin centers of the waveform data (given the known sampling period). Useful for aligning, plotting, or further time-domain processing.

### Charge / Integral & Timing Extraction
- **`GetIntWindow(...)`**  
    For a given waveform (or histogram), this method identifies an integration window around the signal peak: typically finds the maximum in a time range (start → end), then returns indices corresponding to `t_max - windowlow, t_max + windowhi`. Used to define integration bounds for charge (or amplitude) extraction. Several overloads exist (e.g. accepting raw waveform vs histogram).
- **`GetPeakIntegral(TH1F* his, float windowlow, float windowhi, float start, float end, int channel_index=0)`**  
    Computes the integral (or amplitude, if start/end = 0) around the peak according to the integration window determined via `GetIntWindow()`. This yields a “charge” or “signal amplitude” value per event per channel. 
- **`GetTimingCFD(float cf_r = .3, float start_at_t = 100, float end_at_t = 140, double sigma=0., bool find_CF_from_start = true, int smooth_method = 2, bool use_spline=false, bool verbose=false)`**  
    Performs timing extraction using Constant Fraction Discrimination (CFD): finds the time at which the signal reaches a fraction `cf_r` of its maximum within the given time window. Stores per-event timing results (e.g. CFD time, peak time, etc.) in internal data structures, for later use.
- **`IndexToTime(...)`** / **`TimeToIndex(...)`**  
    Utility methods to convert between sample/bin indices and time (ns), leveraging the known sampling period (`SP`). Useful when you want to define cuts or integration windows in time-domain rather than sample indices.
### Filtering / Event Selection / Cuts
- **`IntegralFilter(vector<float> thresholds, vector<bool> g_thr, float windowlow, float windowhi, float start=50, float end=250, bool use_AND_condition=false, bool verbose=false)`**  
    Applies a filter on collected events based on their integrated charge (or amplitude). For each (active) channel, you supply a threshold and a boolean (for whether to cut events with integral above or below that threshold). Only events that pass the threshold cut in all (or at least some) channels are kept (depending on `use_AND_condition`). Typically used to reject noise or dark-count events before further analysis.
- **`SkipEvent(int event_index, int channel_index = -1)`**  
    Mark a specific event (optionally for a specific channel) as “skipped” / excluded from analysis. Useful for manual or programmatic exclusion of bad events.
- **`UnskipAll()`**  
    Clears all skip flags — i.e. resets event selection so that all events (previously skipped or not) are included again. Useful if you want to re-run analysis after changing criteria. 
- (Note: there are also other skip-related mechanisms like per-channel thresholds or time-difference cuts between channels, but these are implemented via combinations of methods rather than a single “SkipEventsPerChannel” method documented for ReadRun.)

### Plotting, Histograms & Diagnostics
- **`BaselineCorrectionResults(int channel_index, int which, float rangestart=-5, float rangeend=5, int nbins=200)`**  
    Returns a histogram ([[TH1F Class Reference||TH1F*]]) showing the distribution of baseline correction values (offsets) for a given channel. Useful to inspect whether baseline correction worked properly (uniform baseline, no drift, etc.).
- **`ChargeCorrelation(...)`**  
    For two specified channels, plots a 2D histogram correlating their integrals (or amplitudes) event-by-event. Helps to check if e.g. signals in two channels tend to occur together — good for coincidence studies or cross-talk checks. 
- **`PlotChannelSums(bool smooth=false, bool normalize=false, double shift=0., double sigma=0., int smooth_method=2)`**  
    Plots the sum (over all events) of raw waveforms for each channel. Gives you a sense of the “average raw signal + noise” baseline / background. Useful as a first-look diagnostic. [
- **`PlotChannelAverages(...)`** _(implied, via similar naming — although not explicitly listed in your function list, but present in docs)_  
    After baseline correction and optional filtering, this will plot the average waveform per channel — more representative of the true signal shape after corrections.](https://wavecatcher-analysis.web.cern.ch/classReadRun.html?utm_source=chatgpt.com)
- **`PrintWFProjection(float from=0, float to=320, float rangestart=-50, float rangeend=50, int nbins=200)`**  
    Makes histogram projection of waveform amplitudes (over a given time window) for all (non-skipped) events and all channels. Helps inspect baseline stability: e.g., after baseline correction, projections should look like a stable Gaussian around zero if no signal; deviations or a long tail indicate many events with signal or noise.
- **`MaxDist(int channel_index, float from=0, float to=300)`**  
    Generates a 3D “map” of all individual waveforms for one channel, ordered by the maximum amplitude (or sum) — e.g. z-axis = amplitude, x/y = time & event index. This is useful for detailed visual inspection of waveform shapes across all events (for small datasets). Good for debugging.
- **`PrintSkippedEvents()`**  
    Lists all events that were skipped (by filtering or cuts) — helpful for diagnostics / verifying selection.
- **`PrintTimeDist(float from=0, float to=300, float rangestart=0, float rangeend=300, int nbins=100, int which=0, float cf_r=.3)`**  
    Plots histograms of event times — can be time-of-maximum, CFD-based time, or rise-time (10%–90%) depending on argument `which`. Useful for timing studies or checking time resolution / jitter.
- **`ShiftAllToAverageCF()`**  
    After you have obtained per-event CFD times (via `GetTimingCFD()`), this method shifts all waveforms so that their “start times” align to the average signal start (per channel). Useful if you want to overlay or average pulses in a consistent time frame (e.g. to get average pulse shape). 
- **`SaveChargeLists(float windowlow = 20, float windowhi = 80, float start = 0, float end = 300, bool negative_vals = true)`**  
    After analysis and filtering, this saves the “charge” (or amplitude) values of all events & channels into [[TGraph Class Reference|TGraph objects]] in a ROOT file, for further offline analysis/plotting. Skipped events are omitted. Negative values can optionally be reset to zero.
## 🧮 Internal Data Members / Attributes (relevant for understanding behavior)
These define the state of a ReadRun instance and affect how methods work or how results are stored.
- `active_channels` — list of which channels are active (i.e. recorded) in your data set. 
- `binNumber` — number of samples (bins) per waveform (usually 1024 for WaveCatcher) 
- `SP` (and `SP_inv`) — sampling period (ns per bin), e.g. 0.3125 ns (for 3.2 GS/s), used to convert between bin index and time.
- `rundata` — internal storage of all waveforms (e.g. vector of vectors) after reading with `ReadFile()`.
- `baseline_correction_result` — stores results of baseline correction per event per channel. 
- `timing_results` — stores timing results (e.g. CFD times, peak times, etc.) after `GetTimingCFD()`
- `skip_event` — boolean vector indicating which events are excluded (skipped) from analysis after filtering. 
And other metadata like number of events (`nevents`), number of waveforms (`nwf`), data path, etc., that govern how data is handled. 