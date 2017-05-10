---
layout: project
title:  "Rare-Class Claims Classification System"
date: 2016-04-01 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: bnp.jpg
thumb: bnpthumb.jpg
<!--carousel:
- single01.jpg-->
tagged: Data visualization, imbalanced data, log-loss, random forest, xgboost
client: 
website: https://github.com/saurabhkulkarni2312/R-Projects/tree/master/BNP-Paribas-Claims-Management
---
#### Objective
Predictive Modelling for Insurance Claim Approvals

#### Project Report and Code
[//]: # ([Project Report](../assets/writeups/Insurance-Claims-Classification-Report.pdf))

[Github Repo](https://github.com/saurabhkulkarni2312/R-Projects/tree/master/BNP-Paribas-Claims-Management)

#### Project Details
**Aim** was implement a R based robust rare class classification model to accelerate claims management processes of BNP Paribas Cardif. The parameter to be evaluated was class probabilities i.e. probability the datapoint belongs to class 0 or 1. 

**Data**: The data contained 131 features. Some features were dominant during classification while some are not. We are not given any additional information so as to which features are crucial. The training dataset was imbalanced. Approximately 77% of the datapoints belonged to class 1.

The pipeline was as follows: 
- first clean the dataset, perform missing data imputation and to encode categorical variables using one-hot encoding. 
- Perform visualization of data to identify significant feature variables post data-imputation.
    - Feature distributio  were observed to find noticable skew differences in between different classes
    - Interdependence of variables was observed to reduce features having high correlation coefficients
    - Correspondence matrices were used to identify interdependence between categorical variables
- Post exploratory analysis different techniques were used to model the data
- The performance of tree-based techniques like random forest and other ensembling techniques like boosting (xgboost algorithm) was evaluated with respect to the base case of logistic regression. 
- Inbuilt cross validation R modules were used to fine tune model parameters
- Class probabilities were calculated of the test set and log-loss error metric was used to compare results.