---
Title: "Timestamping with phlex in the UBT" 
Year: 2026 
Authors: Matei Climescu 
Tags:  
---
Zotero PDF Link: [PDF](zotero://select/library/items/RAVID6G2) 

Related::  

### Persistent Notes 
%% begin notes %% 
Write notes here! 
 %% end notes %%

### In-text annotations
###### Timestamping with phlex in the UBT [Page 1](zotero://open-pdf/library/items/RAVID6G2?page=1&annotation=7HE8YDQI)
###### Introduction [Page 2](zotero://open-pdf/library/items/RAVID6G2?page=2&annotation=R2SKKT74)
- Took the CUDA muons and ran them  through my tile UBT simulation [Page 2](zotero://open-pdf/library/items/RAVID6G2?page=2&annotation=C5ISQDA3)
*CUDA - Tile UBT simulation - Spill ID- True timestamps - simutamiulas lare tile fine timestamps, large tile coarse timestamps, small tile file , small tiles corase* [Page 2](zotero://open-pdf/library/items/RAVID6G2?page=2&annotation=FW2XBUDU)![[image-2-x227-y57.png]]
###### CUDA muons at the UBT plane [Page 3](zotero://open-pdf/library/items/RAVID6G2?page=3&annotation=6TL8LE2I)
![[image-3-x9-y39.png]]
###### Counter usage [Page 4](zotero://open-pdf/library/items/RAVID6G2?page=4&annotation=SG3XF9KI)
- Each event has a coarse and fine counter timestamp assigned, based on their true time [Page 4](zotero://open-pdf/library/items/RAVID6G2?page=4&annotation=84V7EBVE)
###### Encoders and timestamps [Page 5](zotero://open-pdf/library/items/RAVID6G2?page=5&annotation=7IP5GMLU)
- Encoder values are spread around the true time as expected, the true timestamps are given assuming we are looking at a fraction of a spill normalised to the sum of all weights of the CUDA muons (since they come in after the magnet) [Page 5](zotero://open-pdf/library/items/RAVID6G2?page=5&annotation=ZMNYWXJZ)*Fundamentaly unweighted* [Page 5](zotero://open-pdf/library/items/RAVID6G2?page=5&annotation=ZMNYWXJZ)
###### Reco timestamps [Page 6](zotero://open-pdf/library/items/RAVID6G2?page=6&annotation=MPQZ5KMS)
![[image-6-x10-y65.png]]
- Better performance by small tiles but this is added by hand at the moment, the real profit comes from taking in account light yield, will have a look at that [Page 6](zotero://open-pdf/library/items/RAVID6G2?page=6&annotation=QXM5WTIL)
###### Conclusion [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=35E9CEBM)
- This is a first model of timestamping for our events in the new framework [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=95VBVXGA)
- Need to take into account light yield in different events [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=89MTJDTZ)
- Heiko noted that things such as pile-up should be considered carefully, I agree of course [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=XPG6RBHW)*Oliver will talk about this one Tuesday 12th May - physics meeting?* [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=XPG6RBHW)
- Ideally we use a physics-driven approach here but measurements are tough [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=UF8IUC22)
- Reached out to friends from NuScope who may have something we need here, also looking at  POKER [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=TX7478W6)
- Will play a bit with different simulation configurations otherwise [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=Q7Q6N2K7)
- DIS also has to be carefully looked at, thankfully, the UBT simulation already has all of  the required infrastructure [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=PDT8YCY7)
- Feedback is very welcome here, will anyway have to iterate on the current version [Page 7](zotero://open-pdf/library/items/RAVID6G2?page=7&annotation=KDVH8GDX)


%% Import Date: 2026-05-07T10:29:54.549+02:00 %%
