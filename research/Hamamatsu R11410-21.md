The model used in this case is Hamamatsu R11410-21 (maybe R11410-2A)
serial number KB3048

- high voltage of -1500 V (negative!). Depending on the PMT, -1250 V is sometimes sufficient. Apply a maximum of -1750 V!
- Window thickness 3.5mm


- https://hep.hamamatsu.com/eu/en/products/R11410-20.html
- The PMT was developed for cryogenic liquid xenon (-100°C). It, therefore, has a bialkali photocathode and a quartz window. The sensitive range is from 160 nm to 650 nm and includes, in particular the VUV range of Xe scintillation light (175 nm)
- Quantum efficiency on p.75 (pdf) here: https://hep.hamamatsu.com/content/dam/hamamatsu-photonics/sites/documents/99_SALES_LIBRARY/etd/High_energy_PMT_TPMZ0003E.pdf
- This is a low-background PMT (details on production/materials are coded in the -xx number). “-21” is the production batch for the XENON experiment.
- The PMT is expensive (approx. 7000 EUR). Please handle it with care!
- You need an approximate high voltage of -1500 V (negative!). Depending on the PMT, -1250 V is sometimes sufficient. Apply a maximum of -1750 V!
- typical gain: ~5e6 at -1500 V typical
- IMPORTANT: the body of the PMT is made of metal (Kovar) and is at cathode potential, i.e. at high voltage! Make sure to install it well insulated!!!
- There is a metal ring in the box for mounting. You can use it, but you don't have to. (I have never done this).
- There is a PCB base on the PMT. The design is optimized for the smallest signals (dark matter search!); electrical components are radioactive and have been saved. We know that the base is no longer linear for large signals!
- the predetermined breaking point of the PMT are the pins. If you have to remove the base, be very careful, especially when putting it back on! The orientation of the base and PMT is defined by the bulge of the base and the point on the PMT (on a pin).
- At the base is a short RG196 coax cable (50 Ohm) for the signal. It has a MMCX coax plug crimped to it. I have added a short RG196 with the mating connector. The easiest way is to attach a connector (BNC, Lemo etc.) that you can use to the open end of it
- the high voltage is applied via two super thin Kapton cables. One for the HV, the other for the HV return. Here you have to think about how to adapt this for you (you probably need SHV). We usually run several of the PMTs together and collect all HV returns on one line, which we then feed back to the (floating) HV supply. This way we avoid HV return and GND coming together (->ground loops etc). If you can leave the Kapton cables on, that would be good for my next application, if it is not possible, then you have to unsolder them and solder a coax cable (conductor and shield) to the appropriate places.
- we need the PMT for low-background applications in xenon detectors: please handle the tube itself only with gloves (powder-free!) to minimize grease (K40) and other contaminants. (I can easily clean the base in an ultrasonic bath, so it is not critical).
- - a few papers on the PMT:
  o https://arxiv.org/abs/2401.00373 (possibly interesting if the base does not work for your purpose)  o https://arxiv.org/abs/1303.0226 and https://arxiv.org/abs/2104.15051 (here you can find average values)
  O https://arxiv.org/abs/1509.04055 (position-dependent photo detection efficiency)
  O https://arxiv.org/abs/1503.07698 (low-background development with Hamamatsu)