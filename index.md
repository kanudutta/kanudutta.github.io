---
title       : Energy Performance Estimation of Residential Buildings  
subtitle    : Using Machine Learning Techniques
author      : Kanu Dutta
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Motivation behind the app



1. Building energy consumption has increased tremendously worldwide, 40% of total primary energy is consumed by buildings alone in US

2. Increased energy consumption leads to higher GHG emissions, which means accelerating Climate Change

3. Energy simulation especially during the design phase, can help in improving the efficiency of
buildlings,leading to lower energy consumption during the operations phase.

4. Simulation is tedious process and it takes hours to do the job.

5. Having tools which can predict heating and cooling load ,during conceptual stage, can help  designers to analyze the influence of input parameters on energy consumption.

6. [App link](https://kanudutta.shinyapps.io/EnergyPrediction)



--- .class #id 








## App Guide

1. It has slider input and allows you to choose among several parameters
2. Parameters are surface area of the building, orientation,Height,Roof area,Glazing Area
3. The dash board consists of Plots, assumption made, Reference Material and Data  
4. Based on your choice of parameter it gives you the heating and cooling load required
<img src="assets/fig/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

--- .class #id 



## Recipe for the building the app

1. Data Sourced from UCI repo store
2. Data munging:- basically slice and dice to make it fit for consumption
3. Partitioned the data in two parts , train and test data
4. performed Exploratory Analysis such as pairwise plots, correlation maps
5. Analysed relationship between predictor, check for normality and multicollinearity in the data
6. Residual diagnostics to see if the v
ariance is homoskedastic,avoided linear regression as the result was negative 
7. Outlier analysis done to check if robust regression is required
8. All the result pointed towards using non linear methd, hence models were built using Neural Network , Support Vector Regression,KNN, Random Forestand Bagged Tree algorithms
9. Ensemble stacking with the help of GAM method was used to combine the models 
10. In sample and out sample error were compared to finalise the model
11. Out sample erro was used to select the final model


--- .class #id


## Spearman's Correlation  and Variable Importance in prediction


```r
corrplot(M, order = "FPC", method = "color", type = "lower", tl.cex = 0.8, 
         tl.col = rgb(0, 0, 0))
mtext("Spearman's Correlation Map", side=3, outer=TRUE, line=-3,cex=1.5) 
p
```

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.png) ![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-2.png) 
--- .class #id 
