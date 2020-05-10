# COVID_19_Prediction

A detailed explanation can be found in [reports/COVID-19_Prediction.pdf](./reports/COVID-19_Prediction.pdf)

## Methodology

We use Twitter data to improve the performance of an epidemiological model like SIR to predict the future covid-19 infection case. More specically, we generate a SIR curve using LSE and find 20 unigrams and bigrams in Tweets whose document frequency are most highly correlated with the daily infection rate (number of new confirmed cases). We input these as features to a Linear Regression model, applying regularization methods, to predict the number of cumulative confirmed cases within the next 4 days.

## Data

COVID-19 data are found from https://www.canada.ca/en/public-health/services/diseases/2019-novel-coronavirus-infection.html

Tweets are downloaded from https://www.kaggle.com/smid80/coronavirus-covid19-tweets

## Result

We use March data as the training set and first 4 days in April as test set. The predictive power of our model is much better than the baseline model (using SIR only).


