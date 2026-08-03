---
tags: 
aliases:
  - timing of scintillators
---
# Time Response of Scintillators

The scintillation pulse $f(t)$ of a single, continuous piece of scintillating material, completely transparent to its fluorescence, can be described by an exponential function:

$$
f(t) = \frac{1}{\tau} \exp\left(-\frac{t}{\tau}\right),
$$

where $\tau$ is the fluorescence decay time constant. 

If the [[Organic Scintillator|scintillator]] re-absorbs some of the emitted photons, this increases $\tau$. 

Time studies with plastic scintillation counters have shown that a slow initial rise $\mathcal{O}({1\,\text{ns}})$ of the light pulse must be assumed in order to capture the temporal properties of the counter and the time jitter of the scintillator. As a result, a convolution of $f(t)$ and a clipped Gaussian function $g(t)$ was proposed to describe the shape of the light pulse of [[Organic Scintillator|plastic scintillators]]:

$$
g(t) * f(t) = \frac{1}{2\tau} \exp\left(\frac{\sigma^2 - 2\tau(t - t_0)}{2\tau^2}\right) \, \text{erf}\left(\frac{\sigma^2 - \tau (t - t_0)}{\sqrt{2\sigma^2 \tau^2}}\right),
$$

where $\sigma$ is the standard deviation describing the variances of the timing of the [[PMT]] and the [[Organic Scintillator|scintillator]], and $t_0$ is the expectation value describing the time response of the [[Scintillation Detectors|scintillator detector]].
