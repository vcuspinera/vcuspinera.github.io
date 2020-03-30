---
title: "Bike Sharing Machine Learning Model"
author: "Aman Kumar Garg, Victor Cuspinera-Contreras, Yingping Qian"
collection: projects
type: "Docker"
permalink: /projects/2020/bike-sharing
venue: "MDS-UBC GitHub"
url: "https://github.com/UBC-MDS/DSCI_522_Group_409"
date: 2020-02-29
location: "Vancouver, BC, Canada"
tags:
  - R
  - Python
  - Docker
  - MDS student
  - UBC
---

Demand forecasting is an important aspect for many companies in carrying out their operations. In this project we analyze the bike-sharing dataset from [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset), and build a regression learning machine model using the **Random Forest Regressor** algorithm to **predict the count of bike rentals** based on time and weather-related information. For this project we use **Docker**, making it easier to replicate the analysis.  
*[Click here](https://github.com/UBC-MDS/DSCI_522_Group_409) to look at the original GitHub repository of this project.*  

*Authors: Aman Kumar ([amank90](https://github.com/amank90)), Dora Qian ([doraqmon](https://github.com/doraqmon)), and Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  

## Dataset
The data that we use to build the model comes from the bike-sharing dataset created by Dr. Hadi from [LIAAD](http://www.liaad.up.pt) and shared in the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). 

This dataset contains the hourly information about the numbers of bike rentals in Washington, DC between 2011 and 2012. It has 17 variables, standing out:  

1. `cnt` (*our tarjet*) count of total rental bikes including both casual and registered  
2. `season`: Season (**1**:spring, **2**:summer, **3**:fall, **4**:winter)  
3. `dteday`: Date
4. `hr`: Hour  
5. `holiday`: (**0**: No, **1**: Yes)  
6. `weekday`: Day of the week (starting from **0**: Sunday)  
7. `workingday`: (**0**: No, **1**: Yes)  
8. `weathersit`:  (**1**: Sunny or partly cloudy. **2**: Mist or cloudy. **3**: Light rain or snow. **4**: Heavy rain, thunderstorm or snow)  
9. `temp`: Normalized temperature in Celsius  
10. `hum`: Normalized humidity  
11. `windspeed`: Normalized wind speed  

## Explanatory Data Analysis (EDA) 

In this initial analysis, we separate the dataset in two parts: train and test. Afterwards, we built some visualizations to deep dive the data and found the relationships between different variables, as well as the explanatory variables with a higher correlation with the target variable (number of bikes rented). The full EDA report can be found [here.](https://github.com/UBC-MDS/DSCI_522_Group_409/blob/master/eda/EDA_summary.md)  

Among our finds, we observe that the demand for bikes increases when the weather is warmer and decreases when the temperatures are lower. 

<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/img/fig_2b_workingday.png" width="650"/>

Figure 1. Analysis of temperatures by workingday  

The day of week and hour of the day clearly affects the count of bike rental. Also, people rent these bikes mainly for work and school on weekdays showing the peak of the demand in two times of the day. Besides, people use rental bikes between 11 am and 4 pm during weekends.  

<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/img/fig_3_hr.png" width="650"/>

Figure 2. Analysis per hour and weekday  

The correlation matrix between features, including the target variable, is shown below.  
<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/img/fig_5_corr.png" width="650"/>

Figure 3. Correlation matrix  

## Analysis
The original dataset has categorical features preprocessed using label encoding and numerical features preprocessed using [MinMaxScalar](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html). So, we decide to de-normalize the numerical features before splitting the data in train and test datasets. Also, we changed holiday and workingday to [OneHotEncoding](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html).

For the analysis we test different models from [Scikit-learn](https://scikit-learn.org/stable/), tunning different hyperparameters (i.e. ‘max_depth’ and ‘n_estimators’) which were chosen used 5-fold cross-validation with mean squared error as the regression metric.

For this project we use both **the R** and **Python** programming langues, R mainly for Data Wrangling and Python for Model Selection.  

## Results

To choose the best prediction model, we test the [Linear Model Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html), [KNN](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html) and [Random Forest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html) from [Scikit-learn](https://scikit-learn.org/stable/) and choose the one that returns the best score in the test dataset, comparing the `mean_squared_error` and the error for both training and testing error. The full final report can be found [here.](https://github.com/UBC-MDS/DSCI_522_Group_409/blob/master/doc/bike_sharing_ml_model.md)  

|Model|Train.Error|Test.Error|Train.r2.score|Test.r2.score|Best.Parameters|Computational.Time..sec.|
|:---|:---:|:---:|:---:|:---:|:---|:---:|
|LinearRegression|147.91|145.61|0.34|0.35|{‘normalize’: False}|0.09|
|KNN|72.19|78.43|0.84|0.81|{‘n_neighbors’: 15}|1.51|
|RandomForest|63.88|70.71|0.88|0.85|{‘max_depth’: 10, ‘n_estimators’: 50}|127.88|

As we can see above, Random Forest is the best model with minimum training and testing error. By hyperparameter tuning, we get best hyper parameters as `max_depth: 10`, and `n_estimators: 50`.  

It is possible to see the feature importance through random forest regression.  

<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/result/feature_importance.png" width="650"/>

Figure 4: The plot for importance for predictors.  

The variable `hr` is the most important feature to predict bike ridership. The second most important feature is `temp`.

In order to visualize the results, we also compared in the next plot the between real rides from test dataset vs. the predicted rides from our Random Forest model.

<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/result/fig_result.png" width="650"/>

Figure 5: The plot for predicted and actual rides  

The relationship looks very linear which means that the predicted values are close to the actual values. The model can be used to predict the ridership in the future given the input features.

In order to improve our model further, we can perform more feature engineering.
