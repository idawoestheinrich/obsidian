
- The temperature dependent gain is calculated by the temperature 
> Gain + Gain uncertainty 
$$
\text{Gain}(T) = A * (V_{set} - B - C * T) + D
$$
A = 7.83861591e5 
dA = 0.00148324e5
B = 39.16
dB = 0.01
C = 33.66e-3
dC = 0.30e-3
D = 9.80997541e5
dD = 0.00466260e5
dT = 0.1
dVset = 0.1
$$
\Delta\text{Gain}(T) \sqrt{((\Delta A * (Vset + B + C*T))^2 + (A * \Delta V_{set})^2 + (\Delta B*A)^2 + (\Delta C * T*A)^2 + (\Delta T*C*A)+ (\Delta D)^2)}
$$
- The SiPM response is devided by the gain - eventwise - is there an error? 
$$\text{SiPM}_{gain} = \frac{\text{SiPM}}{\text{Gain}}$$
$$d\text{SiPM}_{gain} = \text{SiPM}_{gain}\sqrt{(\frac{\Delta\text{SiPM}}{\text{SiPM}})^2 + \frac{\Delta\text{Gain}}{\text{Gain}})^2}$$
- Maybe for the eventwise calculation $dSiPM$ = 0 
> SiPMs get an error from the gain + error from the standard deviation
- SiPMs are normalized with the measurements without WOM $i=0$
$$\text{SiPM}_{gain, norm} = \frac{\text{SiPM}_{gain}}{\text{SiPM}_{gain, i=0}}$$
$$d\text{SiPM}_{gain, norm} = \text{SiPM}_{gain, norm}\sqrt{(\frac{\Delta\text{SiPM}_{gain}}{\text{SiPM}_{gain}})^2 + \frac{\Delta\text{SiPM}_{gain,i=0}}{\text{SiPM}_{gain,i=0}})^2}$$
$$\Delta\text{SiPM}_{gain,i=0} = \frac{\sigma_{\text{SiPM}_{gain,i=0}}}{\sqrt{N}}$$
> Does this make sense?
If I normalize the Reference with the measurement without WOM the overall LED intensity cancels out in the SiPMs but not in the PMT?
>Maybe for the transmission but not for the PMT?
>Error propagation 
- Every event in Transmission SiPM and PMT is normalized with the same event in the reference 
- For each event $i$
$$\text{PMT}_{ref,i} = \frac{\text{PMT}_i}{\text{SiPM}_{ref,i}}$$
>$$\text{SiPM}_{trans, ref,i} = \frac{\text{SiPM}_{trans,i}}{\text{SiPM}_{ref,i}}$$
>$$\Delta\text{PM}_{ref,i} = \text{PM}_{ref,i}\sqrt{(\frac{\Delta\text{PM}_i}{\text{PM}_i})^2 + \frac{\Delta\text{SiPM}_{ref,i}}{\text{SiPM}_{ref,i}})^2}$$
>	For each event $d\text{PMT} = 0$, $d\text{SiPM}_{trans} = d\text{SiPM}_{trans. gain, norm}$ and                     $d\text{SiPM}_{ref} = d\text{SiPM}_{ref. gain, norm}$

- The calculating the mean over several events leads to: 
$$\text{PM}_{ref} = \frac{1}{N}\sum_i^N{\text{PM}_{ref,i}}$$
$$\Delta\text{PM}_{ref} = \frac{1}{N}\sqrt{\sum_i^N{(\Delta\text{PM}_{ref,i}})^2}$$