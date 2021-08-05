# Banking

## Introduction
This project is divided into two parts; EDA and ML

### Exploratory Data Analysis
This portion aims to garner insights from transaction data, through data manipulation, descriptive statistics and visual exploration. The dataset contained in this project was provided by Australia and New Zealand Banking Group for a virtual internship program they offer. The data is a synthensized representation of transactions over a three month period. I hope you enjoy following this analysis as much as i enjoyed putting it together.

### Visual inspection and Cleaning
To begin the exploration, we should start by loading all the required libraries. The package "tidyverse" contains a host of libraries with functionalities such as data visualization with ggplot2, data manipulation with dplyr,reading excel files with readxl and working with dates and time with lubridate that will be useful for our journey. Next we read-in the data and observe its structure. We should also check the first and last few values to get a feel for the dataset.

### Machine Learning
This purpose of this portion is to predict customer salaries based on other features in a given dataset. The data was provided by Austrialian and New Zealand Banking group, and is a synthesized representation of actual transaction information. To achieve this we will use to different models the first being ***multiple regression*** and the other being ***A regression tree model***; which is a decision tree that can produce continous numerical values.

### Feature Engineering
Next we select or generate possible variables from our data set, they will be the "features" for our model. We can start by aggregating the total salary for each customer and their total spending. We can also find less salient correlations with the help of scatterplots.

### **Modelling**

#### Modelling with Cross Validation Plan

Creating a kfold cross validation plan is way to validate the modelling processing by testing the models out of sample performance. This can be done with the help of the *kWayCrossValidation* function from the vtreat package. This function splits the data into **K** pairs of training and testing data.

##Model Results
On the cross-validation test the model had a ***Root Mean Square Error*** of **5772.106 AUD** and a ***Coefficient of Determination*** of **0.2598248**. The root mean square error is a measure of the models accuracy and its in the same unit as the response variable, it can be thought of as the standard error of the models output while the coefficient of determination(R-squared) is a measure of how well the model explains the variance in data, values closer to 1 indicate that model explains variablity in the data well. However, the model performed better on the split and train set and had a lower R-square value, indicating better fit.

###  Predicting With Decision Trees

Unlike the linear model, decision trees can capture non-linear relationships, simply, this means the model can be trained to learn patterns that a linear model couldn't. We will construct this model using a grid search method. This simply means we will construct trees with different *hyperparameters*(***presets***) and choose the one that has to lowest error values.

To accomplish we will follow the following steps:
1. Split the data into three parts: The training set(70%), the validation set(15%), the test set(10%).
2. Create a list of possible model presets (Hyperparameters).
3. Create a set of models with each preset
4. Compute the root mean square error of each model against the validation set.
5. Select model with the least error.
6. Make predictions on the test set.

## Recommendations and Conclusions

* Both the linear model and the decision tree produce relatively high error value
* The R-squared value of the linear model indicated that the model cannot explain the variation in our data.
* A more advanced model with more information such as *education*  and *occupation* can produce more accurate predictions. 
