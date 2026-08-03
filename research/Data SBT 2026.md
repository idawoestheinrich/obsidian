---
Title: "Data of SBT" 
Year: 2026 
Authors:  
Tags:  
---
Zotero PDF Link: [Data_SBT.pdf](zotero://select/library/items/DHVLCD5T) 
### In-text annotations
###### What SBT should measure [Page 2](zotero://open-pdf/library/items/DHVLCD5T?page=2&annotation=XVFMMC47)

| Name                 | Bit | Infos                                                                                                                                                                       |
| -------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Container_ID         | 8   | 8 ID = 0 ... 24: bottom; 32 ... 56: top; 128... 167: Saleve; 192 ... 231: Jura  4 leading bits identify the detector side 0000: bottom, 0001: top, 10xx: Saleve, 11xx: Jura |
| Cell_in_Container_ID | 3   | cell_ID= 0 ... 5                                                                                                                                                            |
| SIPM_channel_ID      | 4   | channel = 0 ... 15                                                                                                                                                          |
| Time                 | 22  | leading bit identifies WOM A and B in a cel                                                                                                                                 |
| Time_over_Threshold  | 14  |                                                                                                                                                                             |
| Type                 | 2   | 00 ... 11 – give information on method for Time_over_Threshold                                                                                                              |
###### Counter [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=46KB7JXH)
- 2 timers „counter“ [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=68JY9LEV)
- If frequency + count known => time [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=TYNSAXZY)
- Chip = FastIC+ [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=L5PX5NE4)
- Precision Counter: period 25ps with 22 bits [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=LJW7YL37)
- Coarse Counter: period 25ns with 24 bits [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=6L4YAY8M)
- If counter reaches max => set back to 0 [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=IFFYHJ92)
- Timeframe testbeam: 0.4s between each spill [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=IA3SUBL9)
- Write 1 s in storage with each bit = 25 ps  => huge storage mit 38 bits (inefficient) [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=YCIN8JJM)
- Precision Counter measures time precisely, but overflows fast [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=I5WS4W56)
- Slow Course Counter, allows to classify time from precision counter [Page 3](zotero://open-pdf/library/items/DHVLCD5T?page=3&annotation=PXD4BLMJ)
###### What SBT should measure [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=8UBVVEA6)
- Additional data could be... [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=FS28EMLK)
- Fast Controll: Voltage and Current SiPM PCB [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=LUQR3NIU)
- Slow Controll: [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=IELRS83Q)
- Temperatur [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=7SJ6T8YY)
- Filling Level connected to Nitrogen pressure [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=N3HSF3K7)
- (Current of Container Concentrator?) [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=69THPUNN)
- Data rate at Container Concentrator [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=RVKZ9R7K)
- LED response to SiPMs (voltage?, puls length?) [Page 4](zotero://open-pdf/library/items/DHVLCD5T?page=4&annotation=ZJXUJ76U)
