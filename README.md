# Facebook Engagement Prediction
This project uses a Facebook dataset to understand what makes a post get more interactions (likes, comments, shares). The goal is to build a simple machine learning model that tries to predict how much engagement a post will get before it is posted.

## 1.Dataset
The data comes from the UCI Machine Learning Repository:https://archive.ics.uci.edu/dataset/368/facebook+metrics
The data contains 500 Facebook posts from a real business page.
Each row is one post, and it includes things like: what type of post it was (Photo, Status, Link, Video),what day and time it was posted, whether the post was paid/boosted, how many likes, comments, and shares it got,total interactions (our target)

## What I did (Explore and Transform sections) - 
First, I looked at the data to understand patterns. Some simple findings I found are  Photo and Video posts usually get more interactions, paid posts tend to perform better, posting time (hour of day) shows some patterns, engagement numbers are very skewed because just a few posts go viral, most don’t.
Then to help the model learn better, I created a few new features: I grouped post types into Visual (Photo/Video) and Text (Status/Link). I then grouped posting hours into Morning, Afternoon, Evening, Night.
I then turned categories into dummy variables (0s and 1s) and then applied a log transform to the target (Total Interactions) to reduce the skew.

## Modeling (Linear Regression)
I used a Linear Regression model because it’s simple and easy to interpret.
Model Results
R² = 0.069
RMSE (log scale) = 0.993
This means my model explains about 7% of why posts get more or fewer interactions. This is very low and hence i am not so confident that the method i used is the best with all the outliers present in the dataset.
Also i realized from research that social media engagement is hard to predict with simple features like the ones i used. Things like content quality, topic, and virality matter a lot but are not in the dataset and also maybe the brand is not that popular or a very new on.
