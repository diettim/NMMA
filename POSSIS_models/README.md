Spectral energy distributions (SEDs) computed by POSSIS (Bulla 2019)

**1) FILENAME**

nsns_nphX_mejdynY_mejwindZ_phiW.txt <br/>	
X: number of Monte Carlo packets <br/>	
Y: mass in dynamical ejecta <br/>	
Z: mass in post-merger/wind ejecta <br/>	
W: half-opening angle of the dynamical-ejecta lanthanide-rich component	<br/>

**2) FILE FORMAT**

###################################################<br/>
Nobs (number of viewing angles)<br/>
Nwave (number of wavelength bins)<br/>
Ntime (number of time bins), t_i (days), t_f (days)<br/>
#################### iobs = 0 #####################<br/>
<pre>                itime=0    itime=1 ..........<br/>
iwave=0  wave	  flux      flux   ..........<br/>
iwave=1  wave	  flux      flux   ..........<br/>  
.         .         .         .    ..........<br/>
.         .         .         .    ..........<br/>
.         .         .         .    ..........<br/>
.         .         .         .    ..........<br/> <pre>
#################### iobs = 1 #####################<br/>
.<br/>
.<br/>
.<br/>

	 
**3) NOTES:**

- Viewing angles are from equator (edge-on) to pole (face-on)
  equally-spaced in cosine (e.g. 5 viewing angles corresponds 
  to cosine(theta) = 0, 0.25, 0.5, 0.75, 1).<br/>
- Time bins have step size Dt = (t_f - t_i) / Ntime<br/>
- Reference times are [t_i + 0.5 * Dt, t_i + 1.5 * Dt, ...]<br/>
- Fluxes are given in erg s-1 cm-2 A-1 at the distance of 10 pc<br/>
