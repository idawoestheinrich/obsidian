- One function that adds up eventwise the waveforms of a number of channels given by an int array 
```cpp
/////////////////////////////////////////////////////////////// Paul's functions ///////////////////////////////////////////////////////////////

  

/// @brief add up several waveforms for one event

/// @param sig_channel_indices indices of all channels that should be added together, f.e. individual WOMs or all channels of a cell

/// @param event_nr event number that should be added up

/// @return sum waveform (TH1F*)

TH1F* TestBeam::eventWFsum(std::vector<int> sig_channel_indices, int event_nr) {

auto output = Getwf(sig_channel_indices[0], event_nr);

for (int i = 1; i < int(sig_channel_indices.size()); i++) {

output->Add(Getwf(sig_channel_indices[i], event_nr));

}

return output;

}

///////////////////////////////////////////////////////////////// Ida + Chat GPT

/// @brief add up several waveforms for all events

/// @param sig_channel_indices indices of all channels that should be added together, f.e. individual WOMs or all channels of a cell

/// @return vector of summed waveform vector<TH1F*> that is nevents long

std::vector<TH1F*> TestBeam::WFsum(const std::vector<int>& sig_channel_indices, const TString& base_name = "SummedWF")

{

std::vector<TH1F*> summed_waveforms;

// Loop over all events

for (int j = 0; j < nevents; j++) {

// Use eventWFsum to sum the channels for this event

auto sum_histo = eventWFsum(sig_channel_indices, j)

summed_waveforms.push_back(sum_histo);

}

return summed_waveforms;

}
```
# Modify Christians ChargeSpectrum

One Function hat calculates and plots the charge spectrum for that sum

```cpp
///////// First attempt Charge Spectrum Sum ////

/// @brief Histogram of the "charge" spectrum for the sum of multiple channels

/// See PrintChargeSpectrum() for parameters.

///

/// @return Histogram for the sum of multiple channels.

  

TH1F* TestBeam::ChargeSpectrumSum(vector<int> channel_indices, float windowlow, float windowhi, float start, float end, float rangestart, float rangeend, int nbins) {

TString name(Form("channel_sum_Ch_%02d-Ch%02d", active_channels[channel_indices[0]], active_channels[channel_indices.back()]));

auto h1 = new TH1F(name.Data(), name.Data(), nbins, rangestart, rangeend);

  

float pedestal = 0;

float gain = 1;

/// if (channel_index < static_cast<int>(PrintChargeSpectrum_cal.size())) {

/// if (PrintChargeSpectrum_cal[channel_index][0] != 0) gain = PrintChargeSpectrum_cal[channel_index][0];

// if (PrintChargeSpectrum_cal[channel_index][1] != 1) pedestal = /// PrintChargeSpectrum_cal[channel_index][1];

// }

float i_gain = 1. / gain;

  
// create temporary histo per thread

vector<TH1F*> h1_thread;

int n_threads = omp_get_max_threads();

h1_thread.resize(n_threads);

for (int t = 0; t < n_threads; ++t) h1_thread[t] = new TH1F("", "", nbins, rangestart, rangeend);

  

#pragma omp parallel

{

int t_id = omp_get_thread_num();

TH1F* hlocal = h1_thread[t_id];

  

#pragma omp for

for (int j = 0; j < nevents; ++j) {

float integral_value_sum = 0;

  

for (int channel_index : channel_indices) {

if (!SkipEvent(j, channel_index)) {

float integral_value = GetPeakIntegral(rundata[GetWaveformIndex(j, channel_index)], windowlow, windowhi, start, end, channel_index);

integral_value_sum += (integral_value - pedestal) * i_gain;

}

}

hlocal->Fill(integral_value_sum);

}

}

// merge

for (auto htmp : h1_thread) {

h1->Add(htmp);

delete htmp;

}

return h1;

}
```


# Editing PrintChargeSpectrum
```cpp
/// @brief Plots the "charge" spectrums of the sum of some given channels

///

/// For each event integrate in range ("start", "end") from t_max - "windowlow" to t_max + "windowhi" for each of the given channels,

/// and than sum the integrals for each event.

/// Return the charge histogram with x range ("rangestart", "rangeend") and the number of bins "nbins". \n

/// It is not really charge, but either amplitude (mV) or integral (mV x ns).

/// See ChargeSpectrumSum() and GetIntWindow(). \n

/// Can be normalised to the number of photoelectrons by defining the calibration values in PrintChargeSpectrum_cal.

///

/// \image html PrintChargeSpectrum.png "Simple example of the integrated signals for a single channel. The resulting integrated signals are fitted with a Landau-Gauss convolution (-> energy deposition of a minimum ionizing particle in a thin absorber). Code in example." width=75%

///

/// \image html cosmics-fit-example.png "Integrated signals for a SiPM in blue and a fit with the fit function Fitf for SiPMs missing after-pulses and dark counts in red. The spectrum is not well fit by the simplified model. You can try different fit models in the example cosmics-fit.ipynb." width=50%

///

/// @param channel_indices vector of indices of all channels that should be summed

/// @param windowlow Integrate from "windowlow" ns from max...

/// @param windowhi ...to "windowhi" ns from max.

/// @param start Find max from "start" in ns...

/// @param end ...to "end" in ns.

/// @param rangestart Plot x range start

/// @param rangeend Plot x range end

/// @param nbins Number of bins of histogram

/// @param fitrangestart Fit range start

/// @param fitrangeend Fit range end

/// @param max_channel_nr_to_fit Fit only channels with index < "max_channel_nr_to_fit". Set to -1 to skip fitting.

/// @param which_fitf Choose fit function: \n

/// 0 - do not fit \n

/// 1 - Fitf_langaus: landau gauss convolution for large number of photons \n

/// 2 - Fitf_biased: if pedestal is biased because of peak finder algorithm \n

/// 3 - Fitf_full: SiPM fit function with exponential delayed after pulsing \n

/// 4 - Fitf_PMT_ideal: ideal %PMT fit function \n

/// 5 - Fitf_PMT: %PMT fit function \n

/// 6 - Fitf_PMT_pedestal: %PMT fit function with biased pedestal \n

/// 7 - Fitf_plus_DC: default SiPM fit function + dark count spectrum (for lots of false triggers) \n

/// else - Fitf: default SiPM fit function \n

/// @param use_log_y Set all y axes to log scale (for dark count spectra)

void TestBeam::PrintChargeSpectrumSum(vector<int> channel_indices, float windowlow, float windowhi, float start, float end, float rangestart, float rangeend, int nbins, float fitrangestart, float fitrangeend, int max_channel_nr_to_fit, int which_fitf, bool use_log_y) {

// print ReadRun::ChargeSpectrum for all channels optimized for SiPM signals

checkData();

cout << "Creating charge spectrum ..." << endl;

gStyle->SetOptStat("ne");

gStyle->SetOptFit(1111);

  

if (fitrangestart == 0.) fitrangestart = rangestart;

if (fitrangeend == 0.) fitrangeend = rangeend;

  

string ctitle("\"charge\" spectra" + to_string(PrintChargeSpectrum_cnt++));

//auto chargec = new TMultiGraph();

//chargec->SetTitle(ctitle.c_str());

  

float default_rangestart = -2000;

float default_rangeend = 30000;

if (default_rangestart > rangestart) default_rangestart = rangestart;

if (default_rangeend < rangeend) default_rangeend = rangeend;

int default_nbins = static_cast<int>((default_rangeend - default_rangestart) * nbins / (rangeend - rangestart));

  
  

// create histogram

auto his = ChargeSpectrumSum(channel_indices, windowlow, windowhi, start, end, default_rangestart, default_rangeend, default_nbins);

  

his->GetYaxis()->SetTitle("#Entries");

if (windowlow + windowhi > 0.) his->GetXaxis()->SetTitle("Integral in mV#timesns");

else his->GetXaxis()->SetTitle("Amplitude in mV");

  

//if (i < static_cast<int>(PrintChargeSpectrum_cal.size()) && PrintChargeSpectrum_cal[i][0] != 1) {

// cout << "Charge spectrum for channel index " << i << " will be normalized using a gain of "

// << PrintChargeSpectrum_cal[i][0] << " and a pedestal value of " << PrintChargeSpectrum_cal[i][1] << endl;

// his->GetXaxis()->SetTitle("Number of photoelectrons");

//}

//store the mean integral of each channel --> used for correction factors of phi_ew analysis

mean_integral.push_back(his->GetMean());

  

//fitting

if (max_channel_nr_to_fit > -1) {

if (which_fitf == 0) {}

else if (which_fitf == 1) { // landau gauss convolution for large number of photons

Fitf_langaus fitf;

int n_par = 4;

TF1* f = new TF1("fitf_langaus", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "Width"); f->SetParameter(0, 35);

f->SetParName(1, "MPV"); f->SetParameter(1, 1000);

f->SetParName(2, "Area"); f->SetParameter(2, 10000);

f->SetParName(3, "#sigma_{Gauss}"); f->SetParameter(3, 100);

//if (!PrintChargeSpectrum_pars.empty()) for (int j = 0; j < min(4, static_cast<int>(PrintChargeSpectrum_pars.size())); j++) f->SetParameter(j, PrintChargeSpectrum_pars[j]);

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

else if (which_fitf == 2) { // if pedestal is biased because of peak finder algorithm

Fitf_biased fitf;

int n_par = 9;

TF1* f = new TF1("fitf_biased", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "N_{0}"); f->SetParameter(0, his->Integral());

f->SetParName(1, "#mu"); f->SetParameter(1, 2.);

f->SetParName(2, "#lambda"); f->SetParameter(2, .04);

f->SetParName(3, "#sigma_{0}"); f->SetParameter(3, 2.1);

f->SetParName(4, "#sigma_{1}"); f->SetParameter(4, 3.4); //f->SetParLimits(4, 1.e-9, 1.e3);

f->SetParName(5, "Gain"); f->SetParameter(5, 30.); //f->FixParameter(5, 10.);

f->SetParName(6, "Pedestal"); f->SetParameter(6, 2.);

f->SetParName(7, "norm_{0}"); f->SetParameter(7, 0.7);

f->SetParName(8, "x_{0}"); f->SetParameter(8, 5.);

  

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

  

// get number of excess events in the pedestal in the fit region. To get the absolute number of excess events the full pedestal needs to be inside of the fit range (fitrangestart, fitrangeend)

//double excessEventsInPedestal = f->Integral(fitrangestart, fitrangeend)/.3125;

//f->SetParameter(7, 1.);

//excessEventsInPedestal -= f->Integral(fitrangestart, fitrangeend)/.3125;

//cout << "\nNumber of excess events in the pedestal within the fit range:\t" << excessEventsInPedestal << "\n\n";

}

else if (which_fitf == 3) { // SiPM fit function with exponential delayed after pulsing

Fitf_full fitf;

int n_par = 9;

TF1* f = new TF1("fitf", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "N_{0}"); f->SetParameter(0, his->Integral());

f->SetParName(1, "#mu"); f->SetParameter(1, 2.);

f->SetParName(2, "#lambda"); f->SetParameter(2, .04);

f->SetParName(3, "#sigma_{0}"); f->SetParameter(3, 2.1);

f->SetParName(4, "#sigma_{1}"); f->SetParameter(4, 3.4);

f->SetParName(5, "Gain"); f->SetParameter(5, 30.); //f->FixParameter(5, 40.);

f->SetParName(6, "Pedestal"); f->SetParameter(6, 2.);

f->SetParName(7, "#alpha"); f->SetParameter(7, .1); //f->FixParameter(7, .2);

f->SetParName(8, "#beta"); f->SetParameter(8, 80.); //f->FixParameter(8, 80);

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

else if (which_fitf == 4) { // ideal PMT fit function

Fitf_PMT_ideal fitf;

int n_par = 4;

TF1* f = new TF1("fitf", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "N_{0}"); f->SetParameter(0, his->Integral());

f->SetParName(1, "#mu"); f->SetParameter(1, 1.);

f->SetParName(2, "#sigma"); f->SetParameter(2, 5.);

f->SetParName(3, "gain"); f->SetParameter(3, 10.);

  

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

else if (which_fitf == 5) { // PMT fit function

Fitf_PMT fitf;

int n_par = 8;

TF1* f = new TF1("fitf", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "N_{0}"); f->SetParameter(0, his->Integral());

f->SetParName(1, "w"); f->SetParameter(1, .05); f->SetParLimits(1, 1.e-99, 4.e-1); //probability for type II BG

f->SetParName(2, "#alpha"); f->SetParameter(2, .05); f->SetParLimits(2, 1.e-99, 5.e-2); //coefficient of exponential decrease of typ II BG

f->SetParName(3, "#sigma_{0}"); f->SetParameter(3, 5.); f->SetParLimits(3, 1.e-9, 1.e3);

f->SetParName(4, "Q_{0}"); f->SetParameter(4, 0.);

f->SetParName(5, "#mu"); f->SetParameter(5, 1.);

f->SetParName(6, "#sigma_{1}"); f->SetParameter(6, 5.); f->SetParLimits(6, 1.e-9, 1.e3);

f->SetParName(7, "Q_{1}"); f->SetParameter(7, 10.);

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

else if (which_fitf == 6) { // PMT fit function with biased pedestal

Fitf_PMT_pedestal fitf;

int n_par = 9;

TF1* f = new TF1("fitf", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "A"); f->SetParameter(0, his->Integral());

f->SetParName(1, "w"); f->SetParameter(1, .05); f->SetParLimits(1, 1.e-9, 4.e-1); //probability for type II BG

f->SetParName(2, "#alpha"); f->SetParameter(2, .05); f->SetParLimits(2, 1.e-9, 5.e-2); //coefficient of exponential decrease of typ II BG

f->SetParName(3, "#sigma_{0}"); f->SetParameter(3, 5.); f->SetParLimits(3, 1.e-9, 1.e3);

f->SetParName(4, "Q_{0}"); f->SetParameter(4, 0.); f->SetParLimits(4, -1.e2, 1.e2);

f->SetParName(5, "#mu"); f->SetParameter(5, 1.); f->SetParLimits(5, 1.e-9, 1.e2);

f->SetParName(6, "#sigma_{1}"); f->SetParameter(6, 5.); f->SetParLimits(6, 1.e-9, 1.e3);

f->SetParName(7, "Q_{1}"); f->SetParameter(7, 10.); f->SetParLimits(7, 1.e-9, 1.e9);

f->SetParName(8, "A_{0}"); f->SetParameter(8, 1.); f->SetParLimits(8, 1.e-9, 1.e1);

  

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

else if (which_fitf == 7) { // default SiPM fit function + dark count spectrum (for lots of false triggers)

Fitf_plus_DC fitf;

int n_par = 9;

TF1* f = new TF1("fitf", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "A"); f->SetParameter(0, his->Integral());

f->SetParName(1, "w"); f->SetParameter(1, .05); f->SetParLimits(1, 1.e-9, 4.e-1); //probability for type II BG

f->SetParName(2, "#alpha"); f->SetParameter(2, .05); f->SetParLimits(2, 1.e-9, 5.e-2); //coefficient of exponential decrease of typ II BG

f->SetParName(3, "#sigma_{0}"); f->SetParameter(3, 5.); f->SetParLimits(3, 1.e-9, 1.e3);

f->SetParName(4, "Q_{0}"); f->SetParameter(4, 0.); f->SetParLimits(4, -1.e2, 1.e2);

f->SetParName(5, "#mu"); f->SetParameter(5, 1.); f->SetParLimits(5, 1.e-9, 1.e2);

f->SetParName(6, "#sigma_{1}"); f->SetParameter(6, 5.); f->SetParLimits(6, 1.e-9, 1.e3);

f->SetParName(7, "#mu_darkcount"); f->SetParameter(7, .1); f->SetParLimits(7, 1.e-9, 1.);

f->SetParName(8, "N_{0}_darkcount"); f->SetParameter(8, .05); f->SetParLimits(8, 1.e-9, .3);

  

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

else { // default SiPM fit function

Fitf fitf;

int n_par = 7;

TF1* f = new TF1("fitf", fitf, fitrangestart, fitrangeend, n_par); f->SetLineColor(3); f->SetNpx(1000);

  

f->SetParName(0, "N_{0}"); f->SetParameter(0, his->Integral());

f->SetParName(1, "#mu"); f->SetParameter(1, 2.);

f->SetParName(2, "#lambda"); f->SetParameter(2, .04);

f->SetParName(3, "#sigma_{0}"); f->SetParameter(3, 2.1);

f->SetParName(4, "#sigma_{1}"); f->SetParameter(4, 3.4);

f->SetParName(5, "Gain"); f->SetParameter(5, 30.); //f->FixParameter(5, 40.);

f->SetParName(6, "Pedestal"); f->SetParameter(6, 2.);

  

cout << "\n\n---------------------- Fit for channel sum ----------------------\n";

TFitResultPtr fresults = his->Fit(f, "LRS");

fit_results.push_back(fresults);

}

}

TString name(Form("ChargeSpectrum sum_%02d-%02d_%d", active_channels[channel_indices[0]], active_channels[channel_indices.back()], PrintChargeSpectrum_cnt));

root_out->WriteObject(his, name.Data());

his->Draw();

if (use_log_y) gPad->SetLogy();

}

////////////////////////////////////////////// Paul's shid: /////////////////

  

// needed for get SumSpectrum(), getTimings() and getTimingsIterative():

  

/// @brief add up several waveforms

/// @param sig_channel_indices indices of all channels that should be added together

/// @param event_nr event number that should be added up

/// @return sum waveform (TH1F*)

TH1F* TestBeam::sumUpWFs(std::vector<int> sig_channel_indices, int event_nr) {

auto output = Getwf(sig_channel_indices[0], event_nr);

for (int i = 1; i < int(sig_channel_indices.size()); i++) {

output->Add(Getwf(sig_channel_indices[i], event_nr));

}

return output;

}
```