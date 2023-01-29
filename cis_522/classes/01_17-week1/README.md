## Week 1

### 01/17

* We worked on the notebook in this folder, got from [here](https://github.com/CIS-522/course-content/tree/main/W01_Introduction).
* There are assignments each week. For that, I had to follow the instructions in [this repository](https://github.com/CIS-522/homework).
  * My private fork is [here](https://github.com/miltondp/homework).
  * I forked this into the k99_courses
  * And added the upstream repo
  

### 01/19

* For homework:
  * gradiant descend:
    * compute gradient first: delta L / delta w
    * compute w' = w - n * (delta L / delta w), where n is learning rate
    * use np.clip in case the gradient keeps changing. Something like: np.clip(gradient, -1, 1)
    * suggested to use package: wandb (weights and bias), although it is too much for linear regression
  * closed form:
    * use numpy.linalg.pinv for the close formed solution
