
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
- The SiPM response is devided by the gain 
$$\text{SiPM}_{gain} = $\frac{\text{SiPM}}{\text{Gain}}$
> SiPMs get an error from the gain + error from the standard deviation
- SiPMs are normalized with the measurement without WOM
> Does this make sense?
If I normalize the Reference with the measurement without WOM the overall LED intensity cancels out in the SiPMs but not in the PMT?
>Maybe for the transmission but not for the PMT?
>Error propagation 
- Every event in Transmission SiPM and PMT is normalized with the same event in the reference 
>Error propagation
