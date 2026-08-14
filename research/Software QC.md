### Normalization and gain correction





## Improvements of the code by using [[Python classes]]

``` python
def heatmap_WOM(df, WOMnr, ring = False, limit = False, imin = 2e-8 , imax = 4.5e-8, smin = 2e-10 , smax = 6e-10):


def riemann_sum_peak(data, rec_time_min, rec_time_max, int_window_min, int_window_max,
frame_length_max):

def get_data(ch, rep, pulsewidth_ch1, pulsewidth_ch2, rec_time_min, rec_time_max, int_window_min, int_window_max, frame_length_max): #channel number ch, number of waveforms taken per position rep

def riemann_sum_peak(data, rec_time_min, rec_time_max, int_window_min, int_window_max,
frame_length_max):

title = f"{WOMnr} inside LED"
dfname = f"plots/{date}_WOM{WOMnr}_inside_LED_heatmap.pdf"
dfnamehist = f"plots/{date}_WOM{WOMnr}_inside_LED_integrated_spectrum.pdf"
offset = 2.5 # inside spacing

colorbar_label ="Integral [Vxs]"

vmin, vmax = imin, imax
```


\ Start motion into the WOM

**Send I/O Signal to motionsoft over pin1**

i=0

j=0

\\ write i and j into a script with positions


as long as j <30: 

\\ When getting a signal from motionsoft start measurment 

**receive signal over pin 3**

i++

\\ Efficiency measurment

\\ Moku generate pulses for 1 s on output 1 

\\ trigger on output 1 and save input 1 to a logfile called „inside something“

\\ Moku generate pulses for 1 s on output 2

\\ trigger on output 2 and save input 1 to a logfile called „outside something“

  

\\  Absorption measurment

**\\  start an Arduino script that measures Sensors one and two - save something inside**

  

\\  Moku generates a 1s long signal with an amplitude of about 3 Vs on output 1

**\\  start an Arduino script that measures Sensors one and two - save something inside** 

  

\\ Moku generates a 1s long signal with an amplitude of about 3 Vs on output 2

  

As long as i<20 

Send I/O Signal to MotionSoft over pin1

\\ System moves one step down

receive signal over pin 3

i++

\\ repeat measurement 

  

if i = 20 

**\\ Run Arduino script that does 20 steps in rotation asign the step number and sends a signal when its done**

j ++

set i = 0

  

\\ repeat measurement 

  

**Send I/O Signal to motion soft over pin2**

\\ System moves one step up

receive signal over pin 3

i++

  

\\ repeat measurement 

  

if i < 20 

**Send I/O Signal to MotionSoft over pin1**

\\ System moves one step up

**receive signal over pin 3**

i++

  

\\ repeat measurement 

  

if i = 20: \\ position at the top of the WOM again 

  

**\\ Run Arduino script that does 20 steps in rotation asign the step number with j and sends a signal when its done**

j++

  

\\ repeat measurement 

i = 0

Send I/O Signal to motion soft over pin2

\\ System moves one step down 

receive signal over pin 3

i++

\\ repeat measurement 

As long as i<20 

Send I/O Signal to MotionSoft over pin1

\\ System moves one step down

receive signal over pin 3

i++ …

  

if j = 30  and i = 20:

**\\ Run Arduino script that does 600 steps rotating in the other direction and sends a signal when its done**

  

I/O output 4 whenever the system is in position 1

  

if !output 4

Send I/O Signal to motion soft over pin2

  

if output 4

Send I/O Signal to motion soft over pin2

Send I/O Signal to motion soft over pin2 

\\ system moves back up into position 0