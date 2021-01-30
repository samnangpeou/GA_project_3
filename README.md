# Reddit Classification Modeling Project


## Problem Statement

Using data between two subreddits on Reddit, would a Multinomial Naive Bayes model perform better than a Support Vector Machines model to predict which post belonged to the correct subreddit?

## Goal

Scrape data with the PushShift API off of two subreddits of your choice and build a classification model that can predict where a document came from.

## DATA

[Marvel Scraped Data](https://git.generalassemb.ly/sampeou/project_3/blob/master/data/marvel_reddit.csv "Marvel Scraped Data")
[Marvel Studios Scraped Data](https://git.generalassemb.ly/sampeou/project_3/blob/master/data/marvelstudios_reddit.csv "Marvel Studios Scraped Data")


## Column Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|title|object|marvel/marvelstudios|Headline of the post from the document.|
|selftext|object|marvel/marvelstudios|The body of the post.|
|subreddit|object|marvel/marvelstudios|From which subreddit the document came from.|
|created_utc|int|marvel/marvelstudios|Timestamp of post creation in UTC-Code|
|author|object|marvel/marvelstudios|User that posted the document.|
|num_comments|object|marvel/marvelstudios|Number of comments the post received.|
|score|int|marvel/marvelstudios|How many likes on the post.|
|is_self|boolean|marvel/marvelstudios|Whether posted by the user.|
|timestamp|DateTime|marvel/marvelstudios|The date post was created.|


## Research:

After scraping from Reddit in 7 day windows for 10 years, I was able to scrape 30,000 documents from Reddit evenly split between the two subreddits. Actual data cleaning was really straight forward since this is an NLP model and we are only extracting words. After dropping the nulls and removing posts that had been removed by reddit, there was only NLP EDA left. From there, using the hyper parameters and filling in custom stop words helped trimmed the word to lesser used words that are prodominant in both Reddits that weren't training the model to find the correct distinction.


## Conclusion and Recommendations:

Between the two models, TfdifVectorizer ran with a Logistic Regression improves the accuracy scores on test data with a slight bit of overfitting on train data. The CountVectorizer ran with Naive Bayes runs very similarly across test and training data but is less accurate. TfdifVectorizer ran with Logistic Regression would be the model of choice with significantly low runtime.