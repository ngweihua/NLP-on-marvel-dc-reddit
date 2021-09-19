# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

# Problem Statement
Our client is a game creator that specialised in mobile application game and their recent game creation involved heros from DC cinematics and Marvel studios.

As a data scientist from a consultancy firm, our task is to build a good classification model based on reddit posts from marvel and dc subbredits to help them in their marketing campaign. Client will use the model to predict whether the internet user is a marvel or dc fan todisplay appropriate advertisement to entice the users to download the game in order to boost the game popularity. The model will also help client to have a better understanding on the most discussed superheros to be placed of a higher priority or to be included in the game.

The dataset consist of the latest 1000 posts from each of the two subreddit.The primary stakeholders will be the client to boost their game popularity and the secondary stakeholders will be the internet user and game player. 

The following is the general workflow for this project: 
+ Data Collection
+ Exploratory data analysis (EDA)
+ Data cleaning by removing special characters, lemmatizing/stemming and word removal
+ Pre-processing and feature engineering
+ Modelling and evaluation
+ Conclusion and recommendation

The model will then be evaluated by two metrics - model test accuracy and ROC AUC score. The objective of the model is to get a high accuracy score and ROC AUC score.

# Executive Summary
## Contents:
1. [Data collection via API](#Data-Collection-via-API)
2. [Exploratory Data Analysis](#Exploratory-Data-Analysis)
3. [Data Cleaning and Pre-processing text data](#Data-Cleaning-and-Pre-processing-Text-data)
4. [Modelling](#Modelling-and-GridSearch)
5. [Evaluation](#Evaluation-of-model)
6. [Conclusion and Recommendation](#Conclusion-and-Recommendation)
7. [Limitation](#Limitation)

# Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|object|df_marvel,df_dc|subreddit group: r/DC_Cinematic , r/marvelstudios|
|title|object|df_marvel,df_dc|subreddit title|
|selftext|object|df_marvel,df_dc|subreddit post|
|created_utc|object|df_marvel,df_dc|date and time of post|
|id|object|df_marvel,df_dc|subreddit userid|

# Model Evaluation
|Parameters|Results|
|---|---|
|Vectorizer|TF-IDF|
|Model|Logistic Regression|
|Accuracy score|0.942|
|ROC_AUC score|0.942|
|Misclassification rate|0.061|

# Conclusion and Recommedations
The classification model to differentiate between Marvel and DC fans can be modelled with high accuracy by using Tf-IDF Vectorizer with Logistic Regression Model. 

The following are the summary of steps that was taken to derive at the final model:
+ Data Collection via PushshiftAPI
    - Make sure that response status code is 200 which means the process is successful
+ Exploratory data analysis (EDA)
+ Data Cleaning and Pre-processing text data
    - Regular expression to clean data
    - Tokenizing
    - Lemmatizing
    - Stop word removal
+ Modeling
    - Choice of Vectorizer : CountVectorizer and TF-IDF Vectorizer
    - Choice of Classification Model: 
        - Random Forest Classifier
        - Logistic Regression 
        - Multinomial Naives Bayes 
    - GridSearch for best paramter and its hyperparameter tuning
+ Evaluation 
    - Confusion Matrix
    - R2 score and cross validation score
    - Accuracy score
    
In conclusion, the accuracy score is about 95% and roc auc score of the model is about 99%. With the classification model, it can be used to target the right audience group to display appropriate advertisement to entice the users to download the game application in order to boost the game popularity.

The top 5 from each team that are recommended to be included in the game:
- Spiderman
- Loki
- Dr Strange
- Black Widow
- Captain America
- Wonder woman
- Superman
- Black adam
- Bat man
- Green Lantern

The benefit of the model: 
1. Help our client to achieve a successful marketing campaign 
2. Consumers get to play their favourite character in the game 

# Limitations
The model limited to Reddit data and data was limited to the most recent 1000 posts per subreddit.
We suggest to collect more sample data from other social media such as Twitter and for a longer period of time ideally more than 3 months to further improve the model. 
Besides that, with the upcoming tv series and movies, it is recommended to retrain the model on monthly basis.
