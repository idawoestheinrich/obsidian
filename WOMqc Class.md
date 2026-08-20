
```python
class WOMqc:
    def __init__(self, device_ip, WOMname, ni, nj, rep, pulsewidth_ch1, pulsewidth_ch2, voltage_range_PMT,  voltage_range_SiPM , rec_time_min, rec_time_max, int_window_min_PMT, int_window_max_PMT, int_window_min_SiPM, int_window_max_SiPM, frame_length_max, sipm_voltage = 40.7, heatup_roomtemp = False, heatupmin = False,  plot_waveform=False, plot_heatmap = False, PMsoff= False, dry_run=False, date= None):
        self.device_ip 
        self.WOMname 
        self.ni 
        self.nj = nj #number of positions in j direction
        self.rep  = rep #number of waveforms taken per position rep
        self.pulsewidth_ch1 = pulsewidth_ch1 #what should be the pulse length for the inner LED
        self.pulsewidth_ch2 = pulsewidth_ch2 #what should be the pulse length for the outer LED
        
        self.voltage_range_PMT = voltage_range_PMT #voltage range of the Moku input channels "4Vpp", "400mVpp", ...
        self.voltage_range_SiPM = voltage_range_SiPM #voltage range of the Moku input channels "4Vpp", "400mVpp", ...
       
        self.rec_time_min  = rec_time_min #record time window min
        self.rec_time_max = rec_time_max #record time window max
        self.int_window_min_PMT = int_window_min_PMT #integration window relativ to maximum
        self.int_window_max_PMT = int_window_max_PMT
        self.int_window_min_SiPM = int_window_min_SiPM #integration window relativ to maximum
        self.int_window_max_SiPM = int_window_max_SiPM
        self.frame_length_max = frame_length_max #number of bins in the frame 

        self.sipm_voltage = sipm_voltage
        self.heatup_roomtemp = heatup_roomtemp
        self.heatupmin = heatupmin
        self.plot_waveform = plot_waveform #if true, plot example waveforms during the scan
        self.plot_heatmap = plot_heatmap #if true, plot heatmaps after the measurement

        self.dry_run = dry_run  #if true, no hardware is connected
        self.PMsoff = PMsoff

        self.date = date
        
        self.logger = logging.getLogger(self.__class__.__name__)    

        self.i = 0
        self.j = 0

        self.device = None
        self.arduino = None

        self.waveforms = None
        self.integrated_data = None

        self.baseline_wf = None
        self.baseline_integrated_data = None
        self.baseline_integrated_data_eventwise = None

        # Create data directory
        self.foldername.mkdir(parents=True, exist_ok=True)
        # 2️⃣ configure logger **here, inside the class**
        self.logger = logging.getLogger(self.__class__.__name__)
        self.logger.setLevel(logging.INFO)
        # Remove any default handlers to avoid duplicates
        if self.logger.hasHandlers():
            self.logger.handlers.clear()
        # Console handler
        ch = logging.StreamHandler()
        ch.setLevel(logging.INFO)
        ch.setFormatter(logging.Formatter("%(asctime)s | %(levelname)s | %(message)s"))
        # File handler — now self.foldername exists
        fh = logging.FileHandler(self.foldername / "logfile.log")
        fh.setLevel(logging.INFO)
        fh.setFormatter(logging.Formatter("%(asctime)s | %(levelname)s | %(message)s"))

        self.logger.addHandler(ch)
        self.logger.addHandler(fh)

    @property    
    def filename(self):
    @property    
    def foldername(self):
       
    
    def connect_hardware(self): 
    def configure_scope(self):       
    def write_read(self, command): 
    def motor_on(self):
    def motor_off(self):
    def move_home(self):
    def step_down(self):                     
    def move_WOM_top(self):
    def rotate_step(self):
    def riemann_sum_peak():
    def gaussian():
    def EMG(): #Exponential modified Gaussian distribution
    def heatup():
    def measurement_without_WOM(self):
    def getdata(): 
    def measure_position(self, j, i):
    def run_darkcount_scan(self, darkcount, e
    def run_scan(self):
    def save_metadata(self):
    def savecsv(self, name = "integrated_data"):# format
    def savebin(self, name = "waveforms"):
    def cleanup(self):
    def create_baseline_data():#not save everything
    def init_plotting(self):
    def grouped_mean_std(self, value_col, group_col) #not 
    def calculate_eventwise_ratios(self):#not save in files
    def update_example_waveform(
    def plot_temperature_over_time(self):
    def plot_integral_over_time(self, PM):
    def heatmap_WOM() # should be able to relabel the 
    def light_yield_1dim()
    def charge_spectrum()
    def plot_waveforms_position()
    def correct_baseline_min(
    def gain(T, Vset, dVset, dT):
    def apply_sipm_corrections(self, Vset, dVset, dT):
    def read_metadata(cls, folder):
    def readbin(self, i = 1, name="waveforms"):
    def load()
    def run_longterm(self, darkcount = True):
    def run(self):  
``` 
Seperate in 
WOMqc -41 functions
│
├── Hardware - 9 functions
│   ├── connect_hardware()
│   ├── configure_scope()
│   ├── write_read()
│   ├── motor_on()
│   ├── motor_off()
│   ├── move_home()
│   ├── step_down()
│   ├── move_WOM_top()
│   └── rotate_step()
│
├── Acquisition - 8 functions
│   ├── heatup()
│   ├── measurement_without_WOM()
│   ├── getdata()
│   ├── measure_position()
│   ├── run_darkcount_scan()
│   ├── run_scan()
│   ├── run_longterm()
│   └── run()
│
├── Analysis - 9 functions
│   ├── riemann_sum_peak()
│   ├── gaussian()
│   ├── EMG()
│   ├── correct_baseline_min()
│   ├── gain()
│   ├── create_baseline_data()
│   ├── grouped_mean_std()
│   ├── calculate_eventwise_ratios()
│   ├── apply_sipm_corrections()

│
└── DataManager - 6 functions
    ├── save_metadata()
    ├── savecsv()
    ├── savebin()
    ├── read_metadata()
    ├── readbin()
    └── load()

Plotter - 8 functions
├── init_plotting()
├── update_example_waveform()
├── plot_temperature_over_time()
├── plot_integral_over_time()
├── heatmap_WOM()
├── light_yield_1dim()
├── charge_spectrum()
└── plot_waveforms_position()