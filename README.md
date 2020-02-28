# BMEN4460 Notebook 2
## Image classification on MNIST data.
Nanyan "Rosalie" Zhu and Chen "Raphael" Liu

### Overview
This repository is a child repository of [**RnR-2018/Deep-learning-with-PyTorch-and-GCP**](https://github.com/RnR-2018/Deep-learning-with-PyTorch-and-GCP). This serves a primary purpose of facilitating the course BMEN4460 instructed by Dr. Andrew Laine and Dr. Jia Guo at Columbia University. However, it can also be used as a general beginner-level tutorial to implementing deep learning algorithms with PyTorch on Google Cloud Platform.

This repository, [**Image Classification on MNIST Data**](https://github.com/RnR-2018/BMEN4460-NB2-image_classification_on_MNIST_data), presents an application of simple convolutional neural networks (CNNs) on image classification.

For students in BMEN4460 (or who follow the instructions Step00 through Step02 in the parent repository), please create a Projects folder (if you have not done yet) within your GCP VM and download this repository into that folder.

The notebook [BMEN4460-NB2-image_classification_on_MNIST_data.ipynb](https://github.com/RnR-2018/BMEN4460-NB2-image_classification_on_MNIST_data/blob/master/BMEN4460-NB2-image_classification_on_MNIST_data.ipynb) walks you through the process of building a convolutional neural network (CNN) to classify the handwritten digits.

The notebook with visualization [BMEN4460-NB2-image_classification_on_MNIST_data_with_visualization.ipynb
](https://github.com/RnR-2018/BMEN4460-NB2-image_classification_on_MNIST_data/blob/master/BMEN4460-NB2-image_classification_on_MNIST_data_with_visualization.ipynb) intends to visualize how the convolutional kernels/filters evolve over the training process. In our specific case, it seems that these kernels in the first convolutional layer changed minimally throughout the process. Well, don't feel disappointed yet, as there are a lot more you can explore beyond this point. First of all, it is possible that the kernels in deeper layers evolve more drastically over the epochs, which you can check whether it is true or not yourself. Besides, even if this is not the case, at least you get to know this visualization method which you might find useful some day in your own deep learning research.

On the GCP VM Terminal:
```
cd /home/[username]/
mkdir BMEN4460 # This is only necessary if you have not done this yet
mkdir BMEN4460/MNIST # This is only necessary if you have not done this yet
cd BMEN4460/MNIST
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
    ├── BMEN4460-NB2-image_classification_on_MNIST_data_with_visualization.ipynb
    └── data
        └── MNIST_CNN.png
```

## DEBUG

<details>
<summary><strong>Known Issue 1. Jupyter Lab: "No module named ..."</strong></summary>
<br>

If you followed the instructions given in the parent repository and used the Deep Learning VM quick creation routine, you might encounter an error when you try to run the commands in the jupyter notebook. It will probably say that you have not installed tensorflow (which we will use to download the MNIST dataset in this tutorial). What you will need to do is typing the following instructions in a new GCP VM SSH Terminal (you can keep the one that runs jupyter notebook as it is while opening a new SSH Terminal).

#### Step 1. Grant yourself the write permission over the anaconda directory (only necessary if you have not done this before).
```
sudo su [username]
cd /opt/anaconda3/env/ # If you installed anaconda in another directory the permission problem is not likely an issue for you.
ls -ll # You should see that you don't have the write permission.
sudo chmod 777 -R ./* # Grants read, write, execute permission to all users.
ls -ll # Now you should have all three permissions.
```

#### Step 2. Install some additional packages with anaconda (you should know how to do that by now).
```
conda activate BMEN4460
conda install -c anaconda tensorflow pandas seaborn
```

#### Step 3. Refresh the jupyter kernel (we don't think it is necessary but it worth trying if you still cannot use the newly-installed packages in your jupyter lab).
```
python -m ipykernel install --user --name BMEN4460 --display-name "Python3.7 BMEN4460"
```

#### Step 4. Make sure that you selected the correct jupyter kernel when you are using the jupyter lab.

</details>

<details>
<summary><strong>Known Issue 2. Jupyter Lab: "Do not have permission to save model parameters" (something like that).</strong></summary>
<br>

You know how to do this, right? In a new SSH Terminal (as long as not the one that keeps your jupyter lab running), type:
```
cd /home/[username]/Projects
sudo chmod 777 -R ./*
```

Run the jupyter lab block that gives you the error again and it should be fine now.

</details>

## Acknowledgements
This notebook is largely inspired by and adapted from [this GitHub repository](https://github.com/jkotra/mnist-pytorch). The network architecture used in the tutorial comes from [this GitHub repository](https://github.com/floydhub/mnist). Please note that the layer dimensions are (highly likely) incorrect in the network architecture illustration given by the cited GitHub repository.

### The CNN model implemented in this tutorial (again, the idea comes from [here](https://github.com/floydhub/mnist)).
<img src="/data/MNIST_CNN.png" width="1000px">
