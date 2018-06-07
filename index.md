# Our website: https://shinandruth.github.io/Facebook-News-Topics/

#### Shin Lee, Julie Kim, Josh Koo

**Title**: Facebook News Topics

**Contact**: joshuakoo2017@u.northwestern.edu

**Course**: Machine Learning: EECS 349 at Northwestern University

## Abstract
We wanted to apply machine learning techniques to classify Facebook News topics and give news recommendation for users who are interested in certain topics. For example, if Sam is activate on Facebook and he likes to read news about cars, we wanted our machine learning techniques to classify news topics related to cars into a category and give recommendations accordingly. Using programming and analytical methods, we wrote scripts to scrape data from Facebook Trending News, conducted pre-processing on our collected data, and analyze the data with Weka.  

### What?:


## Introduction
### *Motivation*
Facebook has recently been a topic of hot discussion regarding fake news and algorithms that present bias posts. This introduced and influenced us to investigate and apply machine learning techniques to Facebook News. This is important because traditional news are being replaced with online news. According to a study by Pew Research Center, 67% of Americans get their news from social media. This is very interesting because many online news companies are consistently making affort to provide accurate recommendations for their users and we wanted to create a similar task by using machine learning to classify news topics.  

## Methodology
### Method
#### Data Collection
The scraping scripts were written in Python 3.6.4 and Selenium, a user interface (UI) automation tool that automates UI testing. Selenium was selected because it can simulate a real human user and trick the web browsers. It can distribute and scale scripts over many different environments and can create robust, regression automation tests. Regression automation test’s purpose is to catch bugs that were accidently introduced and make sure previous bugs stay dead. Initially, we collected data using Mozilla Firefox because Selenium IDE, a Firefox add-on, was only available on Firefox and we had experience with Selenium IDE. Since we did not use Selenium IDE for this experiment but instead we used Selenium WebDriver which is available on multiple browsers, we were not restricted to one browser.  After running into issues with Firefox when running the scripts on the AWS cloud server, we changed from Firefox to Google Chrome. Another reason we changed from Firefox to Chrome was because Chrome is the most popular web browser with roughly 78% of browser usage verses 11% for Firefox . It was important to collect data from the most commonly used browser since there was a greater chance most Facebook users use Chrome to access their Facebook accounts.
### Data

## Results

## Conclusion

### Sources
https://www.recode.net/2017/9/7/16270900/social-media-news-americans-facebook-twitter



