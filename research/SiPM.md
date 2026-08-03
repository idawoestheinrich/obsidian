---
tags: 
aliases:
  - Silicon Photomultiplier
  - SiPMs
---
### Working Principle of a SiPM

The gain of a [[SiPM]] is typically between a few $10^5$ and $10^6$, similar to a [[PMT]]. A [[SiPM]], also known as a Multi-Pixel Photon Counter (MPPC), is an array of parallel-connected single-photon avalanche diodes (SPAD) implemented on a silicon substrate. SPADs are photodetectors based on avalanche multiplication processes in a p-n junction.
![[THEO_SiPM_functionality.png]]
A schematic view representation of a SPAD cross-section within a [[SiPM]] and of correlated noise sources. When a photon (purple wavy arrow) enters through a transparent and protective epoxy layer and an anti-reflective coating (ARC), it is converted into a photoelectron, triggering a self-sustaining avalanche multiplication process in the depletion zone. If carriers are trapped and only released with a delay, they can trigger new avalanches (AP and APdiff). Secondary photons, produced during an avalanche in one cell, can trigger direct (DiCT) or delayed crosstalk (DeCT).

They are operated with a bias voltage $V_\text{Bias}$ above the breakdown voltage $V_\text{BD}$, which is called Geiger Mode. The SPAD is a binary photodetector in this mode. Each SPAD consists of differently doped silicon layers coated with an anti-reflective coat (ARC)  

In the area where the $\text{n}^+$- and p-implants meet, the additional valence electrons of the $\text{n}^+$-implant fill the holes of the p-implant. This results in a depletion region devoid of free charge carriers. The thickness of the depletion region depends on the reverse bias voltage, which is here $V_\text{Bias} > V_\text{BD}$. In this region, the resulting electric field forms the multiplication region. Below the heavily doped p-layer is the thicker and weakly doped $\text{p}^-$-epi-layer and the $\text{p}^+$-substrate, which make it possible for carriers generated here to diffuse and reach the depletion region [[kolanoski2016teilchendetektoren, 2018SiPM]].

The electric field is so high that a single electron-hole pair generated or injected into the depletion region is accelerated and can trigger a self-sustaining avalanche multiplication process, resulting in a rapid increase in current within nanoseconds. If a photon generates the primary carrier, the leading edge of the pulse marks the arrival time of the detected photon.

The bias voltage is lowered by high-value resistors to or below the breakdown voltage, thereby stopping the self-sustaining avalanche current after a photon-triggered breakdown. The electric field can no longer accelerate the carriers with sufficient energy. This process is called quenching and is enabled by specific quenching circuits described in [[1996SPADs]]. After quenching, the SPAD must be reset by restoring the bias voltage to be able to detect another photon. This *dead-time* is typically in the order of tens of nanoseconds [[2018SiPM]].

The noise sources in SPADs can be divided into primary noise, which is all avalanche pulses due to thermally generated carriers, and correlated noise due to afterpulsing effects. Afterpulsing occurs due to the effect of "trapped" carriers that are only released with a delay after the avalanche pulse, triggering new avalanches unrelated to the measured photon.

In a [[SiPM]], each SPAD serves as one square pixel cell. The pixel cells have typical dimensions in the $15-70\,\si{\mu m}$ range and are densely arranged on the substrate. If the number of photons is significantly lower than the number of cells on the [[SiPM]], this results in a low probability of more than one photon hitting a single cell within the time window specified by the time resolution. That means the number of triggered pixels and, thus, the output current is proportional to the number of incoming photons. The signals of the individual SPAD cells of a [[SiPM]] are combined via the quench resistors.

[[SiPM|SiPMs]] have two major advantages over other single-photon diodes: their scalability and the advantage of being photon-number resolved.

Compared to [[PMT|PMTs]], however, they have a significantly higher noise rate per surface area. Due to the implementation of multiple SPADs in one device and the combination of the signals, the ratio between the sensitive area and the total area of the cell decreases, and additional noise sources must be considered. Secondary photons can be produced during an avalanche in one cell. Because they are emitted isotropically, they can create avalanches in neighboring cells, which is called direct (DiCT) or delayed crosstalk (DeCT). 
Another correlated noise source is the diffused afterpulsing (APdiff). It arises when the secondary photon is re-absorbed in the same cell with the generated carrier diffusing and reaching the depleted region with a certain delay [[2018SiPM]].


The gain of a SiPM is typically between few $10^5$ and $10^6$, similarly to a [[PMT]].
A SiPM, also known as a Multi-Pixel Photon Counter (MPPC), is an array of parallel-connected single-photon avalanche diodes (SPAD) implemented on a silicon substrate.
SPADs are photodetectors based on avalanche multiplication processes in a p-n junction. 
A schematic view representation of a SPAD cross-section within a SiPM is shown in \hyperref[]{fig.\,\si{}} They are operated with a bias voltage $V_\text{Bias}$ above the breakdown voltage $V_\text{BD}$, which is called Geiger Mode. In this mode, the SPAD is a binary photodetector. The electric field is so high that a single electron-hole pair generated or injected into the depletion region is accelerated and can trigger a self-sustaining avalanche multiplication process.
When such an avalanche is triggered, the current rises within nanoseconds to the milliampere range. If the primary carrier was generated by a photon, the leading edge of the pulse marks the arrival time of the detected photon.
To stop the self-sustaining avalanche current after a photon-triggered breakdown
the bias voltage lowered down to or below the breakdown voltage. 
The electric field is no longer able to accelerate the carriers with a sufficient energy.
This process is called quenching and is enabled by specific quenching circuits described in \citep{1996SPADs}. After quenching, the SPAD must be reset by restoring the bias voltage to be able to detect another photon. \\
The noise sources in SPADs can be divided into primary noise, which is all avalanche pulses due to thermally generated carriers, and correlated noise due to afterpulsing effects. Afterpulsing occurs due to the effect of "trapped" carriers that are only released with a delay after the avalanche pulse, triggering new avalanches not related to a measured photon.\\
In a SiPM each SPAD serves as one square pixel cell. The pixel cells have typical dimensions in the $15-70/,/si{\mu m}$ range and are densely arranged on the substrate.  If the number of photons is lower than the number of cells on the SiPM, this results in a low probability of more than one photon hitting a single cell within the time window specified by the time resolution. That means that the number of dropped pixels is proportional to the number of incoming photons. The signals of the individual SPAD cells of a SiPM are combined via the quench resistors. The pulse spectrum and output pulses for different numbers of dropped SiPM pixels can be seen in \hyperref[]{fig\,\ref{}} .
SiPMs have two major advantages over other single-photon diodes: their scalability and the additional advantage of being photon-number resolved.
Due to the implementation of multiple SPADs in one device and the combination of the signal, the ratio between the sensitive area and the total area of the cell decreases and some more noise sources have to be considered. 
Secondary photons can be produced during an avalanche in one cell. Because they are emitted isotropically, they can create avalanches in neighboring cells, which is called direct (DiCT) (see fig.) or delayed crosstalk (DeCT). The correlated noise arises directly if the photon is absorbed in the depleted region and is delayed by a few ns if it is absorbed in the neutral region.
Another correlated noise source is the diffused afterpulsing (APdiff). It arises when the secondary photon is reabsorbed in the same cell with the generated carrier diffusing and reaching the depleted region with a certain delay.
A schematic illustration and a typical measurement of these noise effects can be seen in fig. 

The SiPMs in CheapCal and the [[WOM]] vessels of the [[SHiP]] SBT detector are the Hamamatsu MPPC (Multi-Pixel Photon Counter©) model S14160-3050HS.\citep{HamamatsuSipm}
The have an effective photosensitive area of  $(3×3)\,\si{mm}^2$, with 3531 cells and a typical gain of $2.5\cdot10^6$ . They are operated with a voltage of $V_\text{OP}= (V_\text{BR}+2.7)\,\si{V} = 40.7\,\si{V}$ with the breakdown voltage $V_\text{BR} = 38\,\si{V}$. They have a spectral response range from  270 to 900nm and are optimized for a wavelength  of 450nm. 
The dependence of the photon detection efficiency of these SiPMs on the wavelength is shown in 2.4.
Photon detection efficiency is the ratio between the number of detected photons and those arriving at the detector. It is the product of the quantum efficiency and the avalanche-triggering probability









For thin-junction SPAD’s 1i2 the breakdown voltage
VB isfrom10to50V;1ii2theactiveareaissmallwith
a diameter from 5 to 150 µm;; 1iv2
resolution is very high in photon timing ,remarkably better than 100 ps FWHM.