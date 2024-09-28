# KNN-Based Predictive Modeling for California Housing
by Matthew Chuang

## Overview
This project focuses on the analysis and prediction of housing prices in California using a dataset from the 1990 California housing census. The goal is to provide insights into the factors affecting housing prices and to build predictive models using machine learning algorithms. This readme is a general overview of the project, with much more detail inside the ipynb file. 

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Installation](#installation)
- [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Model Building and Evaluation](#model-building-and-evaluation)
- [Conclusion and Future Work](#conclusion-and-future-work)

## Introduction
This project aims to provide an introductory case study using basic statistical knowledge and machine learning techniques to analyze and predict housing prices in California. The dataset, sourced from Kaggle, contains information about various features such as median income, house age, total rooms, and more.

## Dataset
The dataset used in this project was obtained from Kaggle: [California Housing Prices](https://www.kaggle.com/datasets/camnugent/california-housing-prices). It consists of the following columns:
- `longitude`: The longitude of the property.
- `latitude`: The latitude of the property.
- `housing_median_age`: The median age of the house.
- `total_rooms`: The total number of rooms in the house.
- `total_bedrooms`: The total number of bedrooms in the house.
- `population`: The population of the area.
- `households`: The number of households in the area.
- `median_income`: The median income of the household.
- `median_house_value`: The median house value.

## Installation
To run this project, you need to have Python installed on your system along with the following libraries:
- numpy
- pandas
- geopandas
- seaborn
- matplotlib
- plotly
- scikit-learn

You can install these dependencies using pip:
```sh
pip install numpy pandas geopandas seaborn matplotlib plotly scikit-learn
```

## Data Cleaning and Preprocessing
In this section, I performed various preprocessing steps to prepare the data for analysis. This included:
- handling missing values
- encoding categorical variables
- normalizing numerical features


## Exploratory Data Analysis
I did my best to include visualizations and analyses that accurately captured correlations between numerous features. Through geographical analysis of plotting median house values against latitude-longitude, I was able to grasp a relationship between proximity to the coast and house value. I further used the encoding of categorical variables to analyze the impact of different features on our target variable (the median house value). 

I performed outlier detection initially using boxplots. However I ended up using a more precise method using residuals, which are the differences between actual and predicted values. Standardized residuals were used to identify such outliers (defined as values exceeding three standard deviations from the mean). 

Next, correlation coefficients were examined to identify the features with the strongest relationship with the median house value. 


## Model Building and Evaluation
K-Nearest Neighbors (KNN) regression was chosen as a modeling approach because of its effectiveness in capturing local relationships across dense data points. It uses the idea homes in the same area will have similar prices, making it very suitable for predicting house values based on median income. 

To build the model, the dataset was first split into 60-40 training testing sets. Different k values were assessed to find the most optimal model fit. For each k value the MSE values were recorded, illustrating that as the K increased, the MSE decreased (up to k=144). 

I thus tested the model on the data. The predicted outcomes are varied, some being really close to the actual values and some being pretty far. To visualize the results, I plotted the points on a residual plot and was met with varied results. 

Furthermore, the R-squared value of 0.39 suggests that about 39% of the variance in the median house values could be explained by meidan income. Thus further analysis and additional variables may be able to enhance the models predictive performance. 


## Conclusion and Future Work
In summary, the project successfully laid out some of the groundwork for understanding the housing price dynamics in California, utilizing KNN regression as a predictive tool. However in the future there are several things that I would implement, especially in any type of machine learning project. 

To improve predictive capabilities, I would add feature engineering. This would allow for more accurate identification of relevant features that could possibly enhance the models performance. I would also implement cross-validation, as it may mitigate overfitting and provide a more clear picture of how a model such as this could perform on unseen data. Lastly, I would want to use more algorithms such as random forest or support vector regression to see their performance in comparison to KNN. Using hyperparameter tuning in this case would also help optimize the parameters of these models. 

All in all, I gained lots of valuable insights and practical skills related to data analysis, machine learning, and understanding model evaluation. As this was a introductive project to machine learning, I believe that I am continuously refining my ability to analyze data and use statistical knowledge to draw meaningful conclusions. 
