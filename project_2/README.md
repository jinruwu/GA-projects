# Project 2: Ames Housing Data and Kaggle Challenge

## Problem statement
I am a real estate agent whose role is to advise my clients how much their house is valued. A house is a huge asset for most families and I will assist to provide data insights and predictions to help them maximise the amount of financial gains through the sale of their houses.

I will be using regression models on the Ames housing dataset to predict the sale price of my clients' houses. Thereafter I will also advise them on the features of the houses that can influence the sale price.


## Dataset

The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses. It is used by the Ames Assessor's Office to compute assessed vales for individual residential properties sold in Ames, IA from 2006 to 2010. More information about this data, including a data dictionary, can be found here:

http://jse.amstat.org/v19n3/decock/DataDocumentation.txt


## Exploratory Data Analysis (EDA)

After data cleaning, we checked for correlation between the different feature pairs and also between features and sale price. We explored the top few numerical features with scatter plot diagrams and explored some of the categorical features with box plots.

The main findings of the EDA are as follows:

1. The median sale price of houses in Ames is around 150000 to 200000 dollars. 

2. Variables related to quality of the home and total living area have very strong correlation with sale price.

3. Total number of bathrooms and year built are also some factors with fairly strong correlation with sale price.


## Modeling Process

We have used 3 models on the data set. First, it was the baseline Linear Regression model, then Lasso Regression model and Ridge Regression model. 
All three models have similar results but Ridge regression has slightly higher R2 and has slightly lower RMSE. Hence we will use this model for predicting the Test dataset. For all 3 models, the RMSE test results are higher than train results hence it may mean that there is overfitting of the model. 


## Conclusion
We have chosen the Ridge regression model as it has slightly higher R2 and has slightly lower RMSE as compared to the 2 other models. For the Ridge model, 89.8% of the variability in sale price is explained by the features in our model. The Ridge model was off by about $25,448 in its predictions.

We can further improve the model by rerunning the model after dropping variables with Lasso Regression coefficients close to zero.

The most important features that affect the sale price are overall quality of the houses and total area of the house. We suggest our clients to maximise their total property area to include basement, garage, above grade living area etc. They can also do some renovation to improve the overall quality of the house and do regular maintenance to keep the house in a tip top condition.