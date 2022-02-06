# Rainfall Forecasting with Seasonal ARIMA vs Exponential Smoothing (ETS)

## Project Introduction
A forecast is a calculation or prediction of some future event or condition. Forecasting will be helpful as a guide before taking action in some condition in the future. In Indonesia, as a country that is quite dependent on agriculture, prediction of future rainfall will be very helpful in the pre-planning water resources. Especially as we know unexpected amount of rainfall due to climate change can affect agricultural productivity. But to prevent that, we can decide when is the best time to start planting and maximizing the harvest from the prediction of future rainfall. 

In this project, we will try the forecasting using Python language and the forecast model that will be used are Seasonal ARIMA and Exponential Smoothing (ETS). Then from the two models used in the analysis, we will choose which model that has the best performance on the forecasting. The purpose of the analysis is to determine the range of the amount of rain that will occur and see the rainfall trends in the next few years, such as whether there will be an increase or decrease in extreme rainfall or a seasonal shift because of the effects of climate change that currently happening. 

[The data used](https://github.com/nurannisaa/Seasonal-ARIMA-for-Rainfall-Forecasting/blob/main/g4.areaAvgTimeSeries.TRMM_3B42_Daily_7_precipitation.19990101-20190101.180W_50S_180E_50N.csv) in this analysis are obtained from [Giovanni](https://giovanni.gsfc.nasa.gov/giovanni/#service=TmAvMp&starttime=2000-01-01T00:00:00Z&endtime=2021-01-01T23:59:59Z), a web interface that allows users to analyze NASA's gridded data from various satellite and surface observations. 

## Forecasting Models
A research article titled *"Statistical and Machine Learning forecasting methods: Concerns and ways forward"* shows a visualization below where it shows the overall sMAPE for all statistical and ML methods used for forecasting in M3 Competition. As we can see, ARIMA and ETS are the two methods that performed best among the other methods. Therefore, ARIMA and ETS methods will be used in this forecast modelling.

![image](https://user-images.githubusercontent.com/92699016/152678223-2e3f5c6d-8ffa-4762-aa36-087738bead62.png) 

*source : Makridakis, S., Spiliotis, E. & Assimakopoulos, V. Statistical and Machine Learning forecasting methods: Concerns and ways forward. PLoS One 13, 1-26 (2018)*

### ARIMA Model
ARIMA, short for ‘Auto Regressive Integrated Moving Average’ is actually a class of models that ‘explains’ a given time series based on its own past values, that is, its own lags and the lagged forecast errors, so that equation can be used to forecast future values. An ARIMA model is characterized by 3 terms: 
- p: autoregressive order
- q: moving average order
- d: difference order

If a time series has seasonal patterns, we need to add seasonal terms and it becomes SARIMA, short for ‘Seasonal ARIMA’.
There are four seasonal elements that are not part of ARIMA that must be configured; they are:
- P: Seasonal autoregressive order
- D: Seasonal difference order
- Q: Seasonal moving average order
- m: The number of time steps for a single seasonal period

**In this project, we will determine the best value for each parameter in seasonal arima model that will be used for forecasting.**

### Exponential Smoothing (ETS)
Exponential smoothing is a time series forecasting method for univariate data that can be extended to support data with a systematic trend or seasonal component. There is three type of exponential smoothing methods :
- Simple (single) exponential smoothing uses a weighted moving average with exponentially decreasing weights.
- Holt’s trend-corrected double exponential smoothing is usually more reliable for handling data that shows trends, compared to the single procedure.
- Triple exponential smoothing (also called the Multiplicative Holt-Winters) is usually more reliable for parabolic trends or data that shows trends and seasonality.

**In this project, we will determine which ETS method that will be used for forecasting after identifying the error, trend, and seasonality from the data set.**

## Project Summary

![image](https://user-images.githubusercontent.com/92699016/152681342-12d76ff8-549f-40ad-8977-d7d6852f9b55.png)

- Seen from the metric evaluation and visualization of the model results, SARIMA model has a better performance in forecasting more than exponential smoothing.
- The model results do not show any seasonal shifts in the next few years and an increase or decrease in trends so that the impact of climate change cannot be seen from the results of the model analysis.
- Two models used in the analysis may provide a range of rain that is likely to occur, but it is still very far from accurate and basically rainfall can be unpredictable due to climate change.
- Since the results of the analysis do not show any seasonal shifts, rainfall in the next three years (after 2019) would not have an impact on agricultural cropping patterns.

## Model Recommendation
- The more data used in the train set, the more accurate the model can perform. 
- Try more combinations of parameters in order to improve the model.
