@property

def filename(self):

return self.datamanager.filename

  

@property

def foldername(self):

return self.datamanager.foldername

  

# Hardware Delegation Wrappers

def connect_hardware(self): return self.hardware.connect_hardware()

def configure_scope(self): return self.hardware.configure_scope()

def cleanup(self): return self.hardware.cleanup()

def write_read(self, cmd): return self.hardware.write_read(cmd)

def motor_on(self): return self.hardware.motor_on()

def motor_off(self): return self.hardware.motor_off()

def move_home(self): return self.hardware.move_home(self.j)

def step_down(self): return self.hardware.step_down()

def move_WOM_top(self): return self.hardware.move_WOM_top()

def rotate_step(self): return self.hardware.rotate_step()

  

#Acquisition Delegation Wrappers

def heatup(self, deltaT_in = 7.25, deltaT_out = 8): return self.acquisition.heatup(deltaT_in = deltaT_in, deltaT_out = deltaT_out)

def measurement_without_WOM(self): return self.acquisition.measurement_without_WOM()

def getdata(self, ch): return self.acquisition.getdata(ch)

def measure_position(self, j, i): return self.acquisition.measure_position(j, i)

def run_darkcount_scan(self, darkcount, external_trigger):

return self.acquisition.run_darkcount_scan(darkcount, external_trigger)

def run_scan(self): return self.acquisition.run_scan()

def run_longterm(self, darkcount = True, external_trigger=False): return self.acquisition.run_longterm(darkcount = darkcount, external_trigger = external_trigger)

def run(self): return self.acquisition.run()

  

#Analysis Delegation Wrappers - Signal Processing

def riemann_sum_peak(self, data, int_window_min, int_window_max):

return self.signal_processor.riemann_sum_peak(

data, int_window_min, int_window_max

)

@staticmethod

def gaussian(x, mean, height, sigma):

return self.signal_processor.gaussian(x, mean, height, sigma)

@staticmethod

def EMG(x, mean, height, sigma, tau):

return self.signal_processor.EMG(x, mean, height, sigma, tau)

@staticmethod

def correct_baseline_min(waveform, window, sigma, smooth_method):

return self.signal_processor.correct_baseline_min(waveform, window, sigma, smooth_method)

@staticmethod

def gain(T, Vset, dVset, dT):

return self.signal_processor.gain(T, Vset, dVset, dT)

def create_baseline_data(self, window=(20, 0, 100), sigma=0, smooth_method=2):

return self.signal_processor.create_baseline_data(window=window, sigma=sigma, smooth_method=smooth_method)

  

def grouped_mean_std(self, value_col, group_col,

step_size=6.55, ny=None):

return self.signal_processor.grouped_mean_std(self, value_col, group_col,

step_size=step_size, ny=ny)

  

def calculate_eventwise_ratios(self):

return self.signal_processor.calculate_eventwise_ratios()

  

def apply_sipm_corrections(self, Vset, dVset, dT):

return self.signal_processor.apply_sipm_corrections(Vset, dVset, dT)

  
  

# Data IO Delegation Wrappers - DataManager

def save_metadata(self): return self.datamanager.save_metadata()

@classmethod

def read_metadata(cls, folder): return DataManager.read_metadata(folder)

def savecsv(self, name="integrated_data"):

data = self.baseline_integrated_data if name == "baseline_integrated_data" else self.integrated_data

return self.datamanager.savecsv(data, name=name)

def savebin(self, name="waveforms"):

return self.datamanager.savebin(name=name)

  

def readbin(self, mult=1, name="waveforms"):

return self.datamanager.readbin(self.ni, self.nj, self.rep, self.frame_length_max, mult=mult, name=name)

  

@classmethod

def load(cls, filename, redo=False, window=(20, 0, 100), sigma=0, smooth_method=2, bin_file = True, Vset = 40.7, dVset = 0.1, dT = 0.1):

return cls.datamanager.load(filename, redo=redo, window=window, sigma=sigma, smooth_method=smooth_method, bin_file=bin_file, Vset=Vset, dVset=dVset, dT=dT)

  

#Vizualization Delegation Wrappers - Plotter

def init_plotting(self):

return self.visualizer.init_plotting()

def update_example_waveform(self, waveforms, j, i, ch):

return self.visualizer.update_example_waveform(waveforms, j, i, ch)

def plot_temperature_over_time(self):

return self.visualizer.plot_temperature_over_time()

def plot_integral_over_time(self, PM):

return self.visualizer.plot_integral_over_time(PM)

def heatmap_WOM(self, ch1="PMT_ratio_in", ch2=None, vmin=None, vmax=None,

step_size=6.55, colorlabel=None, title=None, baseline_subtract=True,

normalize=False, remove_rows=[0,0]):

return self.visualizer.heatmap_WOM(ch1=ch1, ch2=ch2, vmin=vmin, vmax=vmax, step_size=step_size, colorlabel=colorlabel, title=title, baseline_subtract=baseline_subtract, normalize=normalize, remove_rows=remove_rows)

def light_yield_1dim(self, ch1= "PMT_in", ch2 = "SiPMin_in", ch3="SiPMout_in"):

return self.visualizer.light_yield_1dim(ch1=ch1, ch2=ch2, ch3=ch3)

def charge_spectrum(self, ch="PMT_ratio_in", bins=90, vmin=None, vmax=None):

return self.visualizer.charge_spectrum(ch=ch, bins=bins, vmin=vmin, vmax=vmax)

def plot_waveforms_position(self,

i = 0,

j = 0,

PM=["PMT_in"],

baseline_corrected = False,

reps = None,

plot_integration_window = False,

plot_mean = False,

legend = True,

title = False

):

return self.visualizer.plot_waveforms_position(i=i, j=j, PM=PM, baseline_corrected=baseline_corrected, reps=reps, plot_integration_window=plot_integration_window, plot_mean=plot_mean, legend=legend, title=title)