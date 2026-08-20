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
    def savecsv(self, name = "integrated_data"):
    def savebin(self, name = "waveforms"):
    def cleanup(self):
    def create_baseline_data():
    def init_plotting(self):
        plt.ion()  # interactive mode ON

        self.fig, self.ax = plt.subplots(1, 3, figsize=(12, 4))
        self.lines = []
        for i in range(3):
            line, = self.ax[i].plot([], [], lw=1)
            self.lines.append(line)

            self.ax[i].set_xlabel("Time [samples]")
            self.ax[i].set_ylabel("Voltage [V]")
            self.ax[i].set_title(f"Example waveform {i+1}")
            self.ax[i].grid(True)

        self.fig.tight_layout()


    """
    Calculate group-wise statistics from event-wise waveform data.

    This function operates on the event-wise integrated data produced by
    `calculate_eventwise_ratios()`. The data are grouped according to either
    the detector row (`i`) or column (`j`).
    For each group:
        4. All waveform-level values from all events belonging to that group
           are collected.
        5. The nested waveform arrays are flattened into a single 1D array.
        6. The mean, standard deviation, and standard error of the mean (SEM)
           are calculated.
    The SEM is calculated as:

        SEM = std / sqrt(N)
    where N is the total number of waveform-level measurements in the group.
    Parameters
    ----------
    value_col : str
        Name of the column to analyze
        (e.g. "PMT_out_ref", "PMT_in", ...).
    group_col : str
        Grouping variable. Must be either:
            - "i" : detector row
            - "j" : detector column
    step_size : float, optional
        Physical spacing between neighboring detector positions in mm.
    ny : int, optional
        Number of detector positions. If None, the number of unique groups
        is used.
    Returns
    -------
    y_phys : np.ndarray
        Physical coordinate corresponding to each group.
    groups : dict
        Dictionary containing all values grouped by i or j.
    group_means : list
        Mean value for each group.
    group_stds : list
        Standard deviation for each group.
    group_sem : list
        Standard error of the mean for each group.
    Raises
    ------
    ValueError
        If `group_col` is not "i" or "j".
    ValueError
        If event-wise data have not yet been generated by
        `calculate_eventwise_ratios()`.
    """

    def grouped_mean_std(self, value_col, group_col,
                     step_size=6.55, ny=None):
        # Check whether event-wise ratio data exist
        if "PMT_out_ref" in self.baseline_integrated_data_eventwise:

            # Only allow grouping by detector row or column
            if group_col not in ["i", "j"]:
                raise ValueError("group_col must be 'i' or 'j'")

            # Extract grouping variable (i or j)
            group_ids = self.baseline_integrated_data_eventwise[group_col]

            # Extract values to be analyzed
            values = self.baseline_integrated_data_eventwise[value_col]

            # Dictionary that will contain all values belonging
            # to a given i or j position
            groups = {}

            # -------------------------------------------------
            # Collect values for each group
            # -------------------------------------------------
            for val, gid in zip(values, group_ids):
                groups.setdefault(gid, []).append(val)
            # -------------------------------------------------
            # Calculate statistics for each group
            # -------------------------------------------------
            group_means = []
            group_stds = []
            group_sem = []
            for gid, vals in groups.items():

                # Flatten nested event/waveform structure
                vals = np.array(vals).flatten()

                # Mean value of the group
                group_means.append(vals[vals != 0].mean())

                # Standard deviation of the group
                group_stds.append(vals[vals != 0].std(ddof=1))

                # Standard error of the mean
                group_sem.append(
                    vals[vals != 0].std(ddof=1) / np.sqrt(len(vals[vals != 0]))
                )
            # Use number of groups if ny was not specified
            if ny is None:
                ny = len(groups)
            # -------------------------------------------------
            # Construct physical coordinate axis
            # -------------------------------------------------
            if group_col == "j":
                # Angular coordinate
                y_phys = np.linspace(0, 360, ny)

            else:
                # Longitudinal detector coordinate
                if (
                    "_in" in value_col
                    or "ref_in" in value_col
                    or "Noise_in" in value_col
                    or "norm_in" in value_col
                ):
                    y_phys = np.linspace(
                        202,
                        202 - ny * step_size,
                        ny
                    )

                elif (
                    "_out" in value_col
                    or "ref_out" in value_col
                    or "Noise_out" in value_col
                    or "norm_out" in value_col
                ):
                    y_phys = np.linspace(
                        195,
                        195 - ny * step_size,
                        ny
                    )

                else:
                    y_phys = np.linspace(
                        199,
                        199 - ny * step_size,
                        ny
                    )
            return (
                y_phys,
                groups,
                group_means,
                group_stds,
                group_sem
            )
        else:
            raise ValueError(
                "self.baseline_integrated_data_eventwise['PMT_out_ref'] "
                "does not exist.\n"
                "Please run calculate_eventwise_ratios() first."
            )   
    
    """
    Calculate event-wise signal ratios between selected detector channels
    and their corresponding reference channels.
    For each detector channel defined in `ratio_map`, the function:
    1. Integrates every waveform within each event using the appropriate
    integration window.
    2. Applies a sign correction for PMT channels because PMT pulses are
    recorded with negative polarity.
    3. Computes the ratio of the integrated signal to the integrated
    reference signal for every waveform in the event.
    4. Calculates the mean and standard deviation of these ratios within
    each event.
    5. Stores the event-wise mean ratios and their standard deviations in
    `self.baseline_integrated_data`.
    The resulting arrays are saved under:
        "{channel}_ref"      : mean ratio per event
        "{channel}_ref_std"  : standard deviation of ratios per event
    Returns
    -------
    PM_int : list of np.ndarray
        Integrated signal values for all processed events and channels.
        [0] - "PMT_in"
        [1] - "SiPMout_in"
        [2] - "PMT_out"
        [3] - "SiPMin_out"
    REF_int : list of np.ndarray
        Integrated reference signal values for all processed events and
        channels.
        [0] - "SiPMin_in"
        [1] - "SiPMin_in"
        [2] - "SiPMout_out"
        [3] - "SiPMout_out"        
    """
    def calculate_eventwise_ratios(self):
        # ----------------------------------------
        # Mapping of signal channels to their
        # corresponding reference channels
        # ----------------------------------------
        if self.baseline_integrated_data_eventwise == None:
            ValueError("self.baseline_integrated_data_eventwise does not exist.\n Please run load() with option redo=True")
    
        else: 
            if self.baseline_integrated_data_eventwise.get("SiPMin_in_gain") is not None:
                ratio_map = {
                      "PMT_in": "SiPMin_in_gain",
                      "SiPMout_in_gain": "SiPMin_in_gain",
                      "PMT_out": "SiPMout_out_gain",
                      "SiPMin_out_gain": "SiPMout_out_gain"
                }  
            else:
                ratio_map = {
                        "PMT_in": "SiPMin_in",
                        "SiPMout_in": "SiPMin_in",
                        "PMT_out": "SiPMout_out",
                        "SiPMin_out": "SiPMout_out"
                } 
            for pm, ref in ratio_map.items():
                ratios_mean = []
                ratios_std = []
                Ratios = [] 

                # Loop over all events
                for pm_row, ref_row in zip(
                    self.baseline_integrated_data_eventwise[pm],
                    self.baseline_integrated_data_eventwise[ref]
                ):
                    # Convert rows to 1D float arrays
                    pm_arr = np.array(pm_row, dtype=float)
                    ref_arr = np.array(ref_row, dtype=float)

                    # Calculate ratio element-wise; place np.nan where ref_arr == 0
                    with np.errstate(divide='ignore', invalid='ignore'):
                        ratios = np.where(ref_arr != 0, pm_arr / ref_arr, np.nan)

                    # Calculate statistics while ignoring np.nan entries
                    ratios_mean.append(np.nanmean(ratios))
                    ratios_std.append(np.nanstd(ratios))
                    Ratios.append(ratios)

                # Store results
                self.baseline_integrated_data[f"{pm}_ref"] = np.array(ratios_mean)
                self.baseline_integrated_data[f"{pm}_ref_std"] = np.array(ratios_std)
                self.baseline_integrated_data_eventwise[f"{pm}_ref"] = np.array(Ratios, dtype=object)

                self.savecsv(name="baseline_integrated_data")    
                # Loop over all events
                #for pm_row, ref_row in zip(
                    #self.baseline_integrated_data_eventwise[pm],
                    #self.baseline_integrated_data_eventwise[ref]
                #):
                    ## Integrated pulse areas for all waveforms
                    ## belonging to the current event
                    #pm_int = []
                    #ref_int = []
#
                    ## Loop over all waveform pairs within the event
                    #count = 0
                    #for area_pm, area_ref in zip(pm_row, ref_row):
                        ## Store integrated pulse areas
                        #if area_ref != 0:
                            #pm_int.append(area_pm)
                            #ref_int.append(area_ref)
                        #else:
                            #print(ref, count, "area_ref = 0:") 
                            #pm_int.append(None)
                            #ref_int.append(None)
#
                        #count += 1    
#
                    ## Convert to numpy arrays for vectorized operations
                    #pm_int = np.array(pm_int)
                    #ref_int = np.array(ref_int)
#
                    ## Calculate waveform-by-waveform ratios
                    #if "PMT" in pm:
                        #ratios = pm_int / ref_int
                    #else:  
                        #ratios = pm_int / ref_int  
                    ##else:
                     ##   print(pm_row, ref_row, "ref_int = 0")
                    ## Calculate event-wise statistics
                    #ratios_mean.append(np.mean(ratios))
                    #ratios_std.append(np.std(ratios))
                    #Ratios.append(ratios)
#
                ## Store results in the integrated-data dataframe/dictionary
                #self.baseline_integrated_data[f"{pm}_ref"] = np.array(ratios_mean)
                #self.baseline_integrated_data[f"{pm}_ref_std"] = np.array(ratios_std)
                #self.baseline_integrated_data_eventwise[f"{pm}_ref"] = np.array(Ratios)

            
            

    

    """
    Update example waveform plots for a given scan position.

    Updates 3 waveform channels simultaneously in an interactive plot.

    Takes:
        waveforms : list[np.ndarray]
            List of 1D waveform arrays (length = 3)

        j : int
            Scan j-position

        i : int
            Scan i-position

        ch : list[str]
            Channel names used in plot titles

    Notes:
        - Uses fixed time axis from acquisition settings
        - Rescales y-axis dynamically per update
        - Intended for live / iterative visualization
    """
    def update_example_waveform(self, waveforms, j, i, ch):
        """
        waveforms: iterable of 3 1D numpy arrays
        """
        x = np.linspace(
            self.rec_time_min,
            self.rec_time_max,
            self.frame_length_max
        )
        xmin, xmax = self.rec_time_min, self.rec_time_max
        for idx in range(3):
            ymin, ymax = waveforms[idx].min() * 1.1, waveforms[idx].max() * 1.1
        
            y = waveforms[idx]

            self.lines[idx].set_data(x, y)

            self.ax[idx].set_xlim(xmin, xmax)
            self.ax[idx].set_ylim(ymin, ymax)

            self.ax[idx].set_title(
                f"{ch[idx]} mean over {self.rep} wfs | j={j}, i={i}"
            )

        self.fig.canvas.draw_idle()
        plt.pause(0.1)


    """
    Plot detector temperatures as a function of daytime.

    Shows the inside and outside temperature measurements
    including constant measurement uncertainties.

    Returns:
        None
    """
    def plot_temperature_over_time(self):
        timearr = []
        day = 0

        time0 = datetime.strptime(self.integrated_data["time"][0], "%H:%M:%S")
        prev_t = time0

        for i in range(len(self.integrated_data["time"])):

            t = datetime.strptime(self.integrated_data["time"][i], "%H:%M:%S")

            # detect midnight wrap
            if t < prev_t:
                day += 1

            # build full datetime (anchor to arbitrary date, e.g. Jan 1)
            t_full = datetime(2000, 1, 1) + timedelta(days=day,
                                                    hours=t.hour,
                                                    minutes=t.minute,
                                                    seconds=t.second)

            timearr.append(t_full)

        prev_t = t
        plt.errorbar(np.array(timearr), np.array(self.integrated_data["temp_in"]), yerr = 0.0375, label="Temperature inside WOM")
        plt.errorbar(np.array(timearr), np.array(self.integrated_data["temp_out"]), yerr = 0.0375, label="Temperature outside WOM")
        
        plt.xlabel("Daytime [HH:MM]")
        plt.ylabel("Temperature [°C]")

        plt.legend()

        # 👉 format x-axis to show only hours and minutes
        plt.gca().xaxis.set_major_formatter(mdates.DateFormatter('%H:%M'))

        # optional: control tick density
        plt.gca().xaxis.set_major_locator(mdates.AutoDateLocator())
        plt.gcf().autofmt_xdate()
        

    """
    Plot integrated signal values over time for selected channels.

    Creates a time evolution plot of the integrated charge
    for the provided detector channels.

    Takes:
        PM : list[str]
            List of channel names to plot.

    Returns:
        None
    """ 
    def plot_integral_over_time(self, PM):
        fig, ax = plt.subplots(figsize=(7, 5), facecolor='white')
        for pm in PM: 
            ax.plot(np.array(self.integrated_data["time"]), np.array(self.integrated_data[pm]), label = pm)
        ax.set_xlabel("Time")
        ax.set_ylabel("Integral [Vxs]")
        plt.legend()
        ax.xaxis.set_major_locator(plt.MaxNLocator(nbins=8))


    """
    Plot heatmaps of the integrated data for one or two of the following options (ch1 = "...", ch2 = "..."):
        temp_in,
        temp_out,
        PMT_ratio_in,
        PMT_ratio_in_std,
        SiPM_ratio_in,
        SiPM_ratio_in_std,
        SiPM_ref_in,
        SiPM_ref_in_std,
        PMT_ratio_out,
        PMT_ratio_out_std,
        SiPM_ratio_out,
        SiPM_ratio_out_std,
        SiPM_ref_out,
        SiPM_ref_out_std
    vmin, vmax: color scale limits as list vmin = [vmin], vmax = [vmax]/ vmin = [vmin_ch1, vmin_ch2], vmax = [vmax_ch1, vmax_ch2]
    step_size = 6.55 - vertical step size - programmed into the motionsoft, software - note: it probably also makes sense to add a rotation step size that is programed into the arduino
    colorlabel = None - Set to label of the colorbar (string) if you want to set the label
    title = None  - Set to title string if you want to set the title 
    baseline_subtract = True - set to False if you want to see the raw data without baseline correction
    normalize = False,  - Set to True if you want to see the plot normalized to its mean
    remove_rows = [0,0] : must be an array with [how many first rows should be removed, how many last rows should be removed]
    """
    def heatmap_WOM(self, ch1= "PMT_ratio_in", ch2 = None, vmin=None, vmax=None,
                    step_size = 6.55, colorlabel = None, title = None,  baseline_subtract = True, normalize = False, remove_rows = [0,0]):
        if baseline_subtract:
            if hasattr(self, "baseline_integrated_data"):
                integrated_data = self.baseline_integrated_data.copy()
                name_suffix = ""
            else:
                ValueError("self.baseline_integrated_data does not exist. Please run load()")    
        else: 
            integrated_data = self.integrated_data.copy()    
            name_suffix = "_wo_baseline_subtraction"
        # Extract values for heatmap x,y
        if self.integrated_data["j"][0] == 999:
            x, y = integrated_data["j"][1:], -integrated_data["i"][1:]
        else:
            x, y = integrated_data["j"], -integrated_data["i"]    
        nx = len(np.unique(x))
        ny = len(np.unique(y))
        X = x.values.reshape(ny, nx)
        Y = y.values.reshape(ny, nx)
        
        if colorlabel == None:
            if "ratio" in ch1 and "std" in ch1:
                colorbar_label = ["Standard deviation [a.u.]"]
            elif "std" in ch1:
                colorbar_label = ["Standard deviation [Vxs]"]    
            elif "err" in ch1:   
                colorbar_label = ["Error [Vxs]"]
            elif "pull" in ch1:
                colorbar_label = ["Difference/Error"]    
            elif "ref" in ch1 or "ratio" in ch1:
                colorbar_label = ["Integrated yield / Reference"]
            elif "temp" in ch1:
                colorbar_label = ["Temperature [°C]"]   
            if normalize:
                if "std" in ch1:
                    colorbar_label = ["Standard deviation [a.u.]"]
                elif "err" in ch1:
                    colorbar_label = ["Error [a.u.]"]   
                else:      
                    colorbar_label = ["Normalized integrated yield [a.u.]"]    
            else:
                colorbar_label = ["Integral [Vxs]"]    
        else:
            colorbar_label = colorlabel

        if ch2: 
            # ---- Heatmap for two channels ----
            fig, ax = plt.subplots(1, 2, figsize=(12, 5),  facecolor='white')
            channels = [ch1, ch2]
            if title == None:
                title = [f"{ch1}", f"{ch2}"]
            dfname = self.foldername / f"{self.filename}_{ch1}_{ch2}{name_suffix}.pdf"
            if colorbar_label != colorlabel:
                if "ratio" in ch2 and "std" in ch2:
                    colorbar_label.append("Standard deviation [a.u.]")
                elif "std" in ch2:
                    colorbar_label.append("Standard deviation [Vxs]")   
                elif "err" in ch2:   
                    colorbar_label.append("Error [Vxs]")
                elif "pull" in ch2:
                    colorbar_label.append("Difference/Error")    
                elif "ref" in ch2 or "ratio" in ch2:
                    colorbar_label.append("Integrated yield / Reference")
                elif "temp" in ch2:
                    colorbar_label.append("Temperature [°C]")   
                if normalize:
                    if "std" in ch2:
                        colorbar_label.append("Standard deviation [a.u.]")
                    elif "err" in ch2:
                        colorbar_label.append("Error [a.u.]")   
                    else:     
                        colorbar_label.append("Normalized integrated yield [a.u.]")    
                else:
                    colorbar_label.append("Integral [Vxs]")           

        else:    
            # ---- Heatmap ----
            fig, ax = plt.subplots(1, 1, figsize=(6, 5),  facecolor='white')
            if title == None:
                title = [f"{ch1}"]
            dfname = self.foldername / f"{self.filename}_{ch1}{name_suffix}.pdf"
            ax = np.atleast_1d(ax)
            channels = [ch1]
        
        for idx, ch in enumerate(channels):    
            # Extract values for heatmap z = integrated data[ch1]
            if self.integrated_data["j"][0] == 999:
                pivot = integrated_data.iloc[1:].pivot(index="i", columns="j", values=ch)
            else:
                pivot = integrated_data.pivot(index="i", columns="j", values=ch)    
            # remove rows? 
            #   
            if remove_rows != [0,0]:
                if remove_rows[0] != 0 and remove_rows[1] == 0:
                    pivot = pivot.iloc[remove_rows[0]:]
                elif remove_rows[0] == 0 and remove_rows[1] != 0:  
                    pivot = pivot.iloc[:-remove_rows[1]]
                else:    
                    pivot = pivot.iloc[remove_rows[0]:-remove_rows[1]]
                

            if normalize and "std" not in ch and "err" not in ch:
                overall_mean = pivot.mean().mean()   #[here one has to take the mean not the mean of the std]
            elif normalize and "std" in ch or "err" in ch:
                overall_mean = overall_mean
            else:
                overall_mean = 1

            

            #X, Y = np.meshgrid(pivot.columns.values, -pivot.index.values)
            Z = pivot.values/overall_mean
            nx = Z.shape[1]
            ny = Z.shape[0]

            x_phys = np.linspace(0, 360, nx)

            if "_in" in ch or "ref_in" in ch or "Noise_in" in ch or "norm_in" in ch:
                y_phys = np.linspace(202-remove_rows[0]*step_size, 202 - ny*step_size, ny)  # inside spacing
                y_ticks = np.linspace(202-remove_rows[0]*step_size, 202 - ny*step_size, ny)
            elif "_out" in ch or "ref_out" in ch or "Noise_out" in ch or "norm_out" in ch:
                y_phys = np.linspace(195-remove_rows[0]*step_size, 195 - ny*step_size, ny)  # outside spacing
                y_ticks = np.linspace(195-remove_rows[0]*step_size, 195 - ny*step_size, ny)
            else:
                y_phys = np.linspace(199-remove_rows[0]*step_size, 199 - ny*step_size, ny)
                y_ticks = np.linspace(199-remove_rows[0]*step_size, 199 - ny*step_size, ny)

            X, Y = np.meshgrid(x_phys, y_phys)
            #z = self.integrated_data[ch]
            #Z = z.values.reshape(ny, nx)
            if vmin and vmax: 
                im = ax[idx].pcolormesh(X, Y, Z, cmap='plasma', vmin=vmin[idx], vmax=vmax[idx], shading='auto')  # heatmap
            else:
                im = ax[idx].pcolormesh(X, Y, Z, cmap='plasma', shading='auto')  # heatmap
         
            cbar = fig.colorbar(im, ax=ax[idx], label=colorbar_label[idx])
            ax[idx].set_xlabel(r"Rotation $\phi$ [°]")
            ax[idx].set_ylabel("Distance to PMT [mm]")
            ax[idx].set_title(title[idx])

            ax[idx].set_ylim(190 - ny*step_size, 207)
            # Adjust y-axis ticks
            #ax[idx].set_yticks(y_phys)
            #ax[idx].set_yticklabels(y_ticks)

            # Adjust x-axis ticks
            #if nx < 10:
             #   nx_ticks = nx
            #else:
            #    nx_ticks = 10
            #ax[idx].set_xticks(np.linspace(0, nx, nx_ticks))
            #ax[idx].set_xticklabels(np.linspace(0, 360, nx_ticks))
        fig.tight_layout()
        # Save heatmap to folder
        plt.savefig(dfname)
        plt.show()
        return 0

    """
    Plot integrated light yield or related quantities over time
    for up to three detector channels.

    Creates a 1D comparison plot showing the evolution of:
        - signal integrals
        - standard deviations
        - temperatures

    for the selected channels.

    Takes:
        ch1, ch2, ch3 : str
            Channel names to plot.

    Returns:
        int
            Returns 0 after plotting and saving the figure.

    Saves:
        PDF figure in the measurement folder.
    """
    def light_yield_1dim(self, ch1= "PMT_in", ch2 = "SiPMin_in", ch3="SiPMout_in"):
        # Extract values for heatmap x,y
        x = self.integrated_data["time"]
    
        if "std" in ch1:
            ylabel = "Standard deviation [Vxs]"
        elif "int" in ch1:
            ylabel = "Integral [Vxns]"
        elif "temp" in ch1:
            ylabel = "Temperature [°C]" 
        else:
            ylabel = "Unknown"
 
        # ---- Plot ----
        fig, ax = plt.subplots(1, 3, figsize=(12, 4),  facecolor='white')
        
        dfname = self.foldername / f"{self.filename}_Light_yield_over_distance_to_PMT_{ch1}.pdf"
        
        channels = [ch1, ch2, ch3]
        for idx, ch in enumerate(channels):   
            
            y = self.integrated_data[ch]
            y = y[y != 0] * 1e9

            if "t_in" in ch1:
                x_scale = x[:len(y)]
            elif "t_out" in ch1:
                x_scale = x[len(y)-1:2*len(y)-1]
            else:
                x_scale = np.arange(0, len(y))    

            ax[idx].plot(x_scale, y, label=f"{round(np.mean(y),2)}+-{round(np.std(y),2)}")
            ax[idx].set_xlabel("time [h:m:s]")
            ax[idx].set_ylabel(ylabel)
            ax[idx].xaxis.set_major_locator(plt.MaxNLocator(nbins=6))
            ax[idx].legend()
            ax[idx].set_title(f"{self.WOMname} {ch}")

            # Adjust y-axis ticks
            #ax[idx].set_yticks(np.linspace(-(ny-1), 1, nymax))
            #ax[idx].set_yticklabels(y_ticks)

            # Adjust x-axis ticks
            #if nx < 10:
             #   nx_ticks = nx
            #else:
            #    nx_ticks = 10
            #ax[idx].set_xticks(np.linspace(0, nx, nx_ticks))
            #ax[idx].set_xticklabels(np.linspace(0, 360, nx_ticks))
        fig.tight_layout()
        # Save heatmap to folder
        plt.savefig(dfname)
        plt.show()
        return 0
    
    '''
    Print the charge spectrum for one of the following options:
            PMT_ratio_in,
            SiPM_ratio_in, 
            SiPM_ref_in,
            PMT_out,
            SiPMin_out,
            SiPMout_out
        bins: number of bins in the histogram
        vmin, vmax: limits of the x-axis
        '''    
    def charge_spectrum(self, ch="PMT_ratio_in", bins=90, vmin=None, vmax=None):
        fig, ax = plt.subplots(figsize=(7, 5), facecolor="white")
        data = self.integrated_data[self.integrated_data[ch] != 0]
        ax.hist(
            data,
            bins=bins,
            range=None if vmin is None or vmax is None else (vmin, vmax),
            histtype="step"
        )
        ax.set_xlabel("Integrated Signal [V·s]")
        ax.set_ylabel("# Entries")
        return fig, ax
    
    """
        Plot all waveforms at a given scan position.
    
        Takes:
            i : int or float
                Scan i-position
    
            j : int or float
                Scan j-position
    
            pm : str
                Channel name, e.g. "SiPMin_in"
    
            baseline_corrected : bool
                If True, plots baseline-corrected waveforms.
                Otherwise plots raw waveforms.
        """
    def plot_waveforms_position(
        self,
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
        if reps is None:
            reps = self.rep

        # ----------------------------------------
        # Find matching scan position
        # ----------------------------------------
        mask = (
            (self.integrated_data["i"] == i) &
            (self.integrated_data["j"] == j)
        )

        indices = np.where(mask)[0]

        if len(indices) == 0:
            raise ValueError(f"No position found for i={i}, j={j}")

        idx = indices[0]
        # ----------------------------------------
        # Time axis
        # ----------------------------------------
        x = np.linspace(
            self.rec_time_min,
            self.rec_time_max,
            self.frame_length_max
        )*1e9 # convert to ns
        # ----------------------------------------
            # Plot
            # ----------------------------------------
        plt.figure(figsize=(8, 6))

        for pm in PM:
            # ----------------------------------------
            # Select waveform source
            # ----------------------------------------
            wf_sum = np.zeros_like(self.waveforms[pm][idx][0])
            if baseline_corrected:
                wf_data = self.baseline_wf[pm][idx]
            else:
                wf_data = self.waveforms[pm][idx]
                
            if "in_in" in pm or "out_out" in pm:
                    label = f"{pm} reference at i={i}, j={j}"
                    color = 'green'
                    color_line ='darkgreen'
                    
            elif "in_out" in pm or "out_in" in pm:
                    label = f"{pm} transmission at i={i}, j={j}" 
                    color = 'blue'  
                    color_line ='darkblue'
                    
            elif "PMT" in pm:
                    label = f"{pm} response at i={i}, j={j}"
                    color = 'orange'
                    color_line ='darkorange'
            else: 
                    label = f"{pm} at i={i}, j={j}"   

            for wf in wf_data[0:reps]:  # plot all repetitions
                if plot_mean is False:
                    alpha = max(1/reps, 0.1)   
                    plt.plot(x, wf, alpha=alpha, color=color, label=label)
                elif plot_mean:
                    wf_sum += wf/reps
                if plot_integration_window:
                    if "PMT" in pm:
                        int_window_min = self.int_window_min_PMT
                        int_window_max = self.int_window_max_PMT
                        peak_idx = np.argmin(wf)
                        ymin = wf.min()
                        ymax = 0
                    elif "SiPM" in pm:
                        int_window_min = self.int_window_min_SiPM
                        int_window_max = self.int_window_max_SiPM
                        peak_idx = np.argmax(wf)
                        ymin = 0 
                        ymax = wf.max()
                    else:
                        raise ValueError(f"Unknown PM type: {pm}")

                
                    peak_time = x[peak_idx]

                    

                    start_time = peak_time - int_window_min*1e9
                    end_time   = peak_time + int_window_max*1e9

                    plt.vlines(
                        start_time,
                        ymin = ymin,
                        ymax = ymax,
                        color=color_line,
                        linestyle="--",
                        label=f"Integration start {pm}"
                    )

                    plt.vlines(
                        end_time,
                        ymin = ymin,
                        ymax = ymax,
                        color=color_line,
                        linestyle="--",
                        label=f"Integration end {pm}"
                    )
            if plot_mean: 
                plt.plot(x, wf_sum, color=color, label=label)        
        plt.xlabel("Time difference to trigger time[ns]")
        plt.ylabel("Amplitude [V]")
        if legend:
            plt.legend()
        if title:
            plt.title(f"{pm} at i={i}, j={j}")
        #plt.grid(True)
        plt.xlim(self.rec_time_min*1e9, self.rec_time_max*1e9)
        plt.ylim(-1.1,1.5)

        plt.show()




    ''' ANALYSIS METHODS'''

    '''
    Baseline correction using minimum sum in range for correction.
        Corrects the baseline (DC offset) of all waveforms.
        Searches for the minimum of the sum of bins in a window of length window[0] in range window[1]-window[2]
        Make sure the search range is shortly before the triggered signal is expected to arrive.
        Takes:
            waveform, 
            window=(integration window length, start index, end index), 
            sigma= 0 (if > 0, applies smoothing before baseline correction),
            smooth_method= 0 (running average), 2 (gaussian)
        returns:
        corrected, baseline_value, min_index
    '''
    @staticmethod
    def correct_baseline_min(waveform, window, sigma, smooth_method):

        wf = np.asarray(waveform, dtype=float)
        n = len(wf)

        # --- Optional smoothing ---
        if sigma > 0:
            if smooth_method == 0:
                kernel = np.ones(int(2 * sigma + 1)) / (2 * sigma + 1)
                wf = np.convolve(wf, kernel, mode='same')
            elif smooth_method == 2:
                wf = gaussian_filter1d(wf, sigma=sigma)

        # --- Window params ---
        length, start, end = window
        start = max(0, int(start))
        end = min(n - length, int(end))

        # 🚀 Vectorized moving average
        kernel = np.ones(length) / length
        means_full = np.convolve(wf, kernel, mode='valid')

        # restrict to search region
        means = means_full[start:end]

        # find minimum
        min_index_local = np.argmin(np.abs(means))
        min_index = start + min_index_local

        baseline_value = means[min_index_local]
        corrected = wf - baseline_value

        return corrected, baseline_value, min_index

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