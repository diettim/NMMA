
gwemlightcurves, available at https://github.com/mcoughlin/gwemlightcurves, can be used to generate the lightcurve fit to ejecta parameters, using the command like below:

Using the Bulla (2019) model:
python run_lightcurves_models.py --doEvent --model Bu2019lm --name GW170817 --tmin 0.00 --tmax 14.00 --filters u,g,r,i,z,y,J,H,K --errorbudget 1.00 --colormodel a2.0  --doFixZPT0 --doEjecta

Using the Kasen et al. (2017) model:
python run_lightcurves_models.py --doEvent --model Ka2017 --name GW170817 --tmin 0.00 --tmax 14.00 --filters u,g,r,i,z,y,J,H,K --errorbudget 1.00 --colormodel a2.0  --doFixZPT0 --doEjecta

It also supplies the fitting formulas to translate ejecta parameters to mass and EOS constraints, see for example,
https://github.com/mcoughlin/gwemlightcurves/tree/master/gwemlightcurves/EjectaFits

The specific call is:
python run_fitting_models.py --doLightcurves --doEvent --model Bu2019lm --name GW170817 --tmin 0.00 --tmax 14.00 --filters u,g,r,i,z,y,J,H,K --errorbudget 1.00  --doFixZPT0 --doEjecta --lambdamin 0 --lambdamax 700

