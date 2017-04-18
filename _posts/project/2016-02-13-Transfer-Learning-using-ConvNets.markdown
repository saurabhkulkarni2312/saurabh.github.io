---
layout: project
title:  "Transfer Learning using ConvNets"
date: 2014-04-25 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: convnet.jpg
<!--carousel:
- single01.jpg-->
tagged: Python, Keras, Tensorflow, Convolutional Neural Nets
---
#### Objective
Transfer Learning using ConvNets

#### Project Details
**Aim** Transfer Learning with VGG16 on Caltech 256 and Urban Tribes Datasets

**Data**: Contains Image Dataset: Caltech 256 and Urban Tribes

**Abstract**:
Here we used transfer learning for Image Classification. 

We have a pre-trained CNN model (VGG16). We are uing the same CNN model but retraining the softmax layer and evaluating its performance on different datasets. 

We also evaluate the classification accuracy vs epochs and visualize the filters in first and last CNN layers. We got a highest train accuracy of 97.75% and test accuracy of 54.88% in the Caltech 256 dataset and a highest train accuracy of 90.91% and a test accuracy of 38.64% in the Urban Tribe Dataset.