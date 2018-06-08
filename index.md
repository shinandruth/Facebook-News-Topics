# Our website: https://shinandruth.github.io/Facebook-News-Topics/

#### Shin Lee, Julie Kim, Josh Koo

**Title**: Facebook News Topics

**Contact**: joshuakoo2017@u.northwestern.edu

**Course**: Machine Learning: EECS 349 at Northwestern University

## Abstract
We wanted to apply machine learning techniques to classify Facebook News topics and give news recommendation for users who are interested in certain topics. For example, if Sam is activate on Facebook and he likes to read news about cars, we wanted our machine learning techniques to classify news topics related to cars into a category and give recommendations accordingly. Using programming and analytical methods, we wrote scripts to scrape data from Facebook Trending News, conducted pre-processing on our collected data, and analyze the data with Weka.  

## Introduction
### *Motivation*
The project tackles the broad task of analyzing news articles and determining whether or not the topic of the article is based on tech companies. To be specific, our project deals with analyzing news articles under the Facebook “Trending” news column. From that analysis, we can extrapolate information to classify other news articles as articles about certain tech companies via the usage of a machine learner. This task is important because of how relevant tech-related discussion is in recent times and because of how wide-spread the usage of Facebook is. In fact, according to a study by Pew Research Center, 67% of Americans get their news from social media. Additionally, Facebook has recently been a topic of hot discussion regarding fake news and algorithms that present bias posts. Therefore we believe it is crucial for social media news platforms to give relevant news topics and due to the prevalence of the tech scene, we decided to pursue those avenues of media. Ultimately our project aims to allow easy distribution of important tech-related news articles relevant to certain users on Facebook.   

## Methodology
### Data

The scraping scripts were written in Python 3.6.4 and Selenium, a user interface (UI) automation tool that automates UI testing. Selenium was selected because it can simulate a real human user and trick the web browsers. It can distribute and scale scripts over many different environments and can create robust, regression automation tests. Regression automation test’s purpose is to catch bugs that were accidently introduced and make sure previous bugs stay dead. Initially, we collected data using Mozilla Firefox because Selenium IDE, a Firefox add-on, was only available on Firefox and we had experience with Selenium IDE. Since we did not use Selenium IDE for this experiment but instead we used Selenium WebDriver which is available on multiple browsers, we were not restricted to one browser.  After running into issues with Firefox when running the scripts on the AWS cloud server, we changed from Firefox to Google Chrome. Another reason we changed from Firefox to Chrome was because Chrome is the most popular web browser with roughly 78% of browser usage verses 11% for Firefox . It was important to collect data from the most commonly used browser since there was a greater chance most Facebook users use Chrome to access their Facebook accounts. Our raw data consisted of roughly 50,000 data each with the 7 attributes listed below:
*	Type: The topic (top trends, politics, science and technology, sports, or entertainment)
*	Title: Title of news trend
*	Description: The short description located under the title (Figure 7)
*	Trend Link: The link that redirects the user when the trend is clicked. The link redirects the user to a compilation of news on a Facebook page. 
*	Rank: Where the trend is ranked in the trending list
*	Scrape ID: An integer to keep track of which round of scraping the data is collected from
*	Timestamp: The exact time and day the data was collected (YY-MM-DD HH-MM-SS)

Type was used to distinguish the different topics during the analysis. The analysis investigated the top trends for all five topics in addition to the top trends for each of the topics. Title and description were collected for detail for each news trend. The trend link was used to uniquely identify each trend. Rank was collected to discover where in the list certain new trends were placed and whether they moved up or down the list. Scrape ID was used with trend link to uniquely identify trends for the whole dataset. Timestamp was used to keep track of the time and date the data was collected, which was critical when analyzing the trend behavior at different days of the week.

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

The figure above depicts the results that various machine learners achieve on our data. We recorded accuracy, precision, and recall. While some of the results might be sporadic, we want to focus on precision. In terms of importance, we say that precision and recall are more important than accuracy, as a large amount of data is not related to tech companies, and so when classifiers classify most examples is irrelevant, they will achieve high accuracy anyway. Precision is given more importance than recall, as precision shows how many of our classifications were actually correct classifications, whereas recall only shows how many within a category we were able to classify correctly as that category. In other words, precision is more important because we are placing more importance on showing relevant news articles, even if it might lead to fewer news articles.

Our solution, in terms of accuracy, performed well across the board with different machine learners. This however, is to be expected, as our data shows that most news articles will not be about tech companies because there is such a large variety of topics that the media covers. As a result, machine learners will all get similar accuracies by classifying most articles as not relevant to tech companies. Therefore we judged performance by focusing on precision. The machine learner with the best precision was Simple Logistic, ran by Weka. As far as the features go, we found that description, title, and topic were the most important. This makes intuitive sense as description, title, and topic hold the most immediate information about any article.


## Conclusion

### Sources
https://www.recode.net/2017/9/7/16270900/social-media-news-americans-facebook-twitter



