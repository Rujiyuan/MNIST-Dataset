# MNIST Dataset

## Overview

The MNIST dataset is a collection of 70,000 handwritten digits, commonly used for training and testing machine learning models in the field of image recognition. It consists of two parts:

- **Training Set**: 60,000 images with corresponding labels.
- **Test Set**: 10,000 images with corresponding labels.

This repository contains the MNIST dataset in `.gz` format for both training and testing purposes. The dataset includes the pixel data and the labels for each image, enabling easy integration into machine learning tasks.

## Dataset Structure

The dataset is organized into the following files:

- **train-images-idx3-ubyte.gz**: Contains the pixel data for the training set images.
- **train-labels-idx1-ubyte.gz**: Contains the corresponding labels for the training set.
- **t10k-images-idx3-ubyte.gz**: Contains the pixel data for the test set images.
- **t10k-labels-idx1-ubyte.gz**: Contains the corresponding labels for the test set.

## Downloading the Dataset

The dataset is downloaded using the Python `MNIST` class from the `torchvision` library, as shown in the following code:

```python
from torchvision import datasets

# Set the mode to True for training data, False for test data
mode = True  # Change to False for test data

# Download the MNIST dataset
dataset = datasets.MNIST(root='../data', download=True, train=mode)

# Load the images and labels
data = getattr(dataset, 'train_data' if mode else 'test_data')
labels = getattr(dataset, 'train_labels' if mode else 'test_labels')
```
