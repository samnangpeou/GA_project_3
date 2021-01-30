# Reddit Classification Modeling Project


## Problem Statement

Using data between two subreddits on Reddit, would a Multinomial Naive Bayes model perform better than a Support Vector Machines model to predict which post belonged to the correct subreddit?

## Goal

Scrape data with the PushShift API off of two subreddits of your choice and build a classification model that can predict where a document came from.

## DATA






## Column Dictionary







## Research:

After scraping from Reddit in 7 day windows for 10 years, I was able to scrape 30,000 documents from Reddit evenly split between the two subreddits. Actual data cleaning was really straight forward since this is an NLP model and we are only extracting words. After dropping the nulls and removing posts that had been removed by reddit, there was only NLP EDA left. From there, using the hyper parameters and filling in custom stop words helped trimmed the word to lesser used words that are prodominant in both Reddits that weren't training the model to find the correct distinction.


## Conclusion and Recommendations:

Currently a more tuned SVC model is still running almost 18 hours after starting it! If what you were looking for was a quick training model that you can tune based on a probability formula within a short deadline, the Naive Bayes model is your model. If you have hours, and I mean hours, to spare then Support Vector is the better performing model of the two.