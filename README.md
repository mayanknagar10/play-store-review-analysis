# Play Store Review analysis EDA
![image](https://user-images.githubusercontent.com/86146916/215672306-b8c63f2e-df41-462f-84b2-be0a3752fe25.png)

Google Play, formerly Android Market, is a digital distribution service operated and developed by Google. It serves as the official app store for certified devices running on the Android operating system, allowing users to browse and download applications developed with the Android software development kit (SDK) and published through Google. It has crossed over 82 billion app downloads with over 3.5 million published apps making it the largest app store in the world.

In this notebook, I will explore and analyze the Google Play Store Data. I used python for analyzing the dataset. Google Play Store apps and reviews Mobile apps are everywhere. They are easy to create and can be lucrative. Because of these two factors, more and more apps are being developed. In this notebook, we will do a comprehensive analysis of the Android app market by comparing over ten thousand apps in Google Play across different categories. We'll look for insights in the data to devise strategies to drive growth and retention.

Dataset:
1. Play Store Data.csv: This data consists of 13 features which describe the details of different applications on Google play Store.
2. User Reviews.csv: This data consists of 5 features which gives the brief about the reviews and sentiments which is helpful for application growth and what changes should do to make the different application unique.

Information about the 13 features of Play store data.

play_store dataframe has 10841 rows and 13 columns. The 13 columns are identified as below:

1. App - It tells us about the name of the application with a short description (optional).
2. Category - It gives the category to the app.
3. Rating - It contains the average rating the respective app received from its users.
4. Reviews - It tells us about the total number of users who have given a review for the application.
5. Size - It tells us about the size being occupied the application on the mobile phone.
6. Installs - It tells us about the total number of installs/downloads for an application.
7. Type - IIt states whether an app is free to use or paid.
8. Price - It gives the price payable to install the app. For free type apps, the price is zero.
9. Content Rating - It states whether or not an app is suitable for all age groups or not.
10. Genres - It tells us about the various other categories to which an application can belong.
11. Last Updated - It tells us about the when the application was updated.
12. Current Ver - It tells us about the current version of the application.
13. Android Ver - It tells us about the android version which can support the application on its platform.


Information about the 5 features of User Review data.

User_reviews dataframe has 64295 rows and 5 columns. The 15 columns are identified as below:

1. App: Contains the name of the app with a short description (optional).
2. Translated_Review: It contains the English translation of the review dropped by the user of the app.
3. Sentiment: It gives the attitude/emotion of the writer. It can be ‘Positive’, ‘Negative’, or ‘Neutral’.
4. Sentiment_Polarity: It gives the polarity of the review. Its range is [-1,1], where 1 means ‘Positive statement’ and -1 means a ‘Negative statement’.
5. Sentiment_Subjectivity: This value gives how close a reviewers opinion is to the opinion of the general public. Its range is [0,1]. Higher the subjectivity, closer is the reviewers opinion to the opinion of the general public, and lower subjectivity indicates the review is more of a factual information.


## Problem Statements:

1. What are the top categories on Play Store?
2. Are majority of the apps Paid or Free?
3. How importance is the rating of the application?
4. Which categories from the audience should the app be based on?
5. Which category has the most no. of installations?
6. How does the count of apps varies by Genres?
7. How does the last update has an effect on the rating?
8. How are ratings affected when the app is a paid one?
9. How are reviews and ratings co-related?
10. Lets us discuss the sentiment subjectivity.
11. Is subjectivity and polarity proportional to each other?
12. What is the percentage of review sentiments?
13. How is sentiment polarity varying for paid and free apps?
14. How Content Rating affect over the App?
15. Does Last Update date has an effects on rating?

## What is Exploratory Data Analysis?

Exploratory data analysis (EDA) is used by data scientists to analyze and investigate data sets for patterns, and anomalies (outliers), and form hypotheses based on our understanding of the dataset and summarize their main characteristics, often employing data visualization methods. It is an important step in any Data Analysis or Data Science project. It helps determine how best to manipulate data sources to get the answers you need.

EDA involves generating summary statistics for numerical data in the dataset and creating various graphical representations to understand the data better and make it more attractive and appealing.

The following are the various steps involved in the EDA process:

- Problem Statement - We shall brainstorm and understand the given data set. We shall study the attributes present in it and try to do a philosophical analysis about their meaning and importance for this problem.
- Hypothesis - Upon studying the attributes present in the data base, we shall develop some basic hypothesis on which we can work and play with the data to look for the varied results which we can get out of it.
- Univariate Analysis - It is the simplest form of analyzing the data. In this we would initially pick up a single attribute and study it in and out. It doesn't deal with any sort of co-relation and it's major purpose is to describe. It takes data, summarizes that data and finds patterns in the data.
- Bivariate Analysis - This analysis is related to cause and the relationship between the two attributes. We will try to understand the dependency of attributes on each other.
- Multivariate Analysis - This is done when more than two variables have to be analyzed simultaneously.
- Data Cleaning - We shall clean the dataset and handle the missing data, outliers and categorical variables.
- Testing Hypothesis - We shall check if our data meets the assumptions required by most of the multivariate techniques.

1. Define the problem and goal: This step involves understanding the problem you are trying to solve and setting a clear goal for your analysis.

2. Collect and import data: This step involves collecting the data you need for your analysis. This could involve obtaining data from a database, a CSV file, or a web API.

3. Clean and preprocess data: This step involves cleaning and preprocessing the data you have collected. This could involve removing missing values, dealing with outliers, and transforming variables to make them suitable for analysis.

4. Univariate analysis: This step involves analyzing each variable individually, to understand their distribution, central tendency, and spread.

5. Bivariate analysis: This step involves analyzing the relationship between two variables. This could involve calculating the correlation between variables, or creating scatter plots to visualize the relationship.

6. Multivariate analysis: This step involves analyzing the relationship between three or more variables. This could involve creating scatter plots, or using more advanced techniques such as multiple regression analysis.

7. Data visualization: This step involves creating visualizations to help understand the data and communicate insights. This could involve creating histograms, bar charts, line charts, or more advanced visualizations such as heat maps or interactive dashboards.

8. Draw conclusions and identify patterns: This step involves drawing conclusions from the analysis and identifying patterns in the data. This could involve creating summary statistics, or creating models to make predictions.

9. Refine and repeat steps as needed: This step involves refining the analysis as needed, and repeating steps as needed to obtain a deeper understanding of the data. This could involve repeating the analysis with different subsets of the data, or using different techniques to analyze the data.

## Analysis Summary

In this project of analyzing play store applications, we have worked on several parameters which would help App Developers to do well in launching their apps on the play store.

In the initial phase, we focused more on the problem statements and data cleaning, in order to ensure that we give them the best results out of our analysis.

App Developers needs to focus more on:

Developing apps related to the least categories as they are not explored much. Like events and beauty.
Most of the apps are Free, so focusing on free app is more important.
Focusing more on content available for Everyone will increase the chances of getting the highest installs.
They need to focus on updating their apps regularly, so that it will attract more users.
They need to keep in mind that the sentiments of the user keep varying as they keep using the app, so they should focus more on users needs and features.

### 1. Rating
Most of the apps have rating in between 4 and 5.

Most numbers of apps are rated at 4.3

Categories of apps have more than 4 average rating.item

### 2. Size
Maximum number of applications present in the dataset are of small size.

### 3. Installs
Majority of the apps come into these three categories, Family, Game, and Tools.

Maximum number of apps present in google play store come under Family, Game and tools but as per the installation and requirement in the market plot, scenario is not the same. Maximum installed apps comes under Game, Communication, Productivity and Social.

Subway Surfers, Facebook, Messenger and Google Drive are the most installed apps.

### 4. Type(Free/Paid)
About 92% apps are free and 8% apps are of paid type.

The category ‘Family’ has the highest number of paid apps.

Free apps are installed more than paid apps.

The app “I’m Rich — Trump Edition” from the category ‘Lifestyle’ is the most costly app priced at

### 5. Content Rating
Content having Everyone only has most installs, while unrated and Adults only 18+ have less installs.

### 6. Reviews
Number of installs is positively correlated with reviews with correlation 0.64. Sentiment Analysis

### 7. Sentiment
Most of the reviews are of Positive Sentiment, while Negative and Neutral have low number of reviews.

### 8. Sentiment Polarity / Sentiment Subjectivity
Collection of reviews shows a wide range of subjectivity and most of the reviews fall in [-0.50,0.75] polarity scale implying that the extremely negative or positive sentiments are significantly low. Most of the reviews show a mid-range of negative and positive sentiments.

Sentiment subjectivity is not always proportional to sentiment polarity but in maximum number of case, shows a proportional behavior, when variance is too high or low.

Sentiment Polarity is not highly correlated with Sentiment Subjectivity.

## Challenges

Handling large volume of data: The number of app reviews can be overwhelming, and processing such large amounts of data can be a challenge.

Major challenge was data cleaning.

Dealing with subjective opinions: User opinions and feedback can be subjective, making it challenging to reach objective conclusions.

## Future Work

We can explore the correlation between the size of the app and the version of Android on the number of installs.

Machine learning can help us to deploy more insights by developing models which can help us interpret even more better. We have left this as future work as this is something where we can work on.

Improving sentiment analysis techniques: There is room for improvement in sentiment analysis techniques to accurately capture the sentiment expressed in app reviews.

Incorporating additional data sources: Other data sources such as demographic information about app users, usage data, and device information could be incorporated to provide a more complete picture of the app's user base and performance.
