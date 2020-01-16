# Ames Housing Sale Price Prediction

To predict the Sale Price of a house using the AMES housing dataset

## Motivation of project

We would like to make observations and take a look at the features that are affecting the Sale Price of the house the most and to determine the features that are compulsary when collecting data.

## File list

code
- Project 2
    - includes the whole python code in jupyter notebook
dataset
- data description
    - Descriptions of all 81 data features
    - [Or you can download here](./dataset/data_description.xlsx)
- train
    - train data set provided
- test
    - test data set provided, where we predict our Sale Price on
- submission_linear
    - prediction of Sale Price based on the test dataset using Linear Regression after feature engineering
- submission_lasso
    - prediction of Sale Price based on lasso (score was not as good as submission_linear)

## EDA, Data Cleaning & Exploratory Visualizations
All null and zero values were taken care of for both train and test set, some features were removed as they contain more than 80% of null/zero values.   
Some columns were merged and then deleted as they will be representing the same features.   
Outliers were identified by plotting box plots, they were then removed.   
Collinear features were also dropped by looking at the heatmap.

## Pre-processing
All categorical variables were One-hot encoded before performing train/test split   

## Modeling
Model used on the baseline were - Linear Regression, Ridge, Lasso and Elastic Net   
RFE (Recursive Feature Elimination) method was used to remove features that might have caused issue in the model    
Model Selection   
- Lasso was the best performing model
- However Linear Regression after performing RFE is a more optimized model as it contains lesser features


## Conclusion and recommendation
- Required features when collecting data:
    - Overall Qual
    - Overall Cond
    - BsmtFin Type 1
    - Total Bsmt SF
    - Gr Liv Area
    - Kitchen Qual
    - Garage Area
    - Bedroom AbvGr
    - Age when Sold
    - Total Bath
    - MS SubClass
    - Neighborhood
    - House Style
    - Exterior 1st
    - Foundation
    - Garage Type
- Overall Qual has the strongest correlation of 0.805797
- Gr Liv Area hurts the value of the home most by 31222.46
- Home owners should improve on their Overall Qual, Overall Condition, Kitchen Qual to increase the value of their home
- Neighborhood not adviced to invest in:
    - College Creek
    - Gilbert
    - Northwest Ames
    - Sawyer West
    - Somerset
- It might generalize to cities that collected similar features as compared to our model
- In order to make it more universal, Neighborhood should not be included in the data we collect as it might restrict to that certain area of the country only.
