
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
d\text{Gain}(T) \sqrt{((dA * (Vset + B + C*T))^2 + (A * dV_{set})^2 + (dB*A)^2 + (dC * T*A)^2 + (dT*C*A)+ (dD)^2)}
$$
- The SiPM response is devided by the gain - eventwise - is there an error? 
$$\text{SiPM}_{gain} = \frac{\text{SiPM}}{\text{Gain}}$$
$$d\text{SiPM}_{gain} = \text{SiPM}_{gain}\sqrt{(\frac{d\text{SiPM}}{\text{SiPM}})^2 + \frac{d\text{Gain}}{\text{Gain}})^2}$$
- Maybe for the eventwise calculation $dSiPM$ = 0 
> SiPMs get an error from the gain + error from the standard deviation
- SiPMs are normalized with the measurements without WOM $i=0$
$$\text{SiPM}_{gain, norm} = \frac{\text{SiPM}_{gain}}{\text{SiPM}_{gain, i=0}}$$
$$d\text{SiPM}_{gain, norm} = \text{SiPM}_{gain, norm}\sqrt{(\frac{d\text{SiPM}_{gain}}{\text{SiPM}_{gain}})^2 + \frac{d\text{SiPM}_{gain,i=0}}{\text{SiPM}_{gain,i=0}})^2}$$
$$\text{SiPM}_{gain,i=0} = \frac{\sigma_{\text{SiPM}_{gain,i=0}}}{\sqrt{N}}$$
> Does this make sense?
If I normalize the Reference with the measurement without WOM the overall LED intensity cancels out in the SiPMs but not in the PMT?
>Maybe for the transmission but not for the PMT?
>Error propagation 
- Every event in Transmission SiPM and PMT is normalized with the same event in the reference 
- For each event $i
$$\text{PMT}_{ref,i} = \frac{\text{PMT}_i}{\text{SiPM}_{ref,i}}$$
>$$\text{SiPM}_{trans, ref,i} = \frac{\text{SiPM}_{trans,i}}{\text{SiPM}_{ref,i}}$$
>$$d\text{PM}_{ref} = \text{PM}_{ref}\sqrt{(\frac{d\text{PM}}{\text{PM}})^2 + \frac{d\text{SiPM}_{ref}}{\text{SiPM}_{ref}})^2}$$
>	For each event $d\text{PMT} = 0$, $d\text{SiPM}_{trans} = d\text{SiPM}_{trans. gain, norm}$ and                     $d\text{SiPM}_{ref} = d\text{SiPM}_{ref. gain, norm}$

- The calulating the mean over several events leads to: 
$$$$