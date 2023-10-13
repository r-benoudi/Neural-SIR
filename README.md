# Neural SIR parameter estimation
Pytorch code for a parameter estimation Neural Network applied to the SIR mathematical model of epidemiology.
## Mathematics
Consider the SIR model
$$\frac{dS}{dt} = -\beta \frac{SI}{N}$$
$$\frac{dI}{dt} = +\beta \frac{SI}{N}-\gamma I$$
$$\frac{dR}{dt} = \gamma I$$
This code will take a time series of datapoints of susceptible (S) and Infected (I) and determine the parameter $\beta$ that generates the corresponding disease model, with a fixed $\gamma$.

In other words, this neural network determines the infectivity of a disease from the infected data (Grimm et al, [2021](https://epub.oeaw.ac.at/0xc1aa5576_0x003cfd4a.pdf)).

## The code
The default data, from which the Neural Network (NN) determines the parameter, is the solution of the SIR equations. The neural network does not have any information of the real value of the infectivity parameter $\beta$ and at the preactivation it is randomly guessed. During the training $\beta$ is used as a hyperparameter that changes together with the biases and weights. The tests on SIR solutions determine that the parameter estimation is robust enough, with an average error of $10^{-2}$ in the value of $\beta$.

The data is transformed using a log function followed by a min-max transformation such that the input data of the NN is comprised between 0 and 1.
The code uses a neural network with a SELU activation function and its architecture is composed by 10 layers of 128 neurons each and the loss functions are the MSE of the time series and the residuals from the SIR differential equations. A weighting/scaling procedure is in place to ensure the proper evolution of the NN (Grimm et al, [2021](https://epub.oeaw.ac.at/0xc1aa5576_0x003cfd4a.pdf)).

## References
Grimm, V. et al. (2021) ‘Estimating the time-dependent contact rate of SIR and SEIR models in mathematical epidemiology using physics-informed neural networks’, ETNA - Electronic Transactions on Numerical Analysis, 56, pp. 1–27. Available at: https://doi.org/10.1553/etna_vol56s1.



