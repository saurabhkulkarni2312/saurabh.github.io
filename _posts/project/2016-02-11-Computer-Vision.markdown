---
layout: project
title:  "Machine Vision"
date: 2014-04-23 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: cv2new.png
<!--carousel:
- single01.jpg-->
tagged: MATLAB, Computer Vision
---

Here are some of the computer vision problems I worked on through various projects/ class assignments.
Tool used: MATLAB

#### Canny Edge Detection
Canny Edge Detector was used to detect sharp edges in an image. 
The five steps involved in this detection are: Smoothing, Gradient Computation, Non
Maximum Suppression, and Hysteresis Thresholding. Smoothing is done by applying a 5x5 Gaussian
kernel. Sobel Operators were used to compute gradient. NMS was used to keep sharp edges and remove soft ones.

#### Lane Detection using Hough Lines
This problem deals with using the Hough Transformation to identify lines in an image.

#### Optical Flow Detection using Iterative Coarse to Fine Lucas Kanade Algorithm
In this project a single-scale Lucas-Kanade optical flow algorithm and iterative Coarse to fine optical flow 
method were implemented. The window sizes and tau values (threshold of eigenvalues) were varied to observe response.

#### Background Segmentation and Motion Detection
This problem dealt with removing dynamic portions of a scene given a sequence of images. 
The end result was expected to be a static background image, removing all dynamic components (cars moving, people walking etc).

#### Face Recognition
For a Yale face database (5760 images of 10 faces) three techniques were explored for face detection: Naive k Nearest Neighbor and Eigenfaces and fischerfaces. 
Idea is to represent the input data is by finding a subspace which represents most of the data variance. 
This can be obtained with the use of Principal Components Analysis (PCA). 
When applied to face images, PCA yields a set of eigenfaces. 
These eigenfaces are the eigenvectors associated to the largest eigenvalues of the covariance matrix of the training data.
Fischerfaces are basis obtained from LDA. Error rates were observed varying the number of eigenfaces/fischer faces used in reconstruction