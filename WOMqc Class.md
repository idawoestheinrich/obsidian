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
	@staticmethod
    def riemann_sum_peak():
    @staticmethod
    def gaussian():
    @staticmethod
    def EMG(): #Exponential modified Gaussian distribution
    def heatup():
    def measurement_without_WOM(self):
    def getdata(): 
    def measure_position(self, j, i):
    def run_darkcount_scan(self, darkcount, e
    def run_scan(self):
    def save_metadata(self):
    def savecsv(self, name = "integrated_data"):#save in different format
    def savebin(self, name = "waveforms"):
    def cleanup(self):
    def create_baseline_data():#should maybe not save everything
    def init_plotting(self):
    def grouped_mean_std(self, value_col, group_col) #should also be able to work on not eventwise data
    def calculate_eventwise_ratios(self):#should maybe not save everything in files
    def update_example_waveform(
    def plot_temperature_over_time(self):
    def plot_integral_over_time(self, PM):
    def heatmap_WOM() # should be able to relabel the 
    def light_yield_1dim()
    def charge_spectrum()
    def plot_waveforms_position()
    @staticmethod
    def correct_baseline_min(waveform, window, sigma, smooth_method):
    @staticmethod
    def correct_baseline_min_not_vectorized(waveform, window=(20, 10, 90), sigma=0, smooth_method=2):
        """
        Baseline correction using minimum-sum search over a moving window.
        """
        wf = np.array(waveform, dtype=float)
        # Converts the input waveform to a float numpy array.

        n = len(wf)
        # Gets the length of the waveform.

        # --- Optional smoothing ---
        if sigma > 0:
            if smooth_method == 0:
                # Simple running average (boxcar)
                kernel = np.ones(int(2 * sigma + 1)) / (2 * sigma + 1)
                # Creates a boxcar kernel of width 2*sigma+1.
                wf = np.convolve(wf, kernel, mode='same')
                # Applies running average smoothing.
            elif smooth_method == 2:
                wf = gaussian_filter1d(wf, sigma=sigma)
                # Applies Gaussian smoothing.

        # --- Extract window parameters ---
        length, start, end = window
        # Unpacks window parameters: averaging length, start, end.

        start = max(0, int(start))
        # Ensures start index is not negative.

        end = min(n - length, int(end))
        # Ensures end index does not exceed waveform length.

        # --- Search for the minimum average ---
        means = np.array([
            np.mean(wf[i:i + length])
            for i in range(start, end)
        ])
        # For each window position, computes the mean value.

        min_index_local = np.argmin(np.abs(means))
        # Finds the index of the minimum mean value.

        min_index = start + min_index_local
        # Converts local index to global index in waveform.

        # --- Determine baseline value ---
        baseline_value = means[min_index_local]
        # Gets the minimum mean value as the baseline.

        corrected = wf - baseline_value
        # Subtracts the baseline value from the waveform.

        return corrected, baseline_value, min_index
        # Returns the corrected waveform, baseline value, and baseline index.

    @staticmethod
    def gain(T, Vset, dVset, dT):
        """
        Calculate the gain of the SiPM based on the applied voltage and temperature.
        Slope:     m = (7.838615914826629 ± 0.001483241521232523) e5 1/V
        Intercept: b = (9.809975406709395 ± 0.004662604806026203) e5

        #Gain(Overvoltage) = (7.83861591 ± 0.00148324)*1e5/V * Overvoltage + (9.80997541 ± 0.00466260)*1e5 -  at 25 degrees C - 0.12 V geringere overvoltage - 12% weniger Gain pro 4 Grad Temperaturerhöhung
        #Breakdownvoltage(T) = (39.16+-0.01)V + (33.66e-3+-0.30e-3) V/K * T
        #If the Voltage is set to Vset than the 
        # Overvoltage is Vset-Breakdownvoltage(T) 
        # = (Vset+-0.1)V - (39.16+-0.01)V - (33.66e-3+-0.30e-3) V/K * T 

        # Gain over Temperature: 
        # Gain(T) = (7.83861591 ± 0.00148324)*1e5/V * ((Vset+-0.1)V - (39.16+-0.01)V - (33.66e-3+-0.30e-3) V/K * T) + (9.80997541 ± 0.00466260)*1e5 

        # Gain(T) = A * (Vset - B - C * T) + D
        # A = 7.83861591e5 #
        # dA = 0.00148324e5
        # B = 39.16
        # dB = 0.01
        # C = 33.66e-3
        # dC = 0.30e-3
        # D = 9.80997541e5
        # dD = 0.00466260e5
        # dT = 0.1
        # dVset = 0.1
        # dGain(T) = \sqrt((dA * (Vset + B + C*T))^2 + (A * dVset)^2 + (dB*A)^2 + (dC * T*A)^2 + (dT*C*A)+ (dD)^2) 
        # SiPM output should proportional to Gain(T) and therefore the SiPM output should decrease with increasing temperature.

        Parameters
        ----------
        T : float/array of floats
            Temperature of the PCB in degrees Celsius.

        Returns
        -------
        Gain : float
            Calculated gain.
        dGain: float    
            Calculated uncertainty of the gain.
        """
        Gain_per_volt = 7.83861591e5 #Gain change per Volt [V^-1] Fit parameter determined from Gain_overvoltage.csv
        dGain_per_volt = 0.00148324e5 
        Breakdown_voltage = 39.16 #Breakdown voltage [V] constant Fit parameter determined from breackdownvoltage_temperature.csv
        dBreakdown_voltage = 0.01
        Breakdown_per_K = 33.66e-3 #Breakdown voltage change per Kelvin [V/K] Fit parameter determined from breackdownvoltage_temperature.csv
        dBreakdown_per_K = 0.30e-3
        Gain_const = 9.80997541e5 #Gain constant [V] Fit parameter determined from Gain_overvoltage.csv
        dGain_const = 0.00466260e5

        Gain = Gain_per_volt * (Vset - Breakdown_voltage - Breakdown_per_K * T) + Gain_const
        dGain = np.sqrt((dGain_per_volt * (Vset - Breakdown_voltage - Breakdown_per_K * T))**2 + (Gain_per_volt * dVset)**2 + (dBreakdown_voltage * Gain_per_volt)**2 + (dBreakdown_per_K * T* Gain_per_volt)**2 + (dT * Breakdown_per_K * Gain_per_volt)**2 + (dGain_const)**2)
        return Gain, dGain

    def apply_sipm_corrections(self, Vset, dVset, dT):
        '''
        - calculate gain
        - first correct all SiPM values with the gain 
        - Normalize SiPM values to the 999 measurement if it exists
        '''
        #name == "integrated_data":   
        #    integrated_data = self.integrated_data
        #elif name == "baseline_integrated_data":    
        #    integrated_data = self.baseline_integrated_data

        self.baseline_integrated_data["gain_out"], self.baseline_integrated_data["dgain_out"] = gain(self.baseline_integrated_data["temp_out"], Vset = Vset, dVset = dVset, dT = dT)
        self.baseline_integrated_data["gain_in"], self.baseline_integrated_data["dgain_in"] = gain(self.baseline_integrated_data["temp_in"], Vset = Vset, dVset = dVset, dT = dT)

        PM = ["SiPMout_in", "SiPMin_in", "SiPMout_out", "SiPMin_out"]
        Gain = ["gain_out", "gain_in", "gain_out", "gain_in"]
        for pm, g in zip(PM, Gain):  
            gain_matrix = np.stack(self.baseline_integrated_data[g].values)[:, None , None]
            #print(np.shape(gain_matrix), gain_matrix)
            dgain_matrix = np.stack(self.baseline_integrated_data[f"d{g}"].values)[:, None , None]
            ratio = self.baseline_integrated_data_eventwise[pm] / gain_matrix
            #for i in range(3):
                #print("temp_out", self.baseline_integrated_data["temp_out"][i], pm, "self.baseline_integrated_data_eventwise", self.baseline_integrated_data_eventwise[pm][i], "gain_matrix", gain_matrix[i], "ratio", ratio[i])
            ratio_err = np.abs(ratio) * np.sqrt(
                    (dgain_matrix/ gain_matrix)**2
                )

            self.baseline_integrated_data_eventwise[f"{pm}_gain"] =  ratio
            self.baseline_integrated_data_eventwise[f"{pm}_gain_err"] = ratio_err


        if self.integrated_data["j"][0] == 9999:
            for pm in PM:
                ref = self.baseline_integrated_data_eventwise[f"{pm}_gain"][0][self.baseline_integrated_data_eventwise[pm][0]!= 0].mean()
                if ref != 0:
                    ratio = self.baseline_integrated_data_eventwise[f"{pm}_gain"][1:]/ref
                #ratio_err = np.abs(ratio) * np.sqrt(1/30*
                #                (self.baseline_integrated_data_eventwise[f"{pm}_std"][1:]/self.baseline_integrated_data_eventwise[pm][1:])**2 +
                #                (self.baseline_integrated_data_eventwise[f"{pm}_std"][0]/self.baseline_integrated_data_eventwise[pm][0])**2
                #            )
                    self.baseline_integrated_data_eventwise[f"{pm}_gain"][1:] = ratio
                else:
                    print(pm, "ref = 0", ref)
                #self.baseline_integrated_data_eventwise[f"{pm}_err"] = ratio_err


    '''
    LOADING BIN AND CSV FILES FOR ANALYSIS
    '''

    '''
    Used to read metadata from a previous measurement - should be used before loading bin or csv files
    md = WOMqc.read_metadata("foldername")
    qc = WOMqc(**md) 
    '''
    @classmethod
    def read_metadata(cls, folder):
        metadata = {}
        metadata_file =  Path("../data")/ Path(folder) / "metadata.txt"
        with open(metadata_file) as f:
            for line in f:
                line = line.strip()
                if not line or line.startswith("#"):
                    continue

                key, value = line.split(":", 1)
                value = value.strip()

                # type casting
                if value.lower() in ("true", "false"):
                    value = value.lower() == "true"
                else:
                    try:
                        value = int(value)
                    except ValueError:
                        try:
                            value = float(value)
                        except ValueError:
                            pass  # keep string

                metadata[key.strip()] = value
        return metadata
    
    """
    Read waveform binary data from file.

    Loads waveform arrays for all detector channels together with
    their corresponding scan coordinates (i, j).

    Takes:
        i : int
            Multiplier for number of scan positions.

        name : str
            Target waveform set:
                - "waveforms"
                - "baseline_waveforms"

    Returns:
        dict
            Dictionary containing waveform arrays and scan indices.

    Stores:
        self.waveforms
        or
        self.baseline_wf
    """
    def readbin(self, i = 1, name="waveforms"):
        filename = self.foldername / f"{self.filename}_{name}.bin"
        if name == "baseline_integrated_data_eventwise":    
            if self.integrated_data["j"][0] == 999:
                N, rep, frame_length = self.nj*self.ni*i+1, self.rep, 1
            else:
                N, rep, frame_length = self.nj*self.ni*i, self.rep, 1    
        else: 
            if self.integrated_data["j"][0] == 999:  
                N, rep, frame_length = self.nj*self.ni*i+1, self.rep, self.frame_length_max
            else:
                N, rep, frame_length = self.nj*self.ni*i, self.rep, self.frame_length_max    
        shape = (N, rep, frame_length)
        with open(filename, "rb") as f:
            j_arr = np.fromfile(f, dtype=np.int32, count=N)
            i_arr = np.fromfile(f, dtype=np.int32, count=N)
            PMT_LEDin_all     = np.fromfile(f, dtype=np.float32, count=np.prod(shape)).reshape(shape)
            SiPMin_LEDin_all  = np.fromfile(f, dtype=np.float32, count=np.prod(shape)).reshape(shape)
            SiPMout_LEDin_all = np.fromfile(f, dtype=np.float32, count=np.prod(shape)).reshape(shape)
            PMT_LEDout_all    = np.fromfile(f, dtype=np.float32, count=np.prod(shape)).reshape(shape)
            SiPMin_LEDout_all = np.fromfile(f, dtype=np.float32, count=np.prod(shape)).reshape(shape)
            SiPMout_LEDout_all= np.fromfile(f, dtype=np.float32, count=np.prod(shape)).reshape(shape)
        assert PMT_LEDin_all.shape == (N, rep, frame_length)
        assert j_arr.dtype == np.int32
        assert PMT_LEDin_all.dtype == np.float32

        data = {
            "j": j_arr,
            "i": i_arr,
            "PMT_in": PMT_LEDin_all,
            "SiPMin_in": SiPMin_LEDin_all,
            "SiPMout_in": SiPMout_LEDin_all,
            "PMT_out": PMT_LEDout_all,
            "SiPMin_out": SiPMin_LEDout_all,
            "SiPMout_out": SiPMout_LEDout_all,
        }
        if name == "waveforms":
            self.waveforms = data
        elif name == "baseline_waveforms":
            self.baseline_wf = data
        elif name == "baseline_integrated_data_eventwise":  
            self.baseline_integrated_data_eventwise = data     
        else:
            raise ValueError("Invalid waveforms attribute")
        return data
    
    def readcsv(self, name="integrated_data"):
        if name == "integrated_data":
            filename = self.foldername / f"{self.filename}_integrated.csv"
            self.integrated_data = pd.read_csv(filename)
            return self.integrated_data
        elif name == "baseline_integrated_data":
            filename = self.foldername / f"{self.filename}_baseline_integrated.csv"
            self.baseline_integrated_data = pd.read_csv(filename)
            return self.baseline_integrated_data
        else:
            raise ValueError("Invalid integrated data attribute")    
        

    """
    Load a WOMqc object including original and baseline corrected waveforms and corresponding integrated data.
    Steps:
        1. Reads metadata using `read_metadata()`.
        2. Creates the WOMqc object.
        3. Loads waveform binary data using `readbin()`.
        4. Loads integrated CSV data using `readcsv()`.

    Additionally attempts to load:
        - baseline-corrected waveforms
        - baseline-integrated data

    If the baseline data files do not exist,
    they are automatically generated using:
        create_baseline_data()

    Takes:
        filename : str
            Base filename of the measurement.
    And additional arguments for baseline data generation:
        window=(20, 0, 100), (integration window length, start index, end index)
        sigma= 0 (if > 0, applies smoothing before baseline correction),
        smooth_method=2 (running average), 2 (gaussian)
            
    Returns:
        WOMqc
            Fully initialized WOMqc object containing:
                - raw waveforms
                - integrated data
                - baseline-corrected waveforms
                - baseline-integrated data
    """
    @classmethod
    def load(cls, filename, redo=False, window=(20, 0, 100), sigma=0, smooth_method=2, bin_file = True, Vset = 40.7, dVset = 0.1, dT = 0.1):
        """
        Load a WOMqc object from metadata + stored data.
        """

        md = cls.read_metadata(filename)

        obj = cls(**md)
        obj.readcsv()
        if bin_file:
            obj.readbin()
            # Try loading baseline data
            try:
                obj.readbin(name="baseline_waveforms")
                obj.readbin(name="baseline_integrated_data_eventwise")
                obj.readcsv(name="baseline_integrated_data")
        
            # If files do not exist -> generate them
            except Exception:
            
                print("Baseline data not found. Generating...")

                obj.create_baseline_data(window=window, sigma=sigma, smooth_method=smooth_method)
                obj.apply_sipm_corrections(Vset = Vset, dVset=dVset, dT = dT)
                obj.calculate_eventwise_ratios()

            if redo:
                print("Redoing baseline correction with new parameters...")
                obj.create_baseline_data(window=window, sigma=sigma, smooth_method=smooth_method)

        return obj

    '''
--- RUN MEASUREMENT -----------------------------------------------------------------------------------
    '''
    """
    Run long-term darkcount / stability measurement.

    Executes a full automated acquisition sequence without spatial scanning:
        1. Cleans up previous hardware state
        2. Saves metadata
        3. Connects and configures hardware
        4. Runs darkcount or stability scan
        5. Saves results (CSV + binary)
        6. Optionally generates light-yield plots

    Error handling:
        - Logs failures
        - Attempts safe return to home position
        - Ensures hardware cleanup in all cases

    Modes:
        darkcount=True  → LED off reference measurement
        darkcount=False → stability measurement with LED on

    Returns:
        None
    """
    def run_longterm(self, darkcount = True):
        self.cleanup() 
        try:
            self.save_metadata()
            self.connect_hardware()
            self.logger.info(f"Connected Hardware")
            if darkcount:
                self.rec_time_min = 0
                self.rec_time_max = 1e-6
                self.frame_length_max = 1024
            if external_trigger:
                self.rec_time_min = 0.1e-6
                self.rec_time_max = 0.7e-6
                self.frame_length_max = 1024    
            self.configure_scope()
            self.logger.info(f"Configured Hardware")
            self.logger.info(f"Pulse LEDs for 20min")
            if self.heatup_roomtemp:
                self.heatup()    
            self.run_darkcount_scan(darkcount, external_trigger)
            self.savecsv()
            self.savebin()
            if self.plot_heatmap:
                self.light_yield_1dim()
                self.light_yield_1dim(ch1= "PMT_out", ch2 = "SiPMin_out", ch3="SiPMout_out")
        except Exception as e:
            self.logger.error("Measurement failed:", e)
            #self.move_home()
            self.cleanup()    
        finally:
            self.logger.info("Measurement completed successfully.")
            #self.move_home()
            self.cleanup() 

    """
    Run full spatial WOM scan measurement.

    Executes a 2D scan over (i, j) positions:
        1. Cleans up previous hardware state
        2. Saves metadata
        3. Connects and configures hardware
        4. Homes system and prepares scan position
        5. Runs full scan acquisition
        6. Saves results (CSV + binary)
        7. Optionally generates heatmaps

    Error handling:
        - Logs exceptions
        - Attempts safe return to home position
        - Ensures cleanup in all cases

    Returns:
        None
    """
    def run(self):
        self.cleanup() 
        try:
            self.save_metadata()
            self.connect_hardware()
            self.logger.info(f"Connected Hardware")
            self.configure_scope()
            self.logger.info(f"Configured Hardware") 
            self.motor_on() 
            self.move_home()
            self.logger.info(f"Move Home")
            if self.heatup_roomtemp:
                self.heatup()    
            self.measurement_without_WOM()
            response = self.step_down()
            self.logger.info(response)
            self.logger.info(f"Move to WOM Top")
            time.sleep(1)
            self.run_scan()
            self.savecsv()
            self.savebin()
            self.motor_off() 
            if self.plot_heatmap:
                self.heatmap_WOM(ch1="PMT_ratio_in", ch2="PMT_ratio_in_std", baseline_subtract= False)
                self.heatmap_WOM(ch1="SiPM_ratio_in", ch2="SiPM_ratio_in_std", baseline_subtract= False)
                self.heatmap_WOM(ch1="SiPM_ref_in", ch2="SiPM_ref_in_std", baseline_subtract= False)
        except Exception as e:
            self.logger.error("Measurement failed:", e)
            self.motor_on() 
            self.move_home()
            self.motor_off()    
            self.cleanup() 
            
        finally:
            self.motor_on() 
            self.logger.info("Measurement completed successfully.")
            self.move_home()
            self.motor_off()   
            self.cleanup()
```