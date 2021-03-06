---
title       : Predicting Car's Miles per Gallon
subtitle    : A project for Coursera Developing Data Products class
author      : Andreas Hadimulyono
job         : (Use the arrow keys to navigate the slides)
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Purpose

1. When evaluating cost of ownership of a car, it is important to estimate fuel consumption
2. Low fuel efficiency may unnecessarily expose car owners to volatile fuel price

--- .slide-1 #slide1 

## Data Source

1. The algorithm for this application is built from cars dataset in R
2. The dataset has contains a lot of variables. For this application only mode of transmission, number of cylinders, and weight of the car is taken into consideration.

--- .slide-2 #slide2

## Model

1. Linear model is used to fit the data set




```r
data(mtcars)
fitData <- mtcars[,c("mpg", "am", "cyl", "wt")]
fit <- lm(mpg ~ am + cyl + wt, data = fitData)
```

--- .slide-3 #slide3

## Prediction

1. Takes three inputs: mode of transmission, number of cylinders, and weight.
2. Input is then used to predict the car's MPG.
3. Example:


```r
newdf <- data.frame(am = 0, cyl = 4, wt = 1.5)
predict(fit, newdf)
```

```
##        1 
## 28.68924
```

--- .slide4 #slide4

## Application

1. Application is built using Shiny.  
2. Hosted on https://ahadimulyono.shinyapps.io/shiny


