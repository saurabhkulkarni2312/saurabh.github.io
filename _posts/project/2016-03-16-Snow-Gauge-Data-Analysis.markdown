---
layout: project
title:  "Recommendations for Calibration Snow Gauges"
date:   2016-03-16 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: snow.jpg
thumb: 
tagged: R Programming, Data Visualization, Regression, Kaggle
client: 
website: https://github.com/saurabhkulkarni2312/R-Projects/tree/master/Calibrating-Snow-Gauges-Regression
---
#### Objective
Recommendations for Calibration Snow Gauges

#### Project Details
**Aim** was to find a relationship between the density with respect to gain and evaluate the performance of linear regression.

**Data**: This data is provided by the USDA during one of their calibration sessions in the Sierra Nevada. For our gauge model, different blocks of polyethylene with known densities are placed between the emitting rod and the receiver rod for the gauge. As gamma rays pass through the polyethylene blocks, the gamma ray may be absorbed, bounce away from the receiver rod, or pass through the block to the receiver rod. For each block, 30 measurements are taken, and the middle 10 are reported in the dataset; the measurement from the gauge is called *gain* There were 9 blocks in total.

Here, I have tried to observe how well simple models like linear and log-linear regression model can be used to model the data. Various visualizations have been performed to illustrate the performance.
 Our aim was not to fit best model but to evaluate the performance of linear regression model (with and without log transformation) and see what all tests we can perform to visualize the performance. For detailed analysis report do checkout the R notebook on my Github page