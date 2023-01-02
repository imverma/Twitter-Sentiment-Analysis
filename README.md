# Twitter Sentiment Analysis:

# Usecase:
This is an entity-level sentiment analysis dataset of twitter. Given a message and an entity, the task is to judge the sentiment of the message about the entity. There are three classes in this dataset: Positive, Negative, Neutral and Irrelevant.

# Tech Stack:
* Category: NLP, Multiclass Classification problem
* Tech Stack: Python, Regular expression, Word cloud, NLTK, TF-IDF, Bag of Words, Pandas, Matplotlib, Sklearn

# Medium Blog:
https://parisrohan.medium.com/twitter-sentiment-analysis-and-classification-7060d4444a27

# Files:
* EDA_TextCleaning.ipynb - EDA and text cleaning code
* Model_building.ipynb - Model building code

# Workflow:

## 1. Data Collection:
* Twitter sentiment analysis dataset from Kaggle has been used to build a multiclass classification model. The dataset can be found from the following link:-
https://www.kaggle.com/datasets/jp797498e/twitter-entity-sentiment-analysis
* The dataset contains 74682 rows and 4 columns
* Distribution of target feature is as below
![image](https://user-images.githubusercontent.com/49038495/180604148-a2c9f30f-8675-44dd-9558-5ed56e47eb90.png)

## 2. EDA:
* The dataset columns have been renamed to {0:'Tweet_ID',1:'Topic',2:'Sentiment',3:'Tweet'} to get a better sense of the data.
* 0.9% of the data has been dropped as it contains null values
![image](https://user-images.githubusercontent.com/49038495/180604286-710aba29-7787-4794-9c8d-f76db0e101d5.png)
* On an average each tweet contains 23 tokens and there are some tweets with extreme outliers
![image](https://user-images.githubusercontent.com/49038495/180604360-79800e2a-1299-4226-a485-5b9b7625bc89.png)

## 3. Data preprocessing:
* Following actions are performed on the 'Tweet' feature to extract important information.
* Remove user mentions
* Remove hashtags
* Remove contractions
* Remove urls
* Remove special characters
* Convert tweets into lowercase
* Remove stopwords
* Normalize text by converting words into lemma
* Generate word clouds for each sentiment on the cleaned tweets
![image](https://user-images.githubusercontent.com/49038495/180649932-fd958ba5-8e55-4702-902a-ef67884e9087.png)
* Perform one-hot encoding on the 'Topic' feature
* Drop features like 'Tweet_ID','Tweet','Topic' as they are no longer required

## 4. Model Building
* TF-IDF vectorizer is used to create bag of words
* Results of Multinomial Naive Bayes model:
![image](https://user-images.githubusercontent.com/49038495/180604622-5af54079-3112-45cc-8143-ea5c93e232b1.png)
* Results of Logistic Regression model:
![image](https://user-images.githubusercontent.com/49038495/180604643-78b1f3bb-cf4c-4804-a824-c706d376caae.png)
* Results of Decision Tree Classifier model:
![image](https://user-images.githubusercontent.com/49038495/180604662-7f819b8d-18d4-4146-aac9-72964487eb53.png)
* Results of Random Forest Classifier model:
![image](https://user-images.githubusercontent.com/49038495/180604683-09ffc6b2-f4e1-4fc4-b418-ce95c5fd3fa7.png)

