---
Title: "TDAnalyser – a modular framework for the analysis of test beam data - 14th Beam Telescopes and Test Beams Workshop" 
Year: 2026 
Authors: L Forthomme 
Tags:  
---
Zotero PDF Link: [PDF](zotero://select/library/items/WP2YJTKY) 

Related::  

### Persistent Notes 
%% begin notes %% 
Write notes here! 
 %% end notes %%

### In-text annotations
###### TDAnalyser in a nutshell [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=ZVQKSCWL)
- <mark class="hltr-yellow">DDOOII 10.5281/zenodo.15773004</mark> [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=3PFQMKHD)
- <mark class="hltr-yellow">a framework for timing (but not only. . . ) detectors characterisation:</mark> [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=SYYXSPIA)
- <mark class="hltr-yellow">base “building block”: timing waveform (map of sample time → amplitude)</mark> [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=PSIC2G9C)
- <mark class="hltr-yellow">flexible extension to user-defined data formats (e.g. rechits, track candidates, time measurements: t0 + ToT)</mark> [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=43YFM92Y)
- <mark class="hltr-yellow">native support of parameters scans</mark> [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=3GL7Q6WF)
- <mark class="hltr-yellow">C++20 standard for max. compatibility with common stacks, easy install on various working environments (LXPLUS, . . . incl. personal *NIX laptop!)</mark> [Page 3](zotero://open-pdf/library/items/WP2YJTKY?page=3&annotation=R5HHZDS5)
![[image-6-x73-y103.png]]
- <mark class="hltr-yellow">Along all analyses, 2 streams defined, and made available to all analyser components through I/O API:</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=MTLL8UP2)
- <mark class="hltr-yellow">event/trigger-based, to store all collections time-consuming to produce on an event-by-event basis</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=9F7ZVINV)
- <mark class="hltr-yellow">waveforms</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=3X8FS6RX)
- <mark class="hltr-yellow">time measurements</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=IGGNU69C)
- <mark class="hltr-yellow">run-based,</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=3HAYY9E6)
- <mark class="hltr-yellow">per-channel timing resolution</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=R27LJXVT)
- <mark class="hltr-yellow">MPV for Landau fit of all maximum aplitudes in one channel, . . .</mark> [Page 4](zotero://open-pdf/library/items/WP2YJTKY?page=4&annotation=UMU7JPPN)
###### TDA analysis workflow [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=UG2FCGYD)
- <mark class="hltr-yellow">pre-analysers chain</mark> [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=53U8XCCJ)
- <mark class="hltr-yellow">analysers chain</mark> [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=DHJ4T8NM)
- <mark class="hltr-yellow">collect/analyse the combination of multi-channel information</mark> [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=PHJ2HSJR)Baseline correction [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=PHJ2HSJR)
- <mark class="hltr-yellow">allows the processing/filtering/characteristics extraction of single waveforms</mark> [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=BTXC7UVS)
- <mark class="hltr-yellow">CFD, band pass filter, polarity inversion/baseline subtraction,</mark> [Page 5](zotero://open-pdf/library/items/WP2YJTKY?page=5&annotation=8QSZVSY8)
- <mark class="hltr-yellow">TDAnalyser input formats</mark> [Page 6](zotero://open-pdf/library/items/WP2YJTKY?page=6&annotation=CW4TVD5X)
- <mark class="hltr-yellow">Sampic: merged trigger+samples, and split trigger/samples  modes (sampiclib wrapper)</mark> [Page 6](zotero://open-pdf/library/items/WP2YJTKY?page=6&annotation=RFMKYNSE)
###### Native RNTuple support [Page 8](zotero://open-pdf/library/items/WP2YJTKY?page=8&annotation=RRU47LRQ)
- <mark class="hltr-yellow">ROOT::RNTupleModel-based EDM for bookkeeping of transient/persistent collections</mark> [Page 8](zotero://open-pdf/library/items/WP2YJTKY?page=8&annotation=VNSA7AUH)
###### A (selected) list of ongoing development activities [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=PJVRQP8U)
- <mark class="hltr-yellow">more input formats unpacking, incl. very user-specific data formats</mark> [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=VSB4UZFJ)
- <mark class="hltr-yellow">multi-threaded processing</mark> [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=735MRSPX)
- <mark class="hltr-yellow">support of multi-reader runs: merging multiple synchronous DAQ streams (incl. relative trigger offsets)</mark> [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=KCZ4MCR9)
- <mark class="hltr-yellow">DD4hep interfacing</mark> [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=5SH37R4X)
- <mark class="hltr-yellow">tracking: wrapping of ACTS Common Tracking Software under development</mark> [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=25NG584Z)
- <mark class="hltr-yellow">help timing detectors testing’s data preservation</mark> [Page 23](zotero://open-pdf/library/items/WP2YJTKY?page=23&annotation=8FY88Y6P)
###### Conclusions & take-home messages [Page 24](zotero://open-pdf/library/items/WP2YJTKY?page=24&annotation=UXWVEGLV)
- <mark class="hltr-yellow">TDAnalyser as a tool to ease analyses workflows</mark> [Page 24](zotero://open-pdf/library/items/WP2YJTKY?page=24&annotation=45P68QX8)
- <mark class="hltr-yellow">base object: sampled waveforms</mark> [Page 24](zotero://open-pdf/library/items/WP2YJTKY?page=24&annotation=5SBNK7ZR)
- <mark class="hltr-yellow">easy extension to user-defined formats (ROOT reflex + RNTuple I/O)</mark> [Page 24](zotero://open-pdf/library/items/WP2YJTKY?page=24&annotation=UVDZYEAS)
- <mark class="hltr-yellow">(growing) documentation available at https://tdanalyser.docs.cern.ch, supporting paper in preparation</mark> [Page 24](zotero://open-pdf/library/items/WP2YJTKY?page=24&annotation=5RM72TLF)
- <mark class="hltr-yellow">enlarging our user base:</mark> [Page 24](zotero://open-pdf/library/items/WP2YJTKY?page=24&annotation=WUT5ALRX)


%% Import Date: 2026-04-16T09:43:22.983+02:00 %%
