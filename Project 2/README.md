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
     
This model was used to run our test dataset which gave our predicted Sale Price. Uploading these predicted values to Kaggle gave a score of 32K

### 5. Refining model

The variables extracted from Lasso previously went through feature engineering process again. This time with the goal of reducing the number of nominal variables by converting them into ordinal variables. Box plot were plotted to see if median price changes for various sub categories of variables. From there, if there is a correlation between price increase/decrease and the sub categories, those variables were converted to ordinal undergoing steps 1 to 5 again for these few variables. 

This gave a slighly better model. This model was used to run our test dataset which gave our predicted Sale Price. Uploading these predicted values to Kaggle gave a score of 31.6K

## Business Recommendation

After modelling and refining, I can conclude that the main factors that affect Sale Price of Ames houses are the Subclass of the houses, the Neighborhood, the type of masonry veneer, the number of bedrooms above ground, the number of cars the garage is able to accomodate and the type of garage and the number of fireplaces. The quantifiable factors that affect Sale Price are the area of the garage, the square foot of the ground floor, the area of the masonry veneer and the total square foot of the basement. Lastly, in terms of the quality of the houses, the basement quality,  the external quality, the kitchen quaity and the overall quality affect the Sale Price as well. 

When collecting data for analysis, real estate personel should focus on these factors and quality condition mainly. Also the real estate personel can use these feature selection to take note of what needs to be upgraded before putting the house up for sale 

As for future recommendation, it might be useful to take note of amneties near the houses and the proximity of the houses to the schools and business districts as Ames is mainly a white collar town and populated by college students. Also looking at the potential for rental will be usefil. This is because there will be high demand rental here or/ and demand for small houses (due to many singles relocating there). Furthermore, House prices might increase as commute to work decreas given that many residents' main mode of transport is public transport. 

### External readings 
https://www.realtor.com/realestateandhomes-search/Ames_IA/housing-market 
https://www.neighborhoodscout.com/ia/ames
