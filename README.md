# BMEN4460 Notebook 2
## Image classification on MNIST data.
Nanyan "Rosalie" Zhu and Chen "Raphael" Liu

This repository is a child repository of [**RnR-2018/Deep-learning-with-PyTorch-and-GCP**](https://github.com/RnR-2018/Deep-learning-with-PyTorch-and-GCP). This serves a primary purpose of facilitating the course BMEN4460 instructed by Dr. Andrew Laine and Dr. Jia Guo at Columbia University. However, it can also be used as a general beginner-level tutorial to implementing deep learning algorithms with PyTorch on Google Cloud Platform.

This repository, [**Image Classification on MNIST Data**](https://github.com/RnR-2018/BMEN4460-NB2-image_classification_on_MNIST_data
), presents an application of simple convolutional neural networks (CNNs) on image classification. For students in BMEN4460 (or who follow the instructions Step00 through Step02 in the parent repository), please create a Projects folder (if you have not done yet) within your GCP VM and download this repository into that folder.

On the GCP VM Terminal:
```
cd /home/[username]/
mkdir Projects # This is only necessary if you have not done this yet
cd Projects
git clone https://github.com/RnR-2018/BMEN4460-NB2-image_classification_on_MNIST_data/
```

You shall then see the following hierarchy of files and folders, hopefully, which matches the hierarchy of the current repository.

```
BMEN4460-NB2-image_classification_on_MNIST_data
    ├── BMEN4460-NB2-image_classification_on_MNIST_data.ipynb
    └── data
        └── MNIST_CNN.PNG
```

This notebook is largely inspired by and adapted from [this GitHub repository](https://github.com/jkotra/mnist-pytorch). The network architecture used in the tutorial comes from [this GitHub repository](https://github.com/floydhub/mnist).

### The CNN model implemented in this tutorial (again, the idea comes from [here](https://github.com/floydhub/mnist)).
<img src="/data/MNIST_CNN.PNG" width="1000px">
