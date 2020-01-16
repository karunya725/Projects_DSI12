# Regression with the Ames Housing Data

This project uses the [Ames housing data](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) from Kaggle.

## Objectives of project

The objective of this project is to create a regression model based on the Ames Housing Dataset and to predict the price of a house at sale.

## Problem Statement 

**Optimising survey features in house pricing survey** - My main aim is to reduce the number of features being surveryed and thus making the survey easier for respondents and also reducing the probability of getting missing responses 

## Workflow 

Here lies the step I undertook to analyse my data to make predctions on the sale price of a house 

### 1. Data Cleaning 

Data cleaning comprised of identifying and replacing null values and certain zero values with appropriate values 
When justified, certain rows were dropped so to ensure uniformity of data

  After cleaning, data had a total of 81 columns and 2041 rows

### 2. Exploratory Data Analysis (EDA) and Feature Engineering

1. Data was first split into three categories 
    - Continuous - Eg. Lot Area, Mas Vnr Area
    - Ordinal - Eg. Overall Qual, Kitchen Qual
    - Nominal - Yr Sold, Nerighborhood
 
    I did not have a separate category for discrete values as discrete values could either fit into the ordinal category or the nominal category. As such, I proceeded with these 3 categories. 
    
    Ordinal data were ensured to be numerical. After which, the 3 categories were differentiated by their data types 
    - Datatype float was assigned to continuous as it holds a range of values 
    - Datatype string/ object was assigned to nominal as it would be easier for splitting and one hot encoding 
    - Datatype integer was assignmed to ordinal as it contains a discrete numerical values
    
2. Transforming data - adding columns 
    
    2 new columns were added so as to reduce the numebr of nominal features. Also, these columns simplified the interpretation of the previous columns. 

3. Heatmap and Histogram plotting 

    For continuous variables, heatmap and correlation coefficient was used to determine which variables to keep. This is because continuous variables are purely numerical and as such, a heatmap is enough to show how correlated variables are with each other and with the target. 
    
    For ordinal variables, both heatmap correlation coefficient and histogram was used to determine which variables to keep and which to discard. 
    The histogram plots helped in visualising which variables were skewed towards a certain variable sub category. Such variables will only reduce the variance of our model and make it more biased. As such, skewed variables were removed. 
    Furthermore, given that ordinal variables are numerical, heatmap and correlation coefficients were also used to feature engineer variables to keep and to discard.
    
    For nominal variables, histogram was used to determine which variables to keep based on the skewness of the variable sub categories

### 3. Initial Model 

The above feature engineered variables were fit into linear regression, ridge regression, lasso regression and elastic net regression model. There were a total of 176 variables including one hot encoded nominal variables, Here, lasso proved to be the best with the highest R squared score. 

### 4. Final Model

To create the final model, Lasso regression was used to extract more optimal variables from the previously feature engineered variables. Out of 176 variables, our model picked 92 variables and elimiated 84. From this list, the top 24 were picked and using these variables, linear regression, ridge regression, lasso regression and elastic net regression modelling was done.
    
This time, the linear regression model gave the highest R squared score after cross validation, thus also proving that our model is neither overfitted nor underfitted. It was just right. 
     
This model was used to run our test dataset which gaave our predicted Sale Price. Uploading these predicted values to Kaggle gave a score of 32K
