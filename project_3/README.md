# Project 3: Web APIs & NLP

---

## Problem Statement

Our Social Media department has informed the Data Science department that users of our newly created Beauty Insider Community Forum have been posting in the wrong group. 

The makeup and perfumes posts are posted in the General Discussion page and we need to find a way to classify their posts into Makeup and Perfumes categories for better analysis of their needs and interests.

The goal of this project will be to use Reddit posts from r/Makeup and r/Perfumes to create a text classifier model that can classify posts into the 2 categories with accuracy more than 50% (baseline accuracy). We can then use the model to classify the posts in our forum. Through this project, we will also find out the trending words in each subreddit to guide our marketing department.

---

## Data Collection

We used Pushshift's API to scrape 5000 most recent posts from each of the two subreddits.

We kept columns ‘Subreddit’, ‘Title’ and ‘Selftext’ which contain the category and text required for our EDA and modelling.

---

## Data Cleaning 

We have combined the 'Title' and 'Selftext' text and removed posts containing words like '[removed]' and '[deleted]' and NaN. Duplicated posts were also removed. 

---

## Preprocessing

We removed stop words, tokenized and lemmatized the text. Through the EDA process, we identified some words that have no relevance to our analysis and added them to our list of stop words.

---

## Modelling
We focused on 3 models, namely Bernoulli Naive Bayes, Logistic Regression and Random Forest Classifier while using Count vectorizer and TF-IDF vectorizer. We used GridSearchCV to determine the best parameters for each model.

Logistic regression model with TF-IDF Vectorizer has the highest test accuracy of 0.94904. It scores well (>0.9) for all other scoring metrics so we can adopt this model for predicting the subreddit which the posts belong to.

---

## Limitations and Future Plans
We see some difference between the train and test scores and we can train more data to prevent overfitting of our model.

To further improve the accuracy of our model, we would want to try including more stop words to make our analysis more relevant. We can also try more advanced modelling techniques like XGBoost, CatBoost and do further tuning of hyperparameters to improve the performance of our model. We can see if combining different models can lead to improvements to our model's performance metrics.

Further sentiment analysis can be done on the posts to understand brand and product sentiments for better targetted marketing efforts.

---

## Conclusions/Recommendations
After comparing with the other models, we have concluded that the Logistic Regression model with TF-IDF Vectorizer has the highest test accuracy of 0.94904. 

We are confident that this model can be deployed for the classification of our forum's posts into either Makeup or Perfumes categories to a high accuracy level.

We have also identified some words and bigrams that appear most frequently in Makeup and Perfumes subreddits that consists of brands, products and product features that can be useful for analysing and understanding customers' preferences.
