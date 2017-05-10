---
layout: project
title:  "Amazon Recommendation Systems"
date: 2017-03-01 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: amz2.PNG
<!--carousel:
- single01.jpg-->
tagged: Python, Recommendation System, Latent Factor Models, Collaborative Filtering, Alternating LS

---
### Objective
1.	To predict the rating a user may give to an item based on available review records.
2.	Based on the review text, predict whether a user’s review of an item will be considered helpful or not

### Project Details

#### Data:

The given data comprises of a database of actual amazon reviews (JSON File). The data had *200000* samples.

The training data  was clean and organized and it had the following features:

 - *category* – Category labels of the product being reviewed 
 - *helpful* – Helpfulness votes for the review. This has two subfields, *nHelpful* and *outOf*. The latter is the total number of votes this review received, 
 the former is the number of those that considered the review to be helpful.
 - *reviewText* - The text of the review. It should be possible to successfully complete this assignment
without making use of the review data, though an effective solution to the helpfulness prediction
task will presumably make use of it.
 - *summary* - Summary of the review
 - *price* - Price of the item
 - *reviewHash* Hash of the review (essentially a unique identifier for the review)
 - *unixReviewTime* Time of the review in seconds since 1970

#### Data Cleaning:
The data was clean so data wrangling component was minimal - only thing to do to parse the JSON file to a flat dataframe. Also in order to predict helpfulness accurately, I decided to predict
helpfulness ration (nhelpful/outOf) as a continuous variable instead of just nHelpful. We then find nHelpful using this ratio and round it
#### Feature Selection:
The next key step was feature selection. One key step is to select relevant features which would be useful the prediction but simple
enough not to overfit the data. Also certain features should be prioritized depending how drastically they aect the response variable. For example: In predicting the Helpful reviews,
we try to fit the helpfulness ratio using outOf, the rating, the characteristics of the review (namely length of review/ sentences in review etc.) or the review summary. We also observe
that for a higher value of outOf, typically nHelpful is almost same as outOf. Similarly in ratings prediction the key features are user and item ID.
#### Evaluation Metric
1. For Ratings prediction [RMSE](https://www.kaggle.com/wiki/RootMeanSquaredError) was used.
2. For helpfulness prediction [MAE](https://www.kaggle.com/wiki/MeanAbsoluteError) was used.

#### Part 1: Ratings prediction
**Baselines**: Here we say Ratings is equal to the global average of all ratings. Clearly this is a very simple but poor predictor.

**Beta model**: We say *Ratings ~ &alpha; +  &beta;<sub>i</sub>$ + &beta;<sub>u</sub>$*. 
Here \alpha is global average rating, \beta<sub>u</sub> accounts for variability in rating from user to user and \beta<sub>i</sub> accounts for variability in rating from item to item

This takes into account the characteristics of the user and item which aects the rating.
We minimize the objective function and terminate the iterations only when the objective
function changes only by a small amount of 10<sup>-7 </sup> in consequent iterations for convergence. 
We use regularization parameter lambda to avoid overfitting. lambda is chosen as the one which
minimizes the MSE on the validation set.

**Latent Factor Model**: 
The above model is a linear model. there is a nonlinear relationship that exist in
the users and the way they rate certain items. The alpha or beta components do not account for variability in how a particular user will rate a particular item.
We take an additional pair of parameters \gamma_u and \gammai and multiply them and add it to our ratings predictor model. These gamma's will be two dimensional matrices with sizes [U,k] and [k,I].

*Ratings ~ &alpha; + &beta;<sub>i</sub>$ + &beta;<sub>u</sub> + &gamma;<sub>u</sub>&gamma;<sub>u</sub>$*

The product term incorporates how user "u" would rate an item "i". This non-
linear term is able to capture the richness in variability of the objective function and hence
we have a better predictor to model the ratings. So we need to estimate 5 parameters during training and use two hyperparameters \lambda and k during validation to tune the model

Here I tested two ways for convergence:
 - a non optimal [Vanilla Gradiant Descent](https://en.wikipedia.org/wiki/Gradient_descent) 
 - more efficient [Alternating Least Squares](https://www.quora.com/What-is-the-Alternating-Least-Squares-method-in-recommendation-systems)

While GD took ages to converge, ALS converged more efficiently. Latent factor with Alt. Least Squares was best predictor and a robust technique of ratings prediction.

#### Part 2: Helpfulness prediction
**Baselines Model**: Predict Helpfulness Ratio as the same as the average ratio or mean Helpfulness ratio as prediction and then find nHelpful by multiplying the ratio with
outOf. But this is a poor model in terms of performance.

**Naive Regression**: Chose a vector {1; outOf; len(reviewText)} and model *f(vector) ~ helpfulness ratio*. 

**Random Forest Regressor**: 
I created a feature vector {outOf, len(reviewText), Sentence Count, Rating, word count} for all training samples. Particular empasis was given on outOf by providing a cuto (outOf >
70) classify ratio as 1 (if outOf is high then nHelpful is almost equal to outOf)

It is estimator that fits a number of weak classifying decision trees on various sub-samples of the dataset and use averaging to improve the
predictive accuracy and control overfitting. The RF hyperparameters: maxdepth, nEstimators were tuned for optimal results using cross validation set.

**Gradient Boosted Regression**: 
Gradient Boosted Regressor builds an additive model in a forward stage-wise fashion; it allows for the optimization of arbitrary loss functions. In each stage
a regression tree is t on the negative gradient of the loss function. The hyperparameters that I were again tuned to avoid overfitting. The advantage of using an ensemble
technique like boosting is that we can incrementally keep on building a better model which works best for us.

Of all the models: Gradient Boosting gave the least MAE followed by Random Forest