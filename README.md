# Predicting U.S. Youth Cigarette Usage in 2019 Using Markov Chain 
by Davin Kaing

## Abstract 

Cigarette usage is prevalent among youth in the United States, however, recent findings show that there’s a decrease in youth cigarette usage [1]. This report examines this trend and predict future youth cigarette usage behavior using Markov Chain. 

## Introduction

The purpose of this project is create the most optimal Markov chain model to predict smoking behaviors of youth in the U.S. in the year 2019. The datasets [2] are retrieved from www.data.gov, and they were collected in the following years: 1993, 1995, 1997, 1999, 2001, 2003, 2005, 2007, 2009, 2011, 2013. Other attributes of the data include the location (state) the information was gathered as well as the gender of the collected sample size. There are also missing values in the data, hence cigarette usage proportions in some states may be missing in the analysis.

## Method & Procedure 

Since the future smoking behavior is dependent on the past behavior, the Markov chain model can be created from data collected. For example, in year 1993 and 1995 for a particular state, the following probabilities are computed: 

-	Youth smoke in 1995 given their smoking behavior in 1993 
-	Youth do not smoke in 1995 given their smoking behavior in 1993
-	Youth do not smoke in 1995 given their non-smoking behavior in 1993
-	Youth smoke in 1995 given their non-smoking behavior in 1993


After these probabilities are computed, they are assembled into a 2 X 2 transition matrix where the rows and columns have probabilities of smoking and non-smoking for a particular location (state). The transition matrix is used to compute the smoking behaviors of test years (see Model Assessment & Prediction) to test for model accuracy. This process is repeated for all 50 states. Afterwards, using the best model, for example, the smoking values in 2019 are predicted.

There are 5 models created from the dataset. These models are derived from pairs of years in chronological order as shown below: 

![](http://i.imgur.com/b6j7oxB.png)

To assess for the best model, the datasets in the year 2007, 2009, 2011, and 2013 are reserved for testing of the models built from the previous years. The model with the lowest sum of squared errors (the sum of the squared errors from predicted and true values) is used to predict smoking behavior in 2019. 

## Results & Discussion

The cigarette usage behaviors of both male and female youth are explored (Fig. 1a & Fig. 1b). These two plots appear to have similar decreasing trend in cigarette usage over time. To predict this trend in the future, five models (Table 1) are created using Markov Chain and their performances are assessed using the proportions of cigarette usage in 2007, 2009, 2011, and 2013. As shown in Figure 1c and 1d, for both male and female cigarette users, model 4 appears to have the lowest sum of squared errors. This result is consistent with the exploratory analysis, as shown in Figure 1a and 1b, the decreasing trend of year pair 1999 and 2001(Model 4) is most representative of the cigarette usage decreasing trend from 2007 to 2013. The boxplots of these models (Fig. 2a & Fig. 2b) further confirm that Model 4 has the lowest errors in predictions. With this information, Model 4 is selected as the best model to predict the proportions of youth cigarette usage in 2019 (Fig. 2d). Comparing this prediction with the proportions of youth cigarette usage in 1999 (Fig. 2c), the predicted usage in 2019 is lower than the usage in 1999. This evidence further supports the analysis because the trend in the exploratory plots (Fig. 1a & Fig. 1b) show that there’s a decreasing trend of cigarette usage over time. 

![](http://i.imgur.com/B6gMo9M.png)
![](http://i.imgur.com/Xl6WtwX.png)

## Conclusion

Overall, there’s a decreasing trend in cigarette usage over time. From the Markov Chain models, the model that best predicts the future trend in youth cigarette usage is Model 4. 

## References

1] Youth and Tobacco Use. (2015). Retrieved May 01, 2016, from http://www.cdc.gov/tobacco/data_statistics/fact_sheets/youth_data/tobacco_use/ 

[2] Data Catalog. (n.d.). Retrieved May 01, 2016, from http://catalog.data.gov/dataset/youth-risk-behavioral-surveillance-system-yrbss-data-d723c 








