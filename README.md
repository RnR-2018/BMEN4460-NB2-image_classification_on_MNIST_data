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

If it says "fatal: could not create work tree dir ...", you may as well try it again with super user permission
```
sudo git clone https://github.com/RnR-2018/BMEN4460-NB2-image_classification_on_MNIST_data/
```

You shall then see the following hierarchy of files and folders, hopefully, which matches the hierarchy of the current repository.

```
BMEN4460-NB2-image_classification_on_MNIST_data
    ├── BMEN4460-NB2-image_classification_on_MNIST_data.ipynb
    └── data
        └── MNIST_CNN.PNG
```

## DEBUG
If you followed the instructions given in the parent repository and used the Deep Learning VM quick creation routine, you might encounter an error when you try to run the commands in the jupyter notebook. It will probably say that you have not installed tensorflow (which we will use to download the MNIST dataset in this tutorial). What you will need to do is typing the following instructions in a new GCP VM SSH Terminal (you can keep the one that runs jupyter notebook as it is while opening a new SSH Terminal).

#### Step 1. Grant yourself the write permission over the anaconda directory (only necessary if you have not done this before).
```
cd /opt/anaconda3/env/ # If you installed anaconda in another directory the permission problem is not likely an issue for you.
ls -ll # You should see that you don't have the write permission.
sudo chmod 777 -R ./* # Grants read, write, execute permission to all users.
ls -ll # Now you should have all three permissions.
```

#### Step 2. Install tensorflow with anaconda (you should know how to do that by now).
```
conda install -c anaconda tensorflow
```

### Acknowledgements
This notebook is largely inspired by and adapted from [this GitHub repository](https://github.com/jkotra/mnist-pytorch). The network architecture used in the tutorial comes from [this GitHub repository](https://github.com/floydhub/mnist).

### The CNN model implemented in this tutorial (again, the idea comes from [here](https://github.com/floydhub/mnist)).
<img src="/data/MNIST_CNN.PNG" width="1000px">
