Solid angle calculation:
- total surface area of the unit sphere $4\pi$
- The formula for the magnitude of the solid angle in steradians is:
$$ \Omega = \frac{A}{r^2}$$
- with $A = \pi (d/2)^2$ the Area of the surface of the sphere with a diameter $d$ and $r$ the radius of the sphere
 The ratio 
$$\frac{\Omega}{4\pi} = \pi d^2 \frac{1}{16\pi r^2} = \frac{d^2}{16r^2}$$
With $d = 1\,$mm, $r = 1\,$mm
$$ = 1/16 = 6.25\%$$
With $d = 1\,$mm, $r = 3\,$mm
$$1/144 = 0.69\bar{44}\%$$
With $d = 1\,$mm, $r = 6\,$mm
$$ = 1/576 = 0.1736\%$$

### How much light is absorpt in the first layer? 
non-absorbing, plane-parallel PMMA plate in air:
- Assuming both layers a 10$\mu m$ thick the total transmission:
$$\Phi_T=T_{tot}\Phi_0\text{exp}(\frac{-2d_{WLS}}{l_{WLS}})$$

with $n_{PMMA} = 1.49$:
$$T_{tot} = \frac{2n_{PMMA}}{1+n_{PMMA}^2} = 0.9254$$
So the fraction transmitted through the first layer becomes: 
$$\frac{\Phi_T}{\Phi_0}=T_{tot}\text{exp}(\frac{-d_{WLS}}{l_{WLS}}) = 0.663$$
Assuming that this light hits the second layer then 
$$ 0.663 \cdot 0.625 = 4.14442\%$$ secondary photons potentially hit the second dye layer 