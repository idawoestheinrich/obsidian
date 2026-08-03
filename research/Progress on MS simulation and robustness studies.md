---
Title: "Framework updates and Robustness analysis" 
Year: 2025 
Authors: Luís Felipe P Cattelan 
Tags:  
---
Zotero PDF Link: [PDF](zotero://select/library/items/4VZGF3C8) 

Related::  

### Persistent Notes 
%% begin notes %% 
Write notes here! 
 %% end notes %%

### In-text annotations
###### Muon Shield Optimization  Framework updates and Robustness analysis
###### Ultra-fast Muon Transport  Heuristic for MC simulation using GPU parallelization
###### Current Soware Framework
- <mark class="hltr-yellow">Geant4 + FEM</mark> [Page 3](zotero://open-pdf/library/items/4VZGF3C8?page=3&annotation=8ZBWP6PT)
- <mark class="hltr-yellow">~4 hours for 1 simulation  • Using heavy CPU clusters</mark> [Page 4](zotero://open-pdf/library/items/4VZGF3C8?page=4&annotation=TI872DSF)
- <mark class="hltr-yellow">• muons</mark> [Page 4](zotero://open-pdf/library/items/4VZGF3C8?page=4&annotation=HYQ6EVM7)
- <mark class="hltr-yellow">3 minutes for 1 simulation  • Using heavy CPU clusters</mark> [Page 4](zotero://open-pdf/library/items/4VZGF3C8?page=4&annotation=XNGKKK6E)
- <mark class="hltr-yellow">Can lead to poor generalization</mark> [Page 4](zotero://open-pdf/library/items/4VZGF3C8?page=4&annotation=NRTQ54YK)
- <mark class="hltr-yellow">Full sample</mark> [Page 4](zotero://open-pdf/library/items/4VZGF3C8?page=4&annotation=5BUYMQI7)
- <mark class="hltr-yellow">Optimization sample</mark> [Page 4](zotero://open-pdf/library/items/4VZGF3C8?page=4&annotation=MUNX488W)
###### CUDA heuristic for muon transport
- <mark class="hltr-yellow">Idea: sample momentum dissipation from Geant4 and build histograms</mark> [Page 5](zotero://open-pdf/library/items/4VZGF3C8?page=5&annotation=PMF96DAT)
- <mark class="hltr-yellow">Simulate muons interaction with matter by sampling from these histograms</mark> [Page 5](zotero://open-pdf/library/items/4VZGF3C8?page=5&annotation=6KL4X4RK)
- <mark class="hltr-yellow">Magnetic force: 4th order Runge-Kutta integration</mark> [Page 5](zotero://open-pdf/library/items/4VZGF3C8?page=5&annotation=9JGRCVC5)
- <mark class="hltr-yellow">Massive parallelization using GPUs (CUDA)</mark> [Page 5](zotero://open-pdf/library/items/4VZGF3C8?page=5&annotation=2V3E4ZUL)
###### Results comparison
- <mark class="hltr-yellow">Full sample in ~4 minutes*</mark> [Page 6](zotero://open-pdf/library/items/4VZGF3C8?page=6&annotation=GB8FRMKQ)
- <mark class="hltr-yellow">Optimization sample in ~2 seconds  • FEM still takes ∼ 7 − 20 seconds.</mark> [Page 6](zotero://open-pdf/library/items/4VZGF3C8?page=6&annotation=YRRH3V7I)
Stochastic simulation, if you run multiple times this will varii a lot. When we have a bigger number of simultaions they are basically equal [Page 6](zotero://open-pdf/library/items/4VZGF3C8?page=6&annotation=UVH488DW)![[image-6-x1310-y77.png]]
- <mark class="hltr-yellow">Using 1 GPU. Can be split in N GPUs</mark> [Page 6](zotero://open-pdf/library/items/4VZGF3C8?page=6&annotation=54YDXP72)Reduce the amount of computation power- cheaper [Page 6](zotero://open-pdf/library/items/4VZGF3C8?page=6&annotation=54YDXP72)
###### Robustness studies  Sensitivity analysis of optimized parameters
###### Magnets template  Warm configuration
![[image-8-x603-y141.png]]
###### Local optimization
###### Robustness analysis
- <mark class="hltr-yellow">• GOAL: Understand the sensitivity in relation to possible fluctuations  • For specific parameter :  • Simulate muon rate with  δφ  φi   ̃  φ = φ* ± [0,0,⋯, δφi, ⋯,0,0]</mark> [Page 10](zotero://open-pdf/library/items/4VZGF3C8?page=10&annotation=DMLZFWT9)
- <mark class="hltr-yellow">Zero order robustness analysis</mark> [Page 10](zotero://open-pdf/library/items/4VZGF3C8?page=10&annotation=774A6JHI)
###### Robustness  Zero-order
- <mark class="hltr-yellow">Limitations:  • Stochasticity  • Number of hits naturally varies due to MC simulations</mark> [Page 12](zotero://open-pdf/library/items/4VZGF3C8?page=12&annotation=YRQ5HECM)
###### Zero order robustness analysis
- <mark class="hltr-yellow">Geant4 is not differentiable  • Let’s build a differentiable surrogate  model (neural network)</mark> [Page 13](zotero://open-pdf/library/items/4VZGF3C8?page=13&annotation=LZMBERVX)
- <mark class="hltr-yellow">LGSO - Estimating gradients</mark> [Page 13](zotero://open-pdf/library/items/4VZGF3C8?page=13&annotation=QZCJW3ZH)
###### Differentiable model
- <mark class="hltr-yellow">Differentiable model</mark> [Page 14](zotero://open-pdf/library/items/4VZGF3C8?page=14&annotation=7RE79EPK)
###### Surrogate model for number of hits
- <mark class="hltr-yellow">Since we are just interested in local  behavior, we train by sampling  parameters around the current  one  φ</mark> [Page 15](zotero://open-pdf/library/items/4VZGF3C8?page=15&annotation=L8SAPVL5)
###### Robustness analysis
- <mark class="hltr-yellow">Second order expansion</mark> [Page 16](zotero://open-pdf/library/items/4VZGF3C8?page=16&annotation=SGDZS8RU)
- <mark class="hltr-yellow">Local-optimal parameters condition:</mark> [Page 16](zotero://open-pdf/library/items/4VZGF3C8?page=16&annotation=FE8P3JWA)
- <mark class="hltr-yellow">Spectral theorem:</mark> [Page 17](zotero://open-pdf/library/items/4VZGF3C8?page=17&annotation=TVX9VLLR)
###### Performance analysis
- <mark class="hltr-yellow">We need to simulate all these points ideally on  full sample</mark> [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=9Q6RZYM7)
- <mark class="hltr-yellow">We can use active learning techniques to  reduce the amount of simulations</mark> [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=MESD2VFY)Future Work [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=MESD2VFY)
- <mark class="hltr-yellow">With Geant4, might take a bunch of days</mark> [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=34EQBFPI)
- <mark class="hltr-yellow">With GPU method, some hours</mark> [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=THUXUDS9)
- <mark class="hltr-yellow">Surrogate model training takes some minutes</mark> [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=3RRCFZ87)
- <mark class="hltr-yellow">Gradient+hessian estimation takes some seconds</mark> [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=CE9CDY7D)The bottleneck is the simulation [Page 18](zotero://open-pdf/library/items/4VZGF3C8?page=18&annotation=CE9CDY7D)
###### Hadron AbsorberExample [Page 19](zotero://open-pdf/library/items/4VZGF3C8?page=19&annotation=RLGWXP2S)
- <mark class="hltr-yellow">Small perturbations in width and height have little impact on the performance</mark> [Page 22](zotero://open-pdf/library/items/4VZGF3C8?page=22&annotation=EY5QTPT5)The highest eigenvalue is the last one- [Page 22](zotero://open-pdf/library/items/4VZGF3C8?page=22&annotation=EY5QTPT5)
- <mark class="hltr-yellow">Increase in Middle gap could bring losses</mark> [Page 22](zotero://open-pdf/library/items/4VZGF3C8?page=22&annotation=84Z45BK4)
- <mark class="hltr-yellow">Decreasing current might damage the performance</mark> [Page 22](zotero://open-pdf/library/items/4VZGF3C8?page=22&annotation=LQCREASF)
- <mark class="hltr-yellow">Parameters: 98</mark> [Page 23](zotero://open-pdf/library/items/4VZGF3C8?page=23&annotation=GLHNP6NQ)
- <mark class="hltr-yellow">Most sensitivity parameters are “trivial” and  not a robustness problem</mark> [Page 23](zotero://open-pdf/library/items/4VZGF3C8?page=23&annotation=6AZZAVT6)
###### All params
- <mark class="hltr-yellow">Parameters: 80</mark> [Page 24](zotero://open-pdf/library/items/4VZGF3C8?page=24&annotation=4BUD4REH)
- <mark class="hltr-yellow">4th magnet</mark> [Page 24](zotero://open-pdf/library/items/4VZGF3C8?page=24&annotation=HX9M95H2)
- <mark class="hltr-yellow">Currents in second section</mark> [Page 24](zotero://open-pdf/library/items/4VZGF3C8?page=24&annotation=QEDMNTDS)
- <mark class="hltr-yellow">Few centimeters in the core of the 4th  magnet might increase hits in O(104)</mark> [Page 24](zotero://open-pdf/library/items/4VZGF3C8?page=24&annotation=U9D5K5BK)
###### All relevant parameters
###### Methodology
- <mark class="hltr-yellow">Analyze sensitivity using surrogate model</mark> [Page 26](zotero://open-pdf/library/items/4VZGF3C8?page=26&annotation=NYTLDGNW)
- <mark class="hltr-yellow">Spot critical parameters and insights</mark> [Page 26](zotero://open-pdf/library/items/4VZGF3C8?page=26&annotation=B4UTD45M)
- <mark class="hltr-yellow">Perform further analysis using Geant4/FairShip simulations</mark> [Page 26](zotero://open-pdf/library/items/4VZGF3C8?page=26&annotation=P4493LRG)
<mark class="hltr-blue">Guglielmo’s talk</mark> [Page 26](zotero://open-pdf/library/items/4VZGF3C8?page=26&annotation=6SUNE957)


%% Import Date: 2025-09-17T12:59:05.034+02:00 %%
