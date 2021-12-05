<h1 align="center">Machine Learning Models for Pulsar Classification</h1>
<h2 align="center">Evaluation ML techniques to improve Pulsar's Classification Tasks</h2>

<img src="https://img.shields.io/badge/v1-mcmc-green" ><img src="https://img.shields.io/badge/python-3-yellowgreen" >


---




## Quick summary: ##

* The problem of classifying Pulsars has been approached from different angles, and more recently focus has been put on Machine Learning as a tool to speed the classification process up.

* Here we use a well known pulsars survey database to test different classification models and to evaluate how to improve the accuracy.

* We have applied **Random Forest** and **Neural Networks** together with **Data Oversampling Technique** in order to improve accuracy as the original database is highly umbalanced.


    - Version: 1.0
   -   [Share this repo](https://github.com/Jorgecardenas1/pulsar_classification_machine_learning)

## Content ##
```
root
│   README.md
│       
└───Pulsar Classification
   │   pulsar_data_test.csv
   |   pulsar_data_train.csv
   │   Pulsar_ML_V1.ipyb
   └───images
       │   Multiples images files
```

### Setup and run ###
1. Open EDGESSimulationV3.ipyb
2. The notebook is set in a way that it downloads and installs all dependencies required to run.

3. There is no need to set variables or parameters. 

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

* In images folder you can find the plots after running the notebook.


![Scheme](images/pairplot_umblanaced.png)