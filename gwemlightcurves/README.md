# gwemlightcurves  

gwemlightcurves is a free software backage that is available at https://github.com/mcoughlin/gwemlightcurves. It can be used to predict and analyse lightcurves and to connect the lightcurves to ejecta parameters as well as binary properties. Further details about the installation and general usage can be found on the main gwemlightcurves webpage.  
For further questions, please contact M. Coughlin, who is the main developer of gwemlightcurves.  


### GW170817

One can generate the lightcurve fit to ejecta parameters, using the command:  

Using the Bulla (2019) model:  
*python run_lightcurves_models.py --doEvent --model Bu2019lm --name GW170817 --tmin 0.00 --tmax 14.00 --filters u,g,r,i,z,y,J,H,K --errorbudget 1.00 --colormodel a2.0  --doFixZPT0 --doEjecta*

Using the Kasen et al. (2017) model:  
*python run_lightcurves_models.py --doEvent --model Ka2017 --name GW170817 --tmin 0.00 --tmax 14.00 --filters u,g,r,i,z,y,J,H,K --errorbudget 1.00 --colormodel a2.0  --doFixZPT0 --doEjecta*

It also supplies the fitting formulas to translate ejecta parameters to mass and EOS constraints, see for example,
https://github.com/mcoughlin/gwemlightcurves/tree/master/gwemlightcurves/EjectaFits

The specific call is:  
*python run_fitting_models.py --doLightcurves --doEvent --model Bu2019lm --name GW170817 --tmin 0.00 --tmax 14.00 --filters u,g,r,i,z,y,J,H,K --errorbudget 1.00  --doFixZPT0 --doJointDisk --lambdamin 0 --lambdamax 700*

### GW190425

The analysis for GW190425 is similar, although we are using limits instead of fitting so there are extra parameters:  

Using the Bulla (2019) model:  
*python run_lightcurves_models.py --doEvent --doEjecta --model Bu2019lw --name GW190425 --tmin 0.1 --tmax 3.0 --filters g,r --limits 20.4,20.4 --distance 156.0 --distance_uncertainty 41.0 --errorbudget 0.10 --doFixZPT0 --doFixedLimit --doWaveformExtrapolate --doFixTheta --theta 0 --doFixMdyn --mdyn 0.005*

Using the Kasen et al. (2017) model:  
*python run_lightcurves_models.py --doEvent --doEjecta --model Ka2017 --name GW190425 --tmin 0.1 --tmax 3.0 --filters g,r --limits 20.4,20.4 --distance 156.0 --distance_uncertainty 41.0 --errorbudget 0.10 --doFixZPT0 --doFixedLimit --doWaveformExtrapolate --doFixXlan --Xlan 1.0e-09*

The ejecta parameter call is then similar to the first case, with one extra parameter:
*python run_fitting_models.py --doLightcurves --doEvent --model Bu2019lm --name GW190425 --tmin 0.1 --tmax 3.00 --filters g,r --errorbudget 1.00  --doFixZPT0 --doJointDisk --doFixedLimit --lambdamin 0 --lambdamax 700*


The Hubble Constant analysis uses KNe_stdcandle.py (with a conservative errorbudget of 1.0 magnitude). The specific commands are:  

Using the Bulla (2019) model:  
*python KNe_stdcandle.py -a inferred -f gpr -l lm -m Bu2019lm -e 1.0*

Using the Kasen et al. (2017) model:  
*python KNe_stdcandle.py -a inferred -f gpr -l lm -m Ka2017 -e 1.0*

