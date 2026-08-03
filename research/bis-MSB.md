---
tags:
  - status/todo
  - topic/ship/sbt/woms
  - type/concept
aliases:
---
The bis-MSB molecules are the part of the color that absorps photons with a wavelength between 300 and 400nm with a very high efficiency and emitts photons with a peak at 420 nm. 

They are dissolved in PEMA and Toluene:
Rough calculation of the number of Molecules in the color 

	PEMA_ratio = 0.9823 # 26.69% of fluid
	p_Terphenyl_ratio = 0.0192 #0.324% of fluid
	
	bis_MSB_ratio = 0.00574 # 0.156% of fluid
	
	bis_MSB_molar = 310.43 #g*mol^{-1}
	[[WOM]]_inner_radius = 5.8 #cm
	[[WOM]]_outer_radius = 6 #cm
	paint_thickness = 25*10**(-4) #cm (um)
	PEMA_density = 1.15 #g*cm^{-3}
	hight = 23 #cm
	pi = np.pi
	
	N_avogado = 6.022*10**(23) #mol^(-1)
	
	lightcone_radius = 0.05 #cm