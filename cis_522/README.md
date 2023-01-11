# CIS-522

* Install PyTorch: https://pytorch.org/get-started/locally/
  ```bash
  conda create -n cis522
  conda activate cis522
  conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
  conda install ipython -c nvidia
  ```

* Quickstart: https://pytorch.org/tutorials/beginner/basics/quickstart_tutorial.html
  * I ran all the code until "Creating Models" section, where I verified that it is using CUDA as a device.
  * I also trained a model and it worked, with 64% accuracy.
  * I made some predictions also.
  * TODO: I did all the previous very quickly just to verify everything works. I need to go back and understand the code now.

* Continue with the "Introduction to PyTorch":
  * Tensors
  * Dataset and Dataloader
  * Transforms
  * Build the Neural Network
  * Automatic Differentiation with torch.autograd
  * Optimizing Model Parameters
  * Save and Load the Model

Then there is another series below that is called "Introduction to PyTorch on YouTube" that seems a little bit different.
