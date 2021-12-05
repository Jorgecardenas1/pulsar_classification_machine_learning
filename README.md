<h1 align="center">Machine Learning Models for Pulsar Classification</h1>
<h2 align="center">Evaluation ML techniques to improve Pulsar's Classification Tasks</h2>

<img src="https://img.shields.io/badge/v1-mcmc-green" ><img src="https://img.shields.io/badge/python-3-yellowgreen" >


---




## Quick summary: ##

* EDGES is a project in the look for the 21-cm line. Since 2018 they provided information about a potential detection of such signal, but the models are being revised. In particular, the T sky model is under review.

* We have applied **Markov Chain Monte Carlo** in particular Metropolis-Hastings, to estimate the proposed model parameters.


    - Version: 1.0
   -   [Share this repo](https://bitbucket.org/jcardenas0/edges_mcmc_metropolis/)

## Content ##
```
root
│   README.md
│       
└───MCMC_SkyModel
   │   figure1_plotdata.csv
   │   EDGESSimulationV3.ipyb
   └───mc_sim
       │   imports.py
       │   MCMC.py
       │   models.py
       │   montecarlo.py
```

### Setup and run ###
1. Open EDGESSimulationV3.ipyb
2. The notebook is set in a way that it downloads and installs all dependencies required to run.

3. Make sure to set the following parameters which are required for the MCMC to run.
Also notice that you will get a folder with plots and data from the estimation process. The folder will be named by the test_to_run constante.

```python
num_walkers=5
num_samples=25000
burn_sample=1000
test_to_run ="test_15"

```

4. ***MCMC Module***:
This modules includes all function for sampling, evaluating loglikelihood and the main function for the metropolis hastings algorithm.

The main method is Metropolis.MH()

```python
result,dataframe = Metropolis.MH(sky_model,
                                 parameters,
                                 t_sky_data,
                                 sigma_parameter,
                                 evaluateLogLikelihood,
                                 initial_point,
                                 num_walkers,
                                 num_samples,
                                 burn_sample)
```

| Method                	| Description                                                            	|
|-----------------------	|------------------------------------------------------------------------	|
| sky_model             	| Function to be evaluated during the MCMC run                           	|
| parameters            	| Dictionary with parameters being tested, with ther min and max values. 	|
| t_sky_data            	| Data loaded from data frame containing truth values.                   	|
| sigma_parameter       	| Sigma value to be used for the loglikelihood evaluation                	|
| evaluateLogLikelihood 	| Function to evaluate loglikelihood every iteration                     	|
| initial_point         	| initial value for the THETA vector. It is a random sample.             	|
| num_walkers           	| Walkers to be used during the run.                                     	|
| num_samples           	| Samples to be used during run.                                         	|
| burn_sample           	| The number of samples tu be burned from the markov chain.              	|
|                       	|                                                                        	|
____

### Results ###

* You will get multiple outputs.
    
    * A folder  named by test_to_run variable with images generated by the run.
    * Same folder with CSV file containing all data from the run. 

![Scheme](MCMC_SkyModel/Results/pair_plot_KDE_Test9.png)