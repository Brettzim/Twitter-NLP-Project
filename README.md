# Twitter-NLP-Project
Phase 4 group project with Brett Zimmerman and Nate Walter

<img src=https://compote.slate.com/images/67c481b4-97ae-429f-9b08-c6918b5f6875.jpeg height="500" width="1000">





## Twitter Sentiment Analysis with NLP

## Table of Contents
* [Repository Structure](#Repository-Structure)
* [Overview](#Project-Overview)
* [Business Problem](#Business-Problem)
* [The Data](#The-Data)
* [Data Cleaning](#Data-Cleaning)
* [Analysis](#Analyis)
* [Conclusions](#Conclusion)



## Repository Structure
```
.
├── Experimentation-Notebook
│   └── Phase-4-EDA_bretts_edits.ipynb
├── README.md
├── Sentiment_Analysis_NLP_Model.ipynb
└── phase-4-dataset.csv
```
## Project Overview

This repository analyzes data in the form of Tweets about multiple brands and products to create a natural language processing classification model capable of predicting whether a Tweet is written with positive, neutral, or negative sentiment. Due to imbalance classes the goal of our model is to have a high F1 score, so we know that our predictions are meaningful. By using different machine learning techniques, we are capable of interpreting the customers’ feelings toward our clients’ products, making our model a useful tool for companies interested in allocating their resources to better serve their customers.


## Business Problem

We are the research and development team at Nebula Analytics, a consulting agency that advises companies on their public perception via Twitter. We are making a proposal to the executives of our company about how our Machine Learning model should be implemented to help the social media analysts at Nebula Analytics perform their job more efficiently and effectively.


## The Data

The dataset is sourced from CrowdFlower, via data.world (Links to an external site.) 
Over 9,000 Tweets which were positive, negative, or neither, were labeled systematically by individuals and uploaded to the dataset. The dataframe originally consisted of four columns. The first column simply being an identifier, assigning a numeric value to each record (or tweet). The second, and arguably most useful column was tweet_text, which encapsulated the raw tweets which were sent out referring to various products.  Next, was the emotion_in_tweet_directed_at column. The information in this column was solely used in the data pre-processing stage by our engineers as an aid for lending context to the other, more pertinent data in the dataset. It served to help in identifying what types of products to which people were referring, but that was the extent of its use in our project. 
The is_there_an_emotion_directed_at_a_brand_or_product column was the other linchpin in the model-making process, along with tweet_text. It served as the label column in which the customer’s sentiment – negative, positive or neutral, was interpreted and logged. 





## Data Cleaning

Traditional data cleaning consisted of checking for null values. As there was only a single row with a null Tweet, we removed it. We also renamed the columns to be more simple. The dataset had four target classes, “Positive, Negative, Neutral, Unsure”. We removed “Unsure” and cut it down to three targets. Finally, we label encoded the three target classes.

Text preprocessing is important for NLP tasks. Transforming text from raw sentences and phrases, into a form that the model can extract information from, consists of many steps and actions. 
The Preprocessing Steps taken are as follows:

Removing Twitter specific embedded text like mentions, Retweets, Links, Videos, and Hashtags
Tokenizing, which is turning strings into a list of words
Lower casing all letters in the dataset
Removing stop words that  do not add meaning to a sentence. Words “like the, and, at”
Removing punctuation and symbols
Stemming words to their root

<img src="https://user-images.githubusercontent.com/66656063/131164051-9ef33b25-2168-4f0b-ada7-57bc6563b712.png" height="200" width="250">
<img src="https://user-images.githubusercontent.com/66656063/131164434-62824df6-daf0-4cca-a279-a17eb646e89c.png" height="200" width="250">

## Analysis

We first created our baseline model with a dummy classifier. Due to our large target class imbalance, we set the dummy to use the stratified strategy. We wanted to use a tfidf vectorizer, and a multinomial naive bayes classifier. We created a pipeline using those two models and added a smote for our target class imbalance. We ran a grid search on that pipeline to find our best parameters. The hyperparameter tuning was used to maximize the F1 scores of the model. Once the best parameters were identified, our team entered them into a pipeline. From there we were able to keep the parameters constant while focusing solely on an individual parameter and adjusting it radically up or down with use of a function, based on experience and intuition. This method saved time by affording us the ability to bypass conducting a new grid search with every experimentation we ran on the parameter tuning at the micro-level. Once it was determined that we had the best hyper-parameter, the process was repeated on all applicable parameter settings.

<img src="https://user-images.githubusercontent.com/66656063/131163650-a67696c8-2e6e-4eeb-a4e0-5fc6116ed360.png" height="400" width="500">



## Conclusions

In conclusion we tried a few different kinds of models. Due to our industry knowledge we were most interested in the Multi-Nomial Niave Bayes model. Our Iterative 
process and hyper-parameter tuning brought us to our final model, that is able to classify text instantaneously. 

