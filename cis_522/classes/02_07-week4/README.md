## Week 4 - Regularization & Optimization

### 02/07

I couldn't attend this class.
But I was exploring the notebooks.

From W4D1:
* what to optimize
* and how to optimize it
* the first piece is the loss function
  * Technical:
    * L2 vs maxEntropy -- for multi class problem
    * Accuracy vs AUC -- for class imbalance
      * Accuracy could be really bad if there is class imbalances
  * Societal questions:
    * Fairness: optimal for whom? the buyer, the seller, the last people in, the first...?
    * Unintended consequences
      * surrogate loss function, they could lead to bad consequences
      * Cobras in India
        * farmers of cobras
      * Game play
        * a game that optimize the points, but never ended the game.
  * training NNets could be very expensive to train, so speed matters
  * this week:
    * why NNet optimization is hard
    * gradient descdend and it's many tricks:
      * batch size selection
      * batch normalizaion
      * momentum
      * adaptive learning schedules
      * natural gradients
    * unintended consequences of optimization
      * amplification and class error disparities

  * Why is training a deep neural net hard?
    * because NNets are really expressive, universal approximatoion (but no guarantees on fiding int)
  * seriously non-convex
    * but we don't want to find the optimum anyways
  * but the gradient does lot necessarily leads to the minimum, but a local one
    * this could be a huge problem, zig zaging, in high dimensional problems
  * what we need in a gradient descent algorithm?
    * it should be fast, few iterations as possible
    * should converge to a good optimum

  * Minibatching
    * a minibatch is a small subset of a large dataset
    * best measure is the average gradient over all of the examples
    * basically all deep learning is minibatching, making it an online algorithm
    * minibatch size selection:
      * too small batch (e.g., SGD) bounces around a lot, and slower
      * too big batch won't fit on the GPU
  
  * SGD uses single instances, but minibatch uses groups of them
  * SGD advantages:
    * The noise in the SGD update can prevent convergence to a bad (shallow) local minima.
    * It is drastically cheaper to compute (as you don’t go over all data points).

  * batch normalization
  * importance of normalize/standaridze with z-score each feature/input of the nural net
    * by adding normalization layers in between existing layers
    * this makes good initialization less important
    * the most common practice is to put the normalization in between the linear layers and activation functions

Regularization:
* key for deep learning
* modern neural nets, with as many weights as data points, "should" overfit, but they don't
  * deep learning often usese more parameters than observations
* lowest test errors come from giant networks with lots of regularization
  * best is combine different regularizations
  * bias/variance trade off
    * bias is training error
    * variance is test error (roughly)
* generalization and overfitting
* GPT-3 (175B params trained on 500 billion words)
  * it does not overfilt, but it memorizes

* regularization is shrinkage, shrinkage is regularization
* the smaller the weights in the model, the more you generalize
* smaller weights underperform on the train, but can do very well on the teset set

early stopping:
  * this is one of the easiest ways to regularize
  * initialize with small weights
  * these weights get bigger and bigger as we do gradient descent
  * so stop when they are the "optimal" size, that is, when validation accuracies do not increase over epochs
  * but **it doesn't solve the problem of local variance** (i.e., accuracy can be very volatile between epochs)
    * to overcome this, we also save the best model based on the val loss/accuracy for use on test data

* dropout is another regularization techniques
  * it sort of samples different networks
  * and does a sort of ensembling of them
  * adds lots of noise, but prevents overfitting
  * enforces distributed representation

### 02/09

* Chernoff bound
  * if you have larger batch sizes, errors are better? it's a mathematical derivation
* Distillation is pretty good (Hainiu)
* adversarial attacks
  * each batch could shift a bit the loss landscape
  * so the idea is that a small shift in input, our network can be fooled
  * here the final loss funcion is, for example, cross entropy(perturbed output, predicted output) + || dL/dX ||2

From W4D3:

* Hyperparameter tuning is basically search
  * so grid search for small parameters, taking smallest and largest values and their combinations
* randomized search, just different random combinations
* coordinate-wise gradient descent
  * gradient descent in hyperparameters
  * change them one at a time, accepting any changes that reduce testing error
* Bayesian optimization / AutoML
  * start with hyperparameters that worked well for similar problems

regularization via SGD (builtin into SGD):
* SGD does regularization
* weights get bigger as one iterates
* if we use early stopping it will avoid overfitting

* small batch size <-> large learning rate
* so increasing batch size is like decreasing the learning rate

regularization by compressing; this can be done by:
* distillation: dimensionality reduction
* pruning: removing nodes
* generally, start big, then compress, works better than starting small

Distillation:
* train a network: the teacher
* apply the teacher to a big set of unlabeled data
  * generates "soft labels" or estimated lables
  * can include hidden node outputs (this are the internal features of the network)
* then we use this to train a "student" network


Adversarial attacks and defenses
* for example, a network classifies an image as a cat, but with subtle changes, then the network thinkgs it's "guacamole"
* the problem is that we are in a high dimensional space, where every point is close to all other points
* can one defend against them? yes
  * regularization "defensive distillation" (here soft labels help) or "feature squeezing"
  * or pick weights to minimize the objective function that the adversary is trying to maximize (when searching for perturbations)
  * so no small pertubation would fool the network
  * it's making the weights more robust


### Optional notebook "Homework tips"

* Learning rate matters
* learning too fast (oscilates) vs learning to slowly (takes forever)
* anneal/decay: start fast, then slow down
* so we adjust the weights for each batch, the idea here is to adjust the learning rate
  * we can use 1/t, or sqrt(t), etc, but with all of them **we are already fixing** how we will adjust them
* gradients can become enormous: they could be clip (gradient clipping).
* for Adagrad, we update *each* weight (w_i) at each time step (or epoch), although the text also says that in practice time step is a minibatch.
* RMSprop:
  * same idea as Adagrad, but running average instead of sum (in the denominator, or v_{t+1})
  * it tries to fix the adagrad's aggressive, monotonically decreasing learning rate
* Adam:
  * similar to RMSprop, but with momentum added

* natural gradients:
  * "destructive interference": Neural nets, when trained on new data, tend to forget what they have already learned
  * natural gradients try to address this
  * the idea is to move in a gradient directoion that keeps prior learning intact
  * instead of changing the parameter vector to at most move an epsilon distance, we constrain the output distribution of the model to be within an epsilon distance from the distribution on the previous step.
  * We measure the distance between two distributions with Kullback-Leibler Divergence (KL) 
  * it uses the fisher information matrix
  * the problem is that they take a lot of memory (the inverse matrix is huge with high dimensions)
  * adam approximates natural gradients

* bias in ML:
  * training data, how it is selected and labels are
  * loss function selected
* algorithmic fairness:
  * two groups: protected class and the general population
  * goals:
    * same prediction accuracy in the two groups
    * same false positive rate
    * same percentage labeled "true"
    * the protected calss label is not used in the prediction
    * in general, these criteria are incompatible (so we need to select something, not everything; there are always trade offs)
  * example of facebook ads targeting by race, age, sex, that was prohibited in 2019
