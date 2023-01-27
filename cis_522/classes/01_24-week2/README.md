## Week 2 - Deep Linear Networks

### 01/24

* today we cover gradient descent and basics of it
* pytorch and autograds
* computational graph (video of Kordan)
  * see again the video (Section 2) "Gradients in Pytorch (Autograd)"

* linear regression:
  * forward (computational graph):
    x -> f=Xw -> (g = y - f) -> L=g^2
  * backward:
    dL / dg = 2g
    dg / df = -1
    df / dw = X

    dL / dw = (chain rule, components canceled) = -2 Xg = -2X^t (Y-Xw)

    and we want this to be zero, so:

    -2X^t (Y-Xw) = 0
    -2X^tY + 2X^tXw = 0
    2X^tXw = 2X^tY
    X^tXw = X^tY
    w = (X^tX)^-1 X^t Y


### 01/27 (makeup pod)

* TA: Ahmed Ahmed
* The part of "crazy" scaling seems to be very important in DL.
