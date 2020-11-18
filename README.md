# Recommendation System - BTP

## Sentiment Analysis

### Description

- **Dataset** : [Amazon fine food reviews](https://www.kaggle.com/snap/amazon-fine-food-reviews)

- This dataset consists of reviews of fine foods from amazon. The data span a period of more than 10 years, including all ~500,000 reviews up to October 2012. Reviews include product and user information, ratings, and a plain text review. It also includes reviews from all other Amazon categories.

- Due to logistics issues and time constraints we have used only first 3k rows as our training dataset.

## Problem Statement

- Given a review, determine whether the review is positive (Rating of >= 3) or negative (rating of 1 or 2).

## Text Preprocessing : 

- Replace regex with ' ' apart from english alphabets
- Perform stemming on the words to retain the original words

## Word Embeddings : 

- Store all the words in the corpus in a single list
- Perform simple hashing technique and select top 3000 words
- Transform sentences of words to sequence of rank number of words

## Deep Learning Model

### Model 1 : 

- Perform padding of sequences
- LSTM with single hidden dense layer
- Use Keras.Embedding layer for embeddings of similar and disimilar words in n-dimensions.
- **Performance** : Accuracy - 83.67%
- **Example:**
- Sentence :"Not as Advertised"
- Output : "Positive review with 55.77 % Accuracy"
- The model doesn't perform quite well on unseen data. This may be due to overfitting, less training samples, poor text preprocessing etc. factors may contribute to 
such poor performance. We tried to improve the model in the next application.

### Model 2:

- Added multiple LSTM layers along with dropout with probability 0.25 and 0.5 respectively.
- Remaining model remained the same as above.
- **performance** : Accuracy : 84.42%
-**Example** - 
- Sentence :"Not as Advertised"
- Output : Negative review with 55.76 % Accuracy
- The model performed quite better than the previous with predicting actual sentiment although with quite less accuracy. 
