# Homework 5

## Problem 1: Correlation, Autocorrelation, Multiple Linear Regression

In this problem, you will explore the relationship between air temperature, precipitation, and [snow water equivalent](https://www.nrcs.usda.gov/wps/portal/nrcs/detail/null/?cid=nrcseprd1314833) over time, using observations from a study site in the Washington Cascades. Download the {Download}`cascades_swe.xlsx</modules/data/cascades_swe.xlsx>` dataset for this problem.

**A.** Begin by making scatterplots of each of these variables vs. all the other variables. Describe any visual patterns you see between each pair of variables.  

**B.** Calculate the correlation (R) between April 1 SWE and the three meteorological variables (precipitation, maximum temperature, and minimum temperature). Then also calculate R between each unique combination of the meteorological variables. Which meteorological variables seem the most correlated with each other?  How might it cause problems if we use both of these in a multi-linear regression?
 
**C.** Calculate the autocorrelation in precipitation, maximum temperature, and minimum temperature over the timeseries. Can we consider each of these values to be an independent sample? Or do some of them depend on the prior year’s sample?

```{note}
In part **C**, we can test for autocorrelation at different lags, but not for any lag longer than a quarter of the length of the data series. Therefore, test for lags from 1 to N/4, where N is the length of the data series.
```

 **D.** Fit a multiple linear regression model to the data, using only two of the three meteorological variables (precipitation and maximum temperature) to predict April 1 SWE. Report the trend in each meteorological variable. Estimate the overall trend in SWE, and the trend due to each meteorological variable alone. How much of the overall trend is due to the effect of a trend in the maximum temperature?  (Note that if we were doing this for research, it would be good to also explore using only minimum temperature, or using the mean daily temperature calculated as (Tmax + Tmin)/2 -- however, for simplicity, we will only look a maximum temperature in this problem.)
 
```{note}
In part **D** we want to quantify how much a change in each variable accounts for a change in SWE. We start with making a multiple linear regression model, such as one which looks like:

SWE = B0 + B1*(precip) + B2*(t_max)

We then have values for all regression parameters (each B value). Take the derivative of both sides with respect to time. Our regression parameter values are coefficients in this new equation.

dSWE/dt = B1*d(precip)/dt + B2*d(t_max)/dt

Then to find how much the trend in SWE is accounted for by the trend in precipitation we compute B1*d(precip)/dt, where d(precip)/dt in the slope of the trend in precipitation.
```

## Problem 2: The best graphics
 
One of our greatest challenges in data analysis is to be able to visualize the information in the data and convey that information to others. Consider various scientific papers you have read (on any subject related to your scientific/engineering discipline) and pick out your favorite graphical representation of data (e.g., the best figure). Include your top two choices in your homework submission with a brief statement of why you chose these figures. We'll share some of these favorite figures in class.

## Problem 3: Peer Reviews (CEWA 565)

Complete the peer review(s) that you were assigned on Canvas. Your review should be thoughtful, but it does not need to be long, nor does it need to focus on minor spelling or grammar mistakes. Write a few sentences describing the most important change that can be made to improve the draft (e.g. "reorganize the paragraphs to better explain X", "add more supporting evidence for the topic statement"). Refer to the prior homework assignment to see guidelines for the draft project reports. (the rubric for the final report is available for your reference [here](/overview/b-project.md))