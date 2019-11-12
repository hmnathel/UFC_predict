# UFC Fight Predictor

## Table of Contents:
* [Goal](#Goal)
* [Data Gathering](#Data-Gathering)
* [Data Cleaning](#Data-Cleaning)
* [Data Exploration](#Data-Exploration)
* [Classification Modeling](#Classification-Modeling)
* [Potential Improvements](#Potential-Improvements)
* [Closing](#Closing)

## Goal

The goal of this project was to create a classification model that can be used to gain a gambling edge on the Las Vegas odds. The classifcation model will predict the winner of UFC fights, given both fighters previous fight statistics and the las vegas odds. This model will then output its own odds which can be used for gambling by comparing them to the las vegas odds.

## Data Gathering
I collected fight statistics from and fighter bios from http://ufcstats.com/. I collected past gambling odds from https://www.betmma.tips/past_mma_handicapper_performance_all.php. I also collected data from https://www.espn.com/ which has not yet been used in any of my models. 

## Data Cleaning
Once I collected the necessary data, I wanted to make sure that stats could be compared in a fair way between two fighters. I turned most of my statistics into a per minute statistic like knock downs per minute (KDPM). Using opponents stats I created defensive statistics like take down defense. I had to create cumulative statistics for each fighter in every fight that they were going into. I created a function that could do that for every fight in my dataset.

## Data Exploration
I performed EDA by looking at what features had the highest correlation to winning or losing. Unsurprisingly, the las vegas odds had the highest correlation.
![Correlation Matrix](https://github.com/hmnathel/UFC_predict/blob/master/corr_matrix.png)


## Classification Modeling
#### Baseline Model
I then ran a dummy model to find a baseline accuracy threashold that I wanted to beat. That baseline was only about 50% accurate. This is not a good comparison, however, because the vegas odds are really what need to be compared to.
The las vegas odds are historically about 60% accurate.

#### Random Forest After Grid Search
Using grid search for a random forest classifier, I was able to classify the winner of each fight with about 65% accuracy. Although I plan on obtaining more data and running more models to improve this project, I believe that this model is pretty good given that it was almost equally accurate in predicting both red fighters and blue fighters winning. I will go into further detail on below on why I believe this is a good way to evaluate the model.
![RFGS scores and matrix](https://github.com/hmnathel/UFC_predict/blob/master/accuracy_RFgamble.png)
![RFGS feature importance](https://github.com/hmnathel/UFC_predict/blob/master/gambling_RFwgs_model_feature_imortance.png)


## Predicting New Fights
I created a function that, when inputing the url of an upcoming UFC event from https://www.betmma.tips/, ouputs which fights have greater than a 10% edge over the Las Vegas odds. I am still changing things in my model and more testing and cross validation needs to be done, but the model was profitable if used for gambling on my test set of 266 fights.

## Potential Improvements
There are a few features that I still want to add to my model including ground control time and hometown/country advantage. The difficulty with ground control time it hasn't been kept track of until the end of 2018.
I would also like to create a function that optimizes how much you should bet using the kelley criterion.

## Closing
More work needs to be done before implementing the model but, I believe that a profitable gambling model can built using UFC fight data. 
