# Predicting the Real Estate Market

## Author: Harrison Gu

## Overview

We will use time series models to predict average median home prices in various zip codes across the country. Our goal is to find the best real estate investment opportunities for our client that match his risk profile.

## The Data

This project uses real estate price data from zillow.com, and contains average median home prices in various zip codes across the country, as well as various other features:

RegionID
RegionName (zip code)
City
State
Metro
CountyName
SizeRank

We selected 6 zipcodes that match our client's risk tolerance: 60657, 60614, 90046, 90034, 10128, 11106

## Analysis

We first ran baseline ARIMA models for each of the selected zip codes, using parameters determined by ACF, PACF, and other EDA. We then ran auto ARIMA and auto ARIMA dynamic forecasts for each model, and used AIC as our metric to compare models. We found that auto ARIMA gave the best model for every zip code except for 10128, where auto ARIMA dynamic was best.

We also ran FB Prophet models for each of the selected zip codes. 

Zip codes 11106 and 90034 were both in the top 3 zip codes in the ARIMA and FB Prophet models.
Zip codes 60614 and 60657 were both in the worst 3 zip codes in the ARIMA and FB Prophet models.
Interestingly, 60614 and 60657 are both in Chicago, which might give some insight on Chicago's overall real estate market. 

## Next Steps

For further investigation, we will do a deep dive into engineering metrics to make the ARIMA and FB Prophet models comparible. We will also use SARIMAX to incorporate seasonality and exogenous variables into our models. Lastly, once we have selected our target zip codes, we will repeat the same process for neighborhoods within those zip codes.