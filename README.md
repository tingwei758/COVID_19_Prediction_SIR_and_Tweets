# COVID_19_Prediction

More detailed explanation can be found in [reports/COVID-19_Prediction.pdf](./reports/COVID-19_Prediction.pdf)

## Methodology

We use Twitter data to improve the performance of an epidemiological model like SIR on its predictive power of future COVID 19 infection cases. More specically, we generate the  SIR curve using Least Squared Estimate as the baseline function. We then collect unigrams and bigrams from COVID 19 related Tweets and count their frequency at a daily level. We then rank the keywords by their absolute correlation to the derative of the cumulative cases curve. Finally, we input the baseline function and the top 20 keywords as explanatory variables of a Linear Regression, number of confirmed case (leading 4 days) as response variable, using L2 regularization to avoid overfitting.

## Data

COVID-19 data are found from [www.canada.ca](https://www.canada.ca/en/public-health/services/diseases/2019-novel-coronavirus-infection.html). This data set includes all informations to generate the SIR curve.

Tweets are downloaded from [kaggle](https://www.kaggle.com/smid80/coronavirus-covid19-tweets). This data set contains all Tweets that are tagged as COVID19 (or its synonyms), including non English ones. Hence, preprocessing is needed. Because this data set is very large (~40M records), it is processed in a distributed environment using Spark.

## Result

We use data in March to train the model and the first 4 days in April to evaluate its predictive performance. The predictive power of our model is much better than the baseline model (using SIR only)
  
![image2](./reports/img/image2.jpg)
![image1](./reports/img/image1.jpg)



