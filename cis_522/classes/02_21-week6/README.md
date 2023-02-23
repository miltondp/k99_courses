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


### 02/23

Today we'll discuss about projects (the presented a slide)
* The text is here: https://edstem.org/us/courses/33082/discussion/2649635
* there they link this [What is a good project?](https://docs.google.com/presentation/d/1rFfe0P6cZ509FMeflPbFvOvBiBodwxPWb-8hQr9kwPQ/edit?usp=sharing)
* I downloaded the slides they presented into this folder

What makes a good DL class project?
* it has to be managenable
* we don't have to use the entire dataset, I can sample it
  * they are mentioning this because you cannot work on Google Collab with this
* you will almost always start with a pre-trained models that others trained on big data
  * this is interesting, maybe, for the VAE on gene expression data
  * huggingface is a resource to download pre-trained models
* https://60years.vizh.ub.ai -> map/grahp of research in AI, interesting
* you need to have a good question:
  * it must be possible to answer it
* **Neural match**:
  * https://deeplearning.neuromatch.io:
    * most of the material here is overlapped with the course
    * so if there is a something that we don't know (like VAEs), we can take a look here
  * suggested by one TA
  * it's a coding camp
  * 