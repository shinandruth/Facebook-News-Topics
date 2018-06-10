#### Shin Lee, Julie Kim, Josh Koo
# <a href="https://github.com/shinandruth/Facebook-News-Topics/blob/master/Facebook%20News%20Topics%20Final.pdf">PDF Report</a>

**Title**: Facebook News Topics

**Contact**: joshuakoo2019@u.northwestern.edu

**Course**: Machine Learning: EECS 349 at Northwestern University

## Abstract
We wanted to apply machine learning techniques to classify Facebook News topics and give news recommendation for users who are interested in certain topics. For example, if Sam is active on Facebook and he likes to read news about cars, we wanted our machine learning techniques to classify news topics related to cars into a category and give recommendations accordingly. Using programming and analytical methods, we wrote scripts to scrape data from Facebook Trending News, conducted pre-processing on our collected data, and analyzed the data with Weka.  

## Introduction
### *Motivation*
The project tackles the broad task of analyzing news articles and determining whether or not the topic of the article is based on tech companies. To be specific, our project deals with analyzing news articles under the Facebook “Trending” news column. This task is important because of how relevant tech-related discussion is in recent times and because of how widespread the usage of Facebook is, which allows for easy news distribution. It is crucial for social media news platforms to give relevant news topics. Ultimately our project aims to allow easy distribution of important tech-related news articles relevant to certain users on Facebook.   

## Methodology
### Data

To collect our data, we wrote scraping scripts in Python 3.6.4 and Selenium, a user interface (UI) automation tool that automates UI testing. Our raw data consisted of roughly 50,000 data each with the 7 attributes listed below:
*	Type: The topic (top trends, politics, science and technology, sports, or entertainment)
*	Title: Title of news trend
*	Description: The short description located under the title 
*	Trend Link: The link that redirects the user when the trend is clicked. The link redirects the user to a compilation of news on a Facebook page. 
*	Rank: Where the trend is ranked in the trending list
*	Scrape ID: An integer to keep track of which round of scraping the data is collected from
*	Timestamp: The exact time and day the data was collected (YY-MM-DD HH-MM-SS)

Type was used to distinguish the different topics during the analysis. The analysis investigated the top trends for all five topics in addition to the top trends for each of the topics. Title and description were collected for detail for each news trend. The trend link was used to uniquely identify each trend. Rank was collected to discover where in the list certain new trends were placed and whether they moved up or down the list. Scrape ID was used with trend link to uniquely identify trends for the whole dataset. Timestamp was used to keep track of the time and date the data was collected, which was critical when analyzing the trend behavior at different days of the week.

We needed to preprocess our data in order to address our problem, so we removed duplicate news articles by filtering by description and went in by hand to add a classification attribute based on whether the article is related to our chosen topic or not. There was a very small percentage of articles that were relevant to our topic. After this preprocessing, we used Weka to analyze our data with different classifiers and we recorded accuracy and precision as well as whether the classification was "yes" or "no" 

We tried several learners via Weka, the exhaustive list being: Naive Bayes, Logistic Regression, IBk, J48, Simple Logistic, and Bayes Net.

## Results

| Classifier | Accuracy | Precision (Yes) | Recall (Yes) |
| --- | --- | --- | ---|
| ZeroR | 95.2747 | N/A | 0 |
| Naive Bayes | 93.956 | 40.9 | 62.8 |
| Logistic | 96.4835 | 64.9 | 55.8 |
| IBk | 96.2637 | 65.5 | 44.2 |
| J48 | 95.2746  | N/A | 0 |
| SimpleLogistic | 96.7033 | 81.0 | 39.5 |
| BayesNet | 90.7692 | 31.9 | 83.7 |

The figure above depicts the results that various machine learners achieve on our data. Although we recorded accuracy, precision, and recall, the above figure reports accuracy and precision, which were the values we focused on. we believed precision and recall were the most important, more so thanaccuracy because a large percentage of our data is not related to tech companies. This is expected as tech companies is a very specific topic. As a result, since most examples are not about tech companies, when the classifiers we selected classify our data, it will achieve high accuracy, even if the classifier is not the most optimal relative to other classifiers.

Our solution, in terms of accuracy, performed well across the board with different machine learners. This is not very informative, however, as our data shows that most news articles will not be about tech companies because there is such a large variety of topics that the media covers. As a result, machine learners will get similar accuracies by classifying most articles as not relevant to tech companies. Therefore we judged performance by focusing on precision. The machine learners with the best precision were Simple Logistic and IBk, ran by Weka. As far as the features go, by looking at an unpruned decision tree, we found that title was the most important. As a key finding, we observed that the classifications primarily work with key words in the article titles, therefore news articles regarding large tech companies often have the name of the companies in the title.


## Full Report


### Sources
https://www.recode.net/2017/9/7/16270900/social-media-news-americans-facebook-twitter

Website: https://shinandruth.github.io/Facebook-News-Topics/




