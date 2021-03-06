# OGGM Mass-Balance sandbox

Next generation of OGGM's mass-balance models. Work in process!

At the moment these options are available:
- to compute degree days:
    - using monthly temperatures ('mb_monthly'), default option in OGGM
    - using monthly temperatures and daily temp std to generate daily temp. assuming normal distributed data ('mb_daily')
    - using daily temperatures ('mb_real_daily')
- temperature lapse rates:
    - using a constant calibrated value independent of location and season (-6.5 K/km, grad_type: cte), default option in OGGM
    - using lapse rates from ERA5 that vary throughout the year and inbetween glacier locations, 
    but that are constant inbetween the years (grad_type: 'var_an_cycle')
    - using lapse rates from ERA5 that vary throughout the year and inbetween glacier locations, 
    different for each year (grad_type: 'var_an_cycle')

All options have been tested with the elevation flowline from Huss. 

# How to install/use !
<!-- structure as in https://github.com/fmaussion/scispack and oggm/oggm -->
the newest OGGM developer version has to be installed in order that MBsandbox works:
e.g. do:

    $ conda create --name env_mb
    $ source activate env_mb
    $ git clone  https://github.com/OGGM/oggm.git
    $ cd oggm 
    $ pip install -e .
    $ git clone https://github.com/OGGM/massbalance-sandbox
    $ cd massbalance-sandbox
    $ pip install -e .

Test the installation via pytest while being in the massbalance-sandbox folder:

    $ pytest .

The MBsandbox package can be imported in python by

    >>> import MBsandbox

A simple use case is explained in **docs/how_to_use.ipynb**. 


# inside of MBsandbox
ToDO more nicely ...

- ***mbmod_daily_oneflowline.py***: ***write_climate_file***, ***process_era5_daily_data***, ***mb_modules***
- ***help_func.py***: need helper functions to minimize the bias, optimise std_quot and to compute performance statistics
- **tests_mbmodules**: tests for different functions inside of ***mbmod_daily_oneflowline.py***, ***help_func.py*** and for the ***ERA5_daily*** dataset


# docs/*:

### simple use case: ***how_to_use.ipynb***

### mass balance intercomparison with figures: ***intercomparison_w_figures/****
- ***HEF_mb_type_intercomparison_oneflowline.ipynb***: shows mb type intercomparison for Hintereisferner
    - plots in **figures_hef**
- ***refglaciersAlps_mb_type_intercomparison_oneflowline.ipynb*** : shows intercomparison for Alpine reference glaciers
  plots in:
    - **figures_alps** (performance measures for Alpine reference glaciers)
    - **figures_alps_indiv** (observed and modelled mb time series with performance measures for each Alpine reference glacier 
    - stats_Alps_6mb_models_N_5000_with_mean_an_cycle.csv: dataset of optimal DDFs and performance measures for all Alpine glaciers and all mb types
  
### preprocess_ERA5_daily: this is just a side product
- ***preprocess_ERA5_daily/cluster_aggregate_dailyERA5.ipynb***: how to preprocess the ERA5_daily files
  (end product is here: https://cluster.klima.uni-bremen.de/~oggm/climate/era5/daily/v1.0/)



<<<<<<< HEAD

=======
>>>>>>> origin/master
