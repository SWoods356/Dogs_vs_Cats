# Dogs_vs_Cats
Dogs_vs_Cats image classification


# Overview
This repository features EDA and classification on the [Dogs vs. Cats Redux: Kernels Edition](https://www.kaggle.com/c/dogs-vs-cats-redux-kernels-edition) kaggle picture library.

This library contains 25,000 train and 12,500 test images of either dogs or cats. The objective is to determine the pobability that a given picture is of a dog.

# EDA and Preparation for Modeling

With .JPG files as my data, files were organized in subdirectories for training, validation, and testing, with separate folders for dogs and cats. 1,000 images were randomly selected from the train directory for training, 200 images for validation, and 100 images for testing.

# Modeling - Convolutional Neural Nets

An initial CNN was fit with two hidden layers, 420,000 parameters, and relu activation. This model was compiled with the adam optimizer. Training accuracy reached 100% by 10 epochs while validation accuracy reached 65%

A second model was created directly from the vgg16 pretrained keras model. This model features 138,000,000 parameters. Only the final activation layer of the model was modified to use softmax activation to work with only two classes: dog and cat. Because this model has already been trained on dog and cat images, only the final activation layer has to be trained on my image data. This model produced 99.2% training accuracy and 97.5% validation accuracy. This model achieved a kaggle log loss score of .08366 on the test image set.

Predicted image labels were matched with test image id numbers from the filenames for kaggle submission. Submitting predicted probability performed significantly better than binary prediction.
