---
Title: Development and Performance Evaluation of the Wavelength-shifting Optical Module for the IceCube Upgrade
Year: 2025
Authors: Yuriy Popovych
Tags:
theme: simple
height: 566
margin: 0
maxScale: 6
---
Zotero PDF Link: [PDF](zotero://select/library/items/4VJIWAQF) 

Related::  

### Persistent Notes 
%% begin notes %% 
Write notes here! 
 %% end notes %%

### In-text annotations
###### Optical Modeling [Page 44](zotero://open-pdf/library/items/4VJIWAQF?page=44&annotation=2VYQQAS8)
- <mark class="hltr-yellow">Several frameworks and models were developed to describe and study different  optical properties of the WOM such as timing and efficiency. In this section, different  simulation tools and analytical models will be introduced.</mark> [Page 44](zotero://open-pdf/library/items/4VJIWAQF?page=44&annotation=QZLR6BHM)
![[image-59-x113-y679.png]]
- <mark class="hltr-yellow">Visualization of propagated photons through the inner WOM tube using Zemax. One can see captured rays as well as rays which are scattered out of the tube.</mark> [Page 45](zotero://open-pdf/library/items/4VJIWAQF?page=45&annotation=UHCNMXYM)
- <mark class="hltr-yellow">This results in a distribution of xyz-coordinates and spherical angles of  all photons as well as the propagated distance. As the propagation of every photon  happens independently, this algorithm can be parallelized on GPUs to simulate  millions of photons within a few seconds.</mark> [Page 45](zotero://open-pdf/library/items/4VJIWAQF?page=45&annotation=EX86XKTX)
###### Flattened Efficiency Model [Page 45](zotero://open-pdf/library/items/4VJIWAQF?page=45&annotation=PEDPM2JS)
- <mark class="hltr-yellow">The efficiency of the inner WLS tube can be approximated analytically by the flattened model [16]. The hollow cylinder is approximated as a "flattened out" cuboid  neglecting its curvature (see Fig. 4.15)</mark> [Page 45](zotero://open-pdf/library/items/4VJIWAQF?page=45&annotation=9PVPKS7S)
![[image-60-x79-y529.png]]
- <mark class="hltr-yellow">From geometrical considerations we get for the traveled photon distance l</mark> [Page 46](zotero://open-pdf/library/items/4VJIWAQF?page=46&annotation=Q525ND77)
![[image-60-x237-y415.png]]
- <mark class="hltr-yellow">Using the Beer-Lambert-Law we can determine the angular dependent efficiency ε  given the attenuation length λatt</mark> [Page 46](zotero://open-pdf/library/items/4VJIWAQF?page=46&annotation=R6GI3QC9)
![[image-60-x154-y329.png]]
- <mark class="hltr-yellow">To get the overall distant dependent efficiency, we integrate this expression over all  possible angles θ, φ. The range the θ is limited to the photon staying within the TIR  angle θC</mark> [Page 46](zotero://open-pdf/library/items/4VJIWAQF?page=46&annotation=8V5PY9BW)
![[image-60-x128-y225.png]]
$$\epsilon(d) = \frac{1}{4\pi}\int^{\theta_C}_{\theta_C}\exp(-\frac{d}{\lambda_{att}\cos(\theta)\cos(\phi)})\cos(\theta
)d\phi d\theta$$

- <mark class="hltr-yellow">While the model captures all photons within  the TIR angle it does not consider for photons being emitted close to the tube’s end</mark> [Page 46](zotero://open-pdf/library/items/4VJIWAQF?page=46&annotation=W9YKRIWC)
![[image-61-x111-y508.png]]
- <mark class="hltr-yellow">hitting the PMT even through θ < θC (direct hits).</mark> [Page 47](zotero://open-pdf/library/items/4VJIWAQF?page=47&annotation=V7KLTM6N)
- <mark class="hltr-yellow">Similarly, the possibility of an  non-captured photon which is scattered towards the PMT is not considered.</mark> [Page 47](zotero://open-pdf/library/items/4VJIWAQF?page=47&annotation=RMTKF2RW)
- <mark class="hltr-yellow">These  effects have proven to be small and only relevant for small d < 10 cm. Therefore  we can conclude that the used approximation is of sufficient precision for the given  tube parameters.</mark> [Page 47](zotero://open-pdf/library/items/4VJIWAQF?page=47&annotation=9BKX5CBV)
###### Self-Absorption Model [Page 47](zotero://open-pdf/library/items/4VJIWAQF?page=47&annotation=TS2CBXVV)
- <mark class="hltr-yellow">The flattened model and the simulation both do not distinguish between the tube and  paint layer as both are modeled as bulk with one refractive index and attenuation  length.</mark> [Page 47](zotero://open-pdf/library/items/4VJIWAQF?page=47&annotation=CRZAVJ8F)
- <mark class="hltr-yellow">An analytical modeling of the self-absorption expands the flattened model by introducing a wavelength dependency to the efficiency ε(d, θ, φ, λ) of each propagated  photon which is changing depending on the traveled distance.</mark> [Page 47](zotero://open-pdf/library/items/4VJIWAQF?page=47&annotation=CIRJ375B)
- <mark class="hltr-yellow">Comparing the self-absorption modeling with the flattened model in Fig. 4.18  outlines better fitting results for the self-absorption model for small distances.</mark> [Page 48](zotero://open-pdf/library/items/4VJIWAQF?page=48&annotation=N2H33A7T)
![[image-63-x110-y449.png]]
27% auf 25% bei 10 auf 20 cm 
29% auf 25% bei 5 auf 20 cm
%% Import Date: 2026-03-10T13:59:42.309+01:00 %%

[[Comparison data testbeam WOMs with IceCube simulation]]