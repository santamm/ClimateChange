# ClimateChange
Climate Change Temperature Predictions

### Table of Contents

1. [Installation](#installation)
2. [Project Analysis](#motivation)
3. [Metric](#metric)
4. [File Descriptions](#files)
5. [Results](#results)
6. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>
The code in this project is written in Python 3.6.6 :: Anaconda custom (64-bit).
The following additional libraries have been used:
* pandas
* numpy
* matplotlib
* seaborn
* sklearn
* warnings
* time
* progressbar
* keras
* statsmodels


## Project Analysis<a name="motivation"></a>
This projects is divided in two parts: the first part is an exploratory analysis of the dataset, where the first questiopn we want to answer is: Is The Global Temperature Really Rising?? 
The resulting visualization shows that temperatures have been rising sharply from the 1970s.
Then we present some visualizations with:
* a world map with average Temperatures by Country
* a time series of the average temperatures by Continent
* a visualization with countries with highest difference between max and min temperature
* a world map with difference between max and min temperature for each country
* a barchart with the cities in South Africa ordered hottest to coldest
* a heatmap of the major cities in SA

In the second part we apply machine learning algorithms to the time series of the temperature to predict future tempertures. We first use models with a window size of 1, where a temperature in time is used to predict the one in the next time instant (usually a month). These models don't perform well in terms of predicting future temperatures that are more distant in time becuase of the seasonality of the data. Then we use models with a window size greater than one, and these ones reach higher accuracy in the prediction.

We compare the performances of the following models:
* Linear Regression
* Feed Forward Neural Network
* Long Short-Term Memory (LSTM): a type of recurrent neural network capable of learning order dependence in sequence prediction problems.
* LSTM  using a moving forward window of size 50, which means we use the first 50 data points as input X to predict y1 — 51st data point. Next, we use the window between 1 to 51 data points as input X to predict y2 i.e., the 52nd data point and so on.

## Metric<a name="metric"></a>
 The metric used to compare all models is RMSE. The loss function used is MSE.

## File Descriptions <a name="files"></a>
The Jupyter notebooks included in this project are:
- Climate Change Hackaton.ipynb


Data files (under data directory):
- GlobalTemperatures.csv: Monthly Time series of global average temperature from 1750 to 2015
- GlobalLandTemperaturesByCountry.csv: Monthly Time series of averages temperature by country from 1750 to 2015
- GlobalLandTemperaturesByCity.csv: Monthly Time series of averages temperature by city from 1750 to 2015.


## Results<a name="results"></a>
The LSTM with a window size of 50 returns an RMSE of 0.883648, which outperforms all other models with window size of 1 whose best RMSE is 2.099682 with the Linear Regression predictor.

## Licensing, Authors, Acknowledgements<a name="licensing"></a>
For licensing see LICENSE file.
The dataset has been supplied from [Berkeley Earth](http://berkeleyearth.org/data/). It can be downloaded from [Kaggle](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data) under license CC BY-NC-SA 4.0.

