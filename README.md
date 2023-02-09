# **COVID-19-Tweet-Sentiment-Analysis**

# Problem Description 

This challenge asks you to build a classification model to predict the sentiment of COVID-19 tweets.The tweets have been pulled from Twitter and manual tagging has been done then. The names and usernames have been given codes to avoid any privacy concerns.

# Data Description

### We are given the following information:

* Username: Unique user-IDs of the users
* Location: Location of the user
* Tweet At: Date at which the tweet was made
* Original Tweet: The exact tweet
* Sentiment: Sentiment of the tweet

COVID-19 originally known as Corona VIrus Disease of 2019, has been declared as a pandemic by World Health Organization (WHO) on 11th March 2020. Unprecedented pressures have mounted on each country to make compelling requisites for controlling the population by assessing the cases and properly utilizing available resources. The rapid number of exponential cases globally has become the apprehension of panic, fear and anxiety among people. The mental and physical health of the global population is found to be directly proportional to this pandemic disease. It is the need of the hour to implement different measures to safeguard the countries by demystifying the pertinent facts and information.

### Workflow in this Project

![Capture](https://user-images.githubusercontent.com/82259772/130586521-be05913c-1b2f-4a20-85f2-1982a833daeb.PNG)

# Exploratory Data Analysis

* The original dataset has 6 columns and 41157 rows.

### Null values in Location column

* There are 20.87%(8567) null values in various places of location column. 

![image](https://user-images.githubusercontent.com/76884379/217925389-7d72a76d-1e35-4f1c-a106-b788c0cfce33.png)

* There are five types of sentiments- Extremely Negative, Negative, Neutral, Positive and Extremely Positive.

![image](https://user-images.githubusercontent.com/76884379/217918688-b2ec8539-367c-4ab4-a4ab-a35c4c051b85.png)

* All tweets data collected from the months of March and April 2020. Bar plot shows us the number of unique values in each column.

![image](https://user-images.githubusercontent.com/76884379/217919720-1c37a11d-d853-444d-afaa-512cc94f5fde.png)

* Most of the tweets came from London followed by U.S.

![image](https://user-images.githubusercontent.com/76884379/217920064-061464a2-8f48-440b-af3d-a403ca8cb7dc.png)

# Data Preprocessing

* The preprocessing of the text data is an essential step as it makes the raw text ready for mining.

* The objective of this step is to clean noise those are less relevant to find the sentiment of tweets such as punctuation, special characters, numbers, and terms which don’t carry much weightage in context to the text.

* Stop words are those words in natural language that have a very little meaning, such as "is", "an", "the", etc.To remove stop words from a sentence, you can divide your text into words and then remove the word if it exits in the list of stop words provided by NLTK.

* The tweets contain lots of twitter handles (@user). We will remove all these twitter handles from the data as they don’t convey much information.

* We are having twitter links in the data which are not useful for our Model. It will make our data noisy.

* Punctuations, numbers and special characters do not help much. It is better to remove them from the text just as we removed the twitter handles,links and hashtags.

* Stemming is a rule-based process of stripping the suffixes (“ing”, “ly”, “es”, “ed”, “s” etc) from a word. For example – “play”, “player”, “played”, “plays” and “playing” are the different variations of the word – “play”.

* Lemmatization is a more powerful operation, and it takes into consideration morphological analysis of the words. It returns the lemma which is the base form of all its inflectional forms.

* In tokenization we convert group of sentence into token . It is also called text segmentation or lexical analysis. It is basically splitting data into small chunk of words. Tokenization in python can be done by python NLTK library’s word_tokenize() function.

### After cleaning text we also create wordbcloud

![image](https://user-images.githubusercontent.com/76884379/217924904-fc00bd9a-1065-4c71-ae9d-20829a78617e.png)


# Model Evaluation

<img width="250" alt="image" src="https://user-images.githubusercontent.com/76884379/217923877-119d08d0-d6d8-4244-8979-0dc61782f598.png">

# Conclusion

## On EDA

*    Original dataset contains 6 columns and 41157 rows. <br>
*   ‘Location’ column contains approx. 20.87% of Null values.<br>
*   The columns such as “UserName” and “ScreenName” does not give any meaningful insights for our analysis.
*   In order to analyse the data we required only two columns "OriginalTweet" & "Sentiment". Hence, to avoid NaN values in "Location" columns we didnot used it further.
*   There are five types of sentiments- Extremely Negative, Negative, Neutral, Positive and Extremely Positive. So, we merged Extremely Positive with positive and Extremely Negative with Negative. And use encoding with value ‘-1’ for negative, ‘0’ for neutral and ‘1’ for positive. 
*  All tweets data collected between months of March and April 2020 and of around 30 days.
*  Most of the tweets came from London followed by U.S.
*  Among top 10 mentions in tweets realDolandTrump was the top mentioned name and "#coronavirus" was most trendiest hashtag that was trending during that period. 


## On Model Training

* At the end we conclude that in our project with 6 models namely Naive Bayes Classifier,Stochastic Gradient Descent, Random Forest Classifier,Support Vector Machine, Logistic Regression and CatBoost. We are getting the highest test accuracy of about **80.98%** with **Stochastic Gradient Descent**.








