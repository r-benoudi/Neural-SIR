# Neural SIR parameter estimation
Pytorch code for a parameter estimation Neural Network applied to the SIR mathematical model of epidemiology.
## Mathematics
Consider the SIR model
$$\frac{dS}{dt} = -\beta \frac{SI}{N}$$
$$\frac{dI}{dt} = +\beta \frac{SI}{N}-\gamma I$$
$$\frac{dR}{dt} = \gamma I$$
This code will take a time series of datapoints of susceptible (S) and Infected (I) and determine the parameter $\beta$ that generates the corresponding disease model, with a fixed $\gamma$.

In other words, this neural network determines the infectivity of a disease from the infected data (Grimm et al, [2021](https://epub.oeaw.ac.at/0xc1aa5576_0x003cfd4a.pdf)).

## References
Grimm, V. et al. (2021) ‘Estimating the time-dependent contact rate of SIR and SEIR models in mathematical epidemiology using physics-informed neural networks’, ETNA - Electronic Transactions on Numerical Analysis, 56, pp. 1–27. Available at: https://doi.org/10.1553/etna_vol56s1.



