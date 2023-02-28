## Week 7 - Modern ConvNets

### 02/28

We went through the first notebook

In "Import Alex" we needed to replace the image because it was not working.

In section 4, there is another error in the code that gest fixed by doing `next(iter(dataiter))`

ResNets by Hainiu:
* people was naively stacking CNNs, but it didn't work well
* thats where ResNets introduced a new concept where connections are skipped
* the input is repeated in the output of layers to learn the residuals:
    * (from Hainiu) CrossEntropy(y_hat, y), where y_hat = X + fw(X) (this last term is sort of the residuals)


Transfer learning:
* fine tunning
* training the classification layer (last one)
* training from scratch
