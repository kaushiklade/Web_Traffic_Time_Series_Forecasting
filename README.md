# Web_Traffic_Time_Series_Forecasting
Web Traffic Forecasting is a problem of forecasting the future page views that we can receive for given Wikipedia articles. The prediction to be carried out based on the available time series data.
In this problem, we are provided with Page Views of approx. 145k Wikipedia articles. Our goal is to forecast the Page Views for these articles for future timestamps. Let’s understand about the data from Exploratory Data Analysis (EDA).

## Exploratory Data Analysis (EDA) :
With Train_\*.csv being the base file in this problem, we are given information about Page Name and it’s Page View for given dates.
The information can be extracted from Web page which contains *Site Name*, *Agent*, *Language*, *Access*.
We prepared the data in such a way to add pageviews of each pages from previous dates as well as above extra features.

### Metric for Evaluation
The performance metric for this problem is provided by Kaggle which is SMAPE i.e. Symmetric Mean Absolute Percentage Error which can be percentage of summation of ratio of absolute error of forecasted and actual value with summation of absolute forecasted and actual value.

## ML Modeling

We can consider the lagged pageviews for all train set to compare the model performance of Machine Learning models. 
This analysis include
 * Window Mean Model
 * Linear Regression Model with Square and Huber loss
 * Adaboost Regressor Model
 * Random Forest Regressor Model
 * XGBoost Regressor Model
Tree based models perform well on given data, also the model performances on unseen data is also good with SMAPE value.

## DN Modeling

Keeping the same approach of modeling, we implemented Deep Learned models for this problem which include,
 * Simple Deep Neural Network
 * N Layered LSTM Model
 * CNN based Deep Neural Network Models
 * Deep Neural Network models with combination of CNN and LSTM
With LSTM based models we are trying to capture the impact of previous values on the future value. The lagged value importance can be also captured in CNN based models.
Comparing performance of these DN Models, we can conclude, CNN based model tend to perform well on unseen data with lowest SMAPE value.

<hr>

Model performance can be improved by extracting more features from the pageviews e.g. FFT value, Trend, Cycle etc.
Detailed blog for the same can be available on https://kaushiklade27.medium.com/web-traffic-time-series-forecasting-6c916c7f5d85
