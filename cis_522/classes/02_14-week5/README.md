## Week 5 - ConvNets

### 02/14

History of ConvNets
* 1980: fukushima
* 1998:
    * LeNet (1998)
    * Developed by Yann LeCun (he worked in Hinton's lab as a postdoc)
    * successfully trained a 60k neural network without GPU
    * solved handwriting for banks
    * 0.8% error on MNIST
    * ANN were very uncool at this time; the field has changed a lot since then
* Deep learning is a **story of representation learning**
    * what are good representations? which properties should they have? how do we learn them?


Neural analogy:
* the idea of invariances (rotation, illumination, size, etc) is not *entirely* true (Konrad)

Convolution:
* desirable:
    * entangling" "similar" stimuli should produce similar representations
    * predictive
    * cheap to compute
    * have compositionality
    * causality
* CNN:
    * classification model, for images for instance
    * local filtering, we can compute the average of the filter
    * we can apply many filters
    * we can also apply a **ReLU** after applying the convolution
        * this helps to break up the linearity
    * the idea of max poooling is to achive some invance
    * Pooling layers:
        * we want to:
            * reduce dimensions of data (no additional parameters)
            * introduce some translation invariance
        * rule of thumb:
            * we want many small maxpools and convolutions
            * a maxpool goes along with a roughly equivalent increase in features
    * ConvNets have a much less amount of parameters

### 02/16

Order:
1. model = Model()
1. epochs = 5
1. optimizer = torch.optim....
1. criterion = torch.CELoss()
1. dataloader = ...

Train:
1. for _ in range(epochs):
        for batch in dataloader:
            optimizer.zero()
            out = model(batch)
            l = criterion(out)
            l.backward()
            optimizer.step()

Then validate (Hainiu does this, but there could be other ways)
on hold out dataset

the idea during training is to keep the current performance, and save the model when it outperforms the best model so far

