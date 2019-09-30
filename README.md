# UFC_predict

## Overview

The goal of this project was to predict the winner of UFC fights, given both fighters previous fight statistics. The data that I used to do this was obtained from https://www.kaggle.com/calmdownkarm/ufcdataset.

For my process, I first had to clean the data so that I could use it in classification models. I then ran a dummy model to find a baseline accuracy threashold that I wanted to beat. That baseline was about 58%. After establishing my baseline, I ran several classification models with all features, running grid search for a few to try to optimize the parameters of the models.

Using grid search for a random forest classifier, I was able to classify the winner of each fight with about 65% accuracy. Although I plan on obtaining more data and running more models to improve this project, I believe that this model is pretty good given that it was almost equally accurate in predicting both red fighters and blue fighters winning. I will go into further detail on below on why I believe this is a good way to evaluate the model.

## Data
#### Distribution of Fight Winners (Red Corner Fighter vs. Blue Corner Fighter)
![Fight winner hist](https://github.com/hmnathel/UFC_predict/blob/master/Distribution_Winners.png)
As you can s

## Baseline Model
#### Dummy Classifier
![Dummy class scores](https://github.com/hmnathel/UFC_predict/blob/master/dummy_conf_matrixscore.png)
![Dummy class matrix](https://github.com/hmnathel/UFC_predict/blob/master/dummy_conf_matrix.png)

## Random Forest After Grid Search
#### Random Forest with Grid Search
![RFGS scores and matrix](https://github.com/hmnathel/UFC_predict/blob/master/RFwGS_conf_matrix.png)
![RFGS feature importance](https://github.com/hmnathel/UFC_predict/blob/master/RFwGS_feature_importance.png)
