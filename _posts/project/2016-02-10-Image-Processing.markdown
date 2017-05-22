---
layout: project
title:  "Image Processing"
date: 2014-04-22 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: cv1new.png
<!--carousel:
- single01.jpg-->
tagged: MATLAB, Image Processing
---

Here are some of the image processing problems I worked on through various projects/ class assignments.
Tool used: MATLAB.

- **Image Transformations and Albedo Detection for given lightsources**
Rendered the image of a face with two different point light sources using a
Lambertian reflectance model. Two albedo maps were used.

- **Corner Detection and Triangulation using Epipolar based Geometry**
Built a corner detector which takes as the input image, the number of corners, the standard
deviation of the smoothing kernel, the size of the smoothing window, and returns the required number
of strongest corners after non-maximum suppression. 
Different values of the standard deviation of the smoothing kernel and
the size of the smoothing window were explored for best results

- **Object Detection using Convolution Filtering**: 
When a filter kernal is convolved with an image, the output intensity image will represent a heat map. 
The largest values in the intensity image will correspond to locations where the filter matches the original image.
Hence we can identify region where an object may be located.