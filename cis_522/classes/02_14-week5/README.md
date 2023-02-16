## Week 5 - ConvNets

### 02/14

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

