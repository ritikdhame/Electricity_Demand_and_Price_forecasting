# Electricity_Demand_and_Price_forecasting
![image](https://github.com/ritikdhame/Electricity_Demand_and_Price_orecasting/assets/7029092/bbfbbb44-1fc0-406b-81f8-d4d2760b9030)

# Objective: 

The focal point of this project revolves around time series forecasting, encompassing the integration of two separate datasets comprising energy and weather data. By amalgamating energy consumption and weather-related metrics from multiple cities in Spain, the project endeavors to tackle a multivariate time series forecasting challenge.

The project employs a diverse array of forecasting models, including the XGboost Regressor, GRU (Gated Recurrent Unit), LSTM (Long Short-Term Memory), CNN (Convolutional Neural Network), CNN-LSTM, and LSTM-Attention. Additionally, hybrid models like GRU-XGBoost and LSTM-Attention-XGBoost are employed, harnessing the strength of multiple techniques through ensembling.

Overall, this project seeks to harness the power of these forecasting methodologies to derive accurate predictions for electricity demand and pricing in a time-dependent context, thereby contributing to the advancement of energy forecasting and enhancing decision-making within the energy sector. 
 

## About the Dataset:

The energy consumption and weather data from various cities in Spain are combined to create a multivariate time series forecasting problem. The energy dataset contains features related to the generation of energy from different sources like fossil fuels, wind, and coal. On the other hand, the weather dataset contains features related to various weather metrics such as temperature, humidity, pressure, wind speed, etc.

The dataset includes a four-year record of weather data <a href="https://openweathermap.org/api">https://openweathermap.org/api</a> 
electrical consumption, pricing, and generation data for Spain <a href="https://transparency.entsoe.eu/dashboard/show">ENTOSE website</a> . The public ENTSOE portal was used to retrieve the consumption and generation data, while 
the Spanish TSO Red Electric España was used to obtain the settlement prices <a href="https://www.esios.ree.es/en/market-and-prices?date=27-03-2023#">TSO website</a>. 

# Method 
The code consists of 4 main parts:

- Data loading and feature exploartion: This part uses os and pandas to load, process the data into a dataframe, plotting correlation matrix on both the dataset. 
- Preprocessing: Involves getting rid of Null values, selecting features required hour,weekday, month, year from the data and plotting visualization, followed by normalizing and reshaping the data follwed by using The Dickey-Fuller test to check if thr data us stationary
- Model building and training: This part using PCA to select the features necessary,normalizing target variables and then building forecasting models With XGBoost, GRU, LSTM, CNN, CNN-LSTM,LSTM attention, GRU-XGboost, LSTM attention-XGboost.
- We plot the train an validation Mean Absolute Error for each case and also compare the scores across the different models towards the end. 

![image](https://github.com/ritikdhame/Electricity_Demand_and_Price_orecasting/assets/7029092/08e42691-68ec-4ccd-9bec-5dcc51206844)

## Requirements

To run the code, you need to install the following libraries:

- matplotlib
- Numpy, panda, math
- Seaborn
- Xgboost
- Tensorflow
- keras
- Scikit Learn 

## Motivation:
This dataset stands out due to its comprehensive hourly data on electrical consumption, along with the corresponding forecasts provided by the TSO for consumption and pricing. This unique combination allows for a valuable opportunity to compare prospective forecasts against the current state-of-the-art industry predictions.

The dataset opens up a realm of intriguing questions that can be explored:

Load and Marginal Supply Curves: The project aims to analyze and visualize how the load and marginal supply curves manifest based on the dataset's information.

Weather Impact on Electrical Demand, Prices, and Generation: Through detailed analysis, the project will identify which weather measurements and cities exert the most significant influence on electrical demand, pricing, and generation capacity.

Enhancing TSO's 24-Hour Forecast: The project seeks to improve upon the accuracy of the TSO's 24-hour advance forecast for electrical consumption and pricing.

Time-of-Day Electrical Price Prediction: Can the project achieve more precise predictions of electrical price based on different times of the day compared to the TSO's forecasts?

Intraday Price and Electrical Demand Forecasting: By utilizing the dataset's rich hourly data, the project endeavors to develop hour-by-hour forecasts for intraday price and electrical demand.

## Models used in this project : 

#### 1. Machine learning : 
 * XGboost Regressor
#### 2. Deep learning/Stacked models :
* GRU 
* LSTM 
* CNN 
* CNN-LSTM 
* LSTM-Attention 
#### 3. Hybrid methods:   
* GRU-XGBoost 
* LSTM-Attention-XGBoost 

## Results
The MAE (Mean Absolute Error) is used to report the results for the normalized test set:
* TSO prediction : 0.070
* XGboost : 0.016
* GRU : 0.015
* LSTM : 0.018
* CNN : 0.025
* CNN-LSTM : 0.019
* LSTM-Attention : 0.015
* Hybrid GRU-XGBoost : 0.014
* Hybrid LSTM-Attention-XGBoost : 0.015
Note : According to the findings, the hybrid methods demonstrated better performance in terms of MAE compared to other methods. It is worth mentioning that all machine learning/deep learning methods outperformed TSO prediction.
 
