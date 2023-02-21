## Week 6 - Deep Learning Thinking

### 02/21

* we were talking about homework 3:
  * cosine method that goes up, then it goes down in an angle, goes up again, etc

* Tutorial 1 in this week is almost the same as we did last week, so today we worked on tutorial 2
* So Tutorial 2:
  * the slides at the beginning are interesting
  * problem of predicting neuron spikes given 12 parameters of a motorcycle
  * we predict lambda, the parameter of the Poisson distribution
  * Hainiu said that this is a "Recognition network"
  * a cost function could be the Negative Log Likelihood (NLL)
  * so the network predicts the parameters of a distribution (such as Poisson's lambda or Gaussians's mean and std), and then we use the NLL to compute the loss given the data and predicted parameters

FID: cost function, Frechlet Inception Distance
* difference for images?

Cost function for different problems:
* Classification: Cross entropy, L2-norm, Hinge loss, Gini index (class impurity)
* Modeling distribution: Negative Log Likelihood
* Reconstruction: ELBO (Evidence lower bound), Dice loss, FID (Frechlet Inception Distance)
* Regression: MSE, MAE, Ridge, Lasso

We discussed projects
* Chain-of-thought: related to prompt engineering
