# Business-analysis-and-marketing-suggestion

1 AB Test ： https://github.com/nirupamaprv/Analyze-AB-test-Results

2 DAU MAU Analysis：

WITH
  dates AS (
    SELECT current_date - 30 as start_date,
    current_date - 1 as end_date
  ),
  dau AS (
    SELECT count(distinct(user_id)) as ct
    FROM visits dates
    WHERE visit_date = end_date
  ),
  mau AS (
    SELECT count(distinct(user_id)) as ct
    FROM visits, dates
    WHERE visit_date between start_date and end_date
  )
SELECT dau.ct::float / mau.ct::float * 100
FROM dau, mau;

 （https://gist.github.com/bdarfler/08711e1a15b48e4d379f）
   （https://gist.github.com/mixpanel-bot  ）

3 Trend Prediction

In statistics and econometrics, and in particular in time series analysis, an autoregressive integrated moving average (ARIMA) model is a generalization of an autoregressive moving average (ARMA) model. Both of these models are fitted to time series data either to better understand the data or to predict future points in the series (forecasting). ARIMA models are applied in some cases where data show evidence of non-stationarity, where an initial differencing step (corresponding to the "integrated" part of the model) can be applied one or more times to eliminate the non-stationarity

https://en.wikipedia.org/wiki/Autoregressive_integrated_moving_average
https://github.com/statsmodels/statsmodels/tree/master/statsmodels/tsa

4 Learning Video ：

https://www.udacity.com/course/ab-testing--ud257
https://www.coursera.org/specializations/social-media-marketing
      
