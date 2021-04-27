# Housing_Price_Prediction: Project Overview

* Created a tool that estimates the sale price of a house (RMSE ~ $21K) to help homeowners better understand the value of their homes.
* Dataset is from the AMES Housing Dataset [here](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview)
* Did some Exploratory Data Analysis (EDA) to better understand the dataset.
* Engineered features to removed outliers, deal with categorical and missing data.
* Optimized Elastic Net using GridsearchCV for the best model.

## Dataset Features 
[Feature Explaination](https://github.com/faithfulalabi/Housing_Price_Prediction/blob/main/Ames_Housing_Feature_Description.txt)


## Exploratory Data Analysis 

The plots below show the correlation between all features and the distribution of the sales price.
![alt text](https://github.com/faithfulalabi/Housing_Price_Prediction/blob/main/correlation_map.png?raw=true)
![alt text](https://github.com/faithfulalabi/Housing_Price_Prediction/blob/main/sales_price_distribution.png?raw=true)

## Data Cleaning
After getting the dataset, I cleaned it up, dealt with missing data, and dropped outliers so our data can be acceptable for our model. I made the following changes:

* Dropped outlier whose General Living Area was greater than 4000 but the sales price was below $400,000
* Dropped the personal ID number column
* Filled all missing Basement integer values with 0 and Basement String values with None
* Dropped the Electrical and Garage Cars columns 
* Filled all Mas Vnr Type and Area with None and 0's
* Filled missing Garage string information with 0's
* Filled missing Garage year built information with 0's
* Dropped Pool QC, Misc Feature, Alley and Fence columns
* Filled missing Fireplace Quality with None
* Transformed missing Lot Frontage data using the average neigeborhood Lot Frontage 
* Seperated out the string and integers into 2 seperate datasets 
* Transformed String dataset into a categorical data structure 
* Combined both datasets back together as the final dataset

## Model Building

First I transformed the categorical strings into dummy variables. I then split the data into train and test sets with a test size of 10%.

I scaled the data and used ElaticNet with GridSearchCV as my model because of the sparse data from the many categorical variables.

I chose the RMSE because it is easy to interpret 

## Model Performance

* ElasticNet : RMSE = 20,486.62
