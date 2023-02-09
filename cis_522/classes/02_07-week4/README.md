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

### 02/09

* Chernoff bound
  * if you have larger batch sizes, errors are better? it's a mathematical derivation
* Distillation is pretty good (Hainiu)
* adversarial attacks
  * each batch could shift a bit the loss landscape
  * so the idea is that a small shift in input, our network can be fooled
  * here the final loss funcion is, for example, cross entropy(perturbed output, predicted output) + || dL/dX ||2