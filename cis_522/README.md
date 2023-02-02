# CIS-522


## PyTorch

### Installation
* Install PyTorch: https://pytorch.org/get-started/locally/
  ```bash
  conda create -n cis522
  conda activate cis522

  # with cuda:
  conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
  # CPU only:
  # conda install pytorch torchvision torchaudio cpuonly -c pytorch

  conda install ipywidgets ipython numpy matplotlib jupyterlab -c pytorch
  ```

Run JupyterLab:
```bash
jupyter lab --ip="127.0.0.1" --port="8888" --ContentsManager.allow_hidden=True --no-browser --ServerApp.token=""
```


### Quickstart
* Quickstart: https://pytorch.org/tutorials/beginner/basics/quickstart_tutorial.html
  * I ran all the code until "Creating Models" section, where I verified that it is using CUDA as a device.
  * I also trained a model and it worked, with 64% accuracy.
  * I made some predictions also.
  * TODO: I did all the previous very quickly just to verify everything works. I need to go back and understand the code now.

### Introduction to PyTorch
* Continue with the "Introduction to PyTorch":
  * Tensors
  * Dataset and Dataloader
  * Transforms
  * Build the Neural Network
  * Automatic Differentiation with torch.autograd
  * Optimizing Model Parameters
  * Save and Load the Model

Then there is another series below that is called "Introduction to PyTorch on YouTube" that seems a little bit different.
