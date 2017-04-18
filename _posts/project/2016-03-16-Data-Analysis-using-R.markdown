---
layout: project
title:  "Data Analysis using R"
date: 2016-03-16 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: snow.jpg
thumb: 
<!-- carousel: 
- single01.jpg -->
tagged: 
client: 
website: https://github.com/saurabhkulkarni2312/R-Projects/tree/master/Calibrating-Snow-Gauges-Regression
---
## Data Analysis using R
These case studies were performed for the course **Data Analysis using R** offered by the Math and Statistics Department at UCSD. 
Each of these projects were done in groups of 2 or 3. Through these projects I was able to implement a typical data analysis workflow 
right from cleaning the data to visualizations to choosing features to modeling and finally interpreting results.
**R** was used to implement the various statistical modeling methods. Links to each R notebook/script file as well as project report have been 
provided below

List of Case studies:

1. Recommendations for Calibration of Snow Gauges
2. Searching for potential replication sites in Human Cytomegalovirus (HCMV) DNA data
3. Explore effect of maternal smoking on infant birth weights

---

---

#### Recommendations for Calibration Snow Gauges
#### Project Links
[Calibration of Snow Gauges Code](../assets/writeups/Recommendations-for-calibrating-gauges.html)

[Project Report](../assets/writeups/Snow-Gauge-Report.pdf)

#### Project Details
**Aim** was to find a relationship between the density with respect to gain and evaluate the performance of linear regression.

**Description**: This data is provided by the USDA during one of their calibration sessions in the Sierra Nevada. For our gauge model, different blocks of polyethylene with known densities are placed between the emitting rod and the receiver rod for the gauge. As gamma rays pass through the polyethylene blocks, the gamma ray may be absorbed, bounce away from the receiver rod, or pass through the block to the receiver rod. For each block, 30 measurements are taken, and the middle 10 are reported in the dataset; the measurement from the gauge is called *gain* There were 9 blocks in total.

Here, I have tried to observe how well simple models like linear and log-linear regression model can be used to model the data. Various visualizations have been performed to illustrate the performance.
The aim was not to fit best model but to evaluate the performance of linear regression model (with and without log transformation) and see what all tests we can perform to visualize the performance. For detailed analysis report do checkout the R notebook on my Github page

---

___

#### Searching for potential replication sites in Human Cytomegalovirus (HCMV) DNA data
#### Project Links
[HCMV Code](../assets/writeups/HCMV.html)

[HCMV Report](../assets/writeups/HCMV-Report.pdf)

#### Project Details
**Aim** 
Identify certain patterns in DNA data (which is 229,354 base pairs long) which could potential DNA replication sites in Human Cytomegalovirus

**Description**: 
The Human Cytomegalovirus (HCMV) is a potentially life threatening disease. HCMV is dicult to detect because the virus remains dormant until a critical
mass is achieved through reproduction. In order to combat the virus, virologists need to isolate origin of replication so that the reproductive cycle of the virus may be interrupted. 
Researchers believe that palindrome sites in DNA might be such locations which could be sites of replication. However some palindromes may also occur by chance.

Hence, we are seeking to identify those certain clusters of palindromes in HCMV DNA Data are statistically dierent from the other
clusters. In other words, certain clusters of palindromes that do not occur by random chance given the
distribution of the clusters may signify the location of the origin of replication. The researchers working on HCMV should begin their search and medical research within these clusters, to save time.

---

___

#### Explore effect of maternal smoking on infant birth weights
#### Project Links

#### Project Details
**Aim** 
**Description**: 
