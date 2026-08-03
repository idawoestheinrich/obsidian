---
tags:
  - status/wip
  - type/concept
  - topic/detector_physics/mip
aliases:
---
Only necessary if the light yield is introduced as well

To develop effective detection systems, one must understand the underlying physics and technologies that govern their operation. This chapter builds the foundation for the experimental investigations by explaining how energy interacts with matter, how light is produced and manipulated in scintillators, and how it is eventually detected. Each section is tailored to answer specific questions relevant to the thesis.

How can we detect minimum ionizing particles? 
- Their energy loss in mater
- Every detection process begins with energy deposition. Charged particles or photons interacting with the detector medium deposit energy, which is subsequently converted into detectable signals. Thin absorbers are particularly significant for high-resolution detectors, where minimizing material effects is critical.


Die Bethe-Bloch-Formel gibt den mittleren Energieverlust pro Weglänge an. Tatsächlich
ist der Energieverlust aber ein statistischer Prozess mit Fluktuationen: Der Energieverlust
ΔE auf einer Wegstrecke Δx setzt sich aus vielen kleinen Beiträgen δEn, die einzelnen
Ionisations- oder Anregungsprozessen entsprechen, zusammen

Im Allgemeinen führen die Fluktuationen der Energieüberträge in einzelnen Kollisionen zu einer asymmetrischen Verteilung f(ΔE; Δx), die einen gaußförmigen Anteil (entsprechend vielen Ionisationsprozessen mit kleinem Energieverlust) und einen Ausläufer zu großen Energieverlustwerten hat (siehe Abb. 14.9 auf Seite 547 oder Abb. 3.12). Die großen Werte entsprechen den selteneren harten Stößen, bei denen viel Energie auf einzelne Elektronen, die in Abschnitt 3.2.2 besprochenen δ-Elektronen, übertragen wird(Abb. 3.9)
Die exakte Form der Verteilung hängt im Wesentlichen von dem Verhältnis des mittleren Energieverlusts (gegeben durch die Bethe-Bloch-Formel) und des maximalen Energieverlusts ab.

Annahmen Landaus:
(i) T_max (Maximaler Energieübertrag Tmax) kann unendlich groß werden, entsprechend κ → 0;
(ii) die Elektronen werden als frei angenommen, das heißt Schaleneﬀekte bei kleinen Energieüberträgen werden vernachlässigt;
(iii) die Verringerung der Energie des Teilchens während des Durchgangs durch die Schicht wird vernachlässigt.

κ groß −→ f(ΔE; Δx) symmetrisch, Gauß-Verteilung (für κ= 1), Vavilov
κ klein −→ f(ΔE; Δx) stark asymmetrisch, Landau ( κ<=0.01)

 Verallgemeinerung mit einem realistischen maximalen Energieübertrag Tmax, die damit auch für größere κ-Werte gilt, stammt von Vavilov.

Die Vavilov-Verteilung ist wie die Landau-Verteilung in dem Programmpaket ROOT implementiert, wobei die mathematische Formulierung auf der Web-Seite [691] dokumentiert ist.

@book{kolanoski2016teilchendetektoren,
  title={Teilchendetektoren},
  author={Kolanoski, Hermann and Wermes, Norbert},
  year={2016},
  publisher={Springer}
}

Wie wirkt sich diese Form auf das Timing aus?

Energy loss in very this absorbers # 
Energy loss measurement for charged particles in very thin silicon layers

S
Meroli, D Passeri and L Servoli

Published 29 June 2011 • Published under licence by IOP Publishing Ltd  
[Journal of Instrumentation](https://iopscience.iop.org/journal/1748-0221), [Volume 6](https://iopscience.iop.org/volume/1748-0221/6), [June 2011](https://iopscience.iop.org/issue/1748-0221/6/06)**Citation** S Meroli _et al_ 2011 _JINST_ **6** P06013**DOI** 10.1088/1748-0221/6/06/P06013