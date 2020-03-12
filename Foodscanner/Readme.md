## Executive Summary

The aim of foodScanner is to be a one-stop platform where all your dining options are at your fingertips. Its 3 functions incluse: 
1. **Consolidate** your favorite eateries from every platform out thereto give you the ease of access to all the available and OPEN places
2. **Notify** you of inhouse and apps related discounts and promotions so that you can compare across platforms easily without having to subscribe to multiple sites
3. **Recommend** you eateries based on your preference when you search for a particular type of place to dine 

#### Objective of the project

To recommend users eateries based on their preference 

#### Problem Statement

To create a recommender system to recommend a user personalised places to dine based on their dining history 

#### Workflow

Here lies the steps undertaken in this project

1.	ETL 

  Yelp data was used for this recommender. 
  -  Exact data used: 'yelp_academic_dataset_business.json' and 'yelp_academic_dataset_review.json'
  -  YELP Business Json file contains all the details of all the businesses in USA and in Canada and YELP Reviews Json file contains all the details of all the reviews given to businesses. 

  First the scope of the project was determined via EDA on the cities, states and categories. From there, Toronto was selected to focus on. 
  Following which, Business data and Review data were combined and only rows from users who have given more than 75 reviews were kept. Unnecessary columns were dropped and data types were changed to be uniform 

2.	EDA and Deature Engineering  

  Numerical id were given to businesses and users to easily identify them as business_id and user_id in dataframe was in hash format
  
  Categories column was exploded and only food related categories values were kept and separted into 'cuisine', 'food' and 'restaurant' columns 
  
  Attributes column was expanded to create numerical attributes column and new ‘attri’ column was created with only the attributes the business contains
  
  **User-Attributes**
    - User-attributes extracted to profile users based on the features they look for in a dining venue 
    This serves as an alternate means of collaborative filtering 

  **Business-Categories**
    - Categories to be fit into a matrix and similar eateries to be filtered using a similarity means (cosine similarity)
    This would be a content based filtering 

3.	Modelling 

  3 types of clustering was carried out to profile users based on the attributes that they prefer
  - K-means Clustering
  - DBSCAN
  - Hierarchical Clustering 
  
  Clusters from Hierarchical Clustering was chosen to be used to recommend

4. Recommending 
   
   3 step recommender 
   1. For a particular user x, find the attribute cluster user x is in
   2. Find all the eateries suited to user x based on cluster
      - Attributes filtering
   3. Use content based filtering to find similar eateries for user x
      - Categories filtering

#### Conclusion and further recommendation 

-	Further recommendation: For deployment, the aim is to take in user input and to filter results from recommendation. 

