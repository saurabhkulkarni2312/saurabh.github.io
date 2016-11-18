---
layout: project
title:  "Recommendations for Calibration Snow Gauges"
date:   2016-03-16 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: snow-gauge.jpg
thumb: bnpthumb.jpg
carousel:
- single01.jpg
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

**Post Analysis**
Here our objective was to identify a relationship between the density and gain of the snow gauge. In our analysis we identified that there is a linear relationship between log(Gain) and the density of the snow. Here the explanatory variable was gain and the response variable is density. (Although, during training, we measured gain for a corresponding density, the nature of the variables during applications get inverted).
We first found the mean value of gain for each density. Then we first tested linear regression model on density v/s gain. The nonlinear relationship between gain and density led to incorrect fitting and high error. Hence we applied linear regression to the density vs log(Gain) plots. We then performed regression analysis on this fit to see if it satisfies all the conditions.
We observed that for the density v/s log(Gain) plots had R^2 coefficient ~ 1. Then, We also found F-test p-value to be close to 0. Both these values imply the linear model was a good fit for the plot. We further analyze the effect on all residuals. For this analysis we do not equate the means. We take all 90 points into consideration. The residual distribution was plotted. The QQ plots and the kurtosis show that the distribution is close to normal but not normal. Hence we verify that the plots are nearly normal. We also found the mean and variance of the residuals and by visual inspection we see that the residuals are homoscedastic in nature surrounded around ~0 mean. Box Plot also illustrates this feature. We found the root mean square error and the absolute error of the fit.

Our aim was not to fit best model but to evaluate the performance of linear regression model (with and without log transformation) and see what all tests we can perform to visualize the performance