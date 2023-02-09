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


### 02/09


