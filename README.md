# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Predicting NFL Fantasy Performance Using Twitter
### By: 
Bobby Kelsey

### Contents:
* [Twitter Scrapping](https://github.com/rkelsey1207/Capstone/blob/master/Twitter_scrapping.ipynb)
* [Cleaning Data](https://github.com/rkelsey1207/Capstone/blob/master/Cleaning%20game%20.ipynb)
* [Compiling Data](https://git.generalassemb.ly/rkelsey1207/rkelsey_capstone/blob/master/Compiling_dataframes.ipynb)
* [EDA and Modeling] 

## Table of Contents

[1. Problem Statement](#1.-Problem-Statement)<br>
[2. Executive Summary](#2.-Tools-&-Methodology)<br>
[3. Data Dictionary](#3.-Data-Dictionary)<br>
[4. Key Takeways](#4.-Key-Takeaways)<br>
[5. Next Steps](#5.-Next-Steps)<br>

## 1. Problem Statement

With the Federal legalization of sports betting, states have been quick to take action in leaglizing it in their own district. 
This legalization will almost certainly lead to an increase in fantasy owned teams. Throughout the years, Fantasy football has become extremely popular with an estimated market value of over $11 billion.  Over 2 million fantasy teams are expected to be drafted in 2019, but who will come out on top? Millions will prepare by generating mock drafts, analyzing players statistics from previous years, and even creating models to pick the perfect team. However, can we turn to social media for the best predictors?

The goal of this project is to see if we can use NFL player's personal tweets to predict if they will perform better or worse than their average. I will conduct a sentiment analysis on the top 150 fantasy player's tweets prior to each games week and compar it to their performance results. 


## 2. Executive Summary

The data from this analysis was obtain from an existing Kaggle dataset (https://www.kaggle.com/pablote/nba-enhanced-stats). The dataset covers six seasons, 2012 to 2017.  There are 30 teams in the league that play an 82 game season for a total of 7,380 games over the six seasons.

The basic framework used was a four factor model.  The overall elements of the model are shooting, turnovers, rebounding and free throws. Several variables make up each of these elements. A logistic regression was conducted on both the data for individual games and a five game moving average.

The following packages were imported to conduct this analysis.

|        |         |                  |            |
|--------|---------|------------------|------------|
| Pandas | Numpy   | Pandas Profiling | Matplotlib |
| Scipy  | Sklearn | Seaborn          | Warnings   |

## 3. Data Dictionary


| Feature       | Type    | Description                                                        |
|---------------|---------|--------------------------------------------------------------------|
| name          | string  | Name of player                                                     |
| position      | string  | Postion of player                                                  |
| game_location | string  | Location of game                                                   |
| def_avg       | float   | Average fantasy of oppponent                                       |
| text          | integer | Number of tweets per that player for given week                    |
| neg           | float   | Calculated negativity for that week                                |
| pos           | float   | Calculated positivity for that week                                |
| neg_avg       | float   | Average negativity for the player that season                      |
| pos_avg       | float   | Average positivity for the player that season                      |
| neg_text      | float   | Neg * text                                                         |
| pos_text      | float   | Pos * text                                                         |
| position_RB   | string  | Dummy for position. RB is running back                             |
| position_WR   | string  | Dummy for position. WR is wide receiver                            |
| position_TE   | string  | Dummy for position. TE is tight end                                |
| position_WR/RB| string  | Dummy for position. WR/RB is WR and RB                             |


## 4. Initial Thoughts

   The current model resultsa with an R-squared of 17.89, which is slightly lower than what we would want in order to use this for real life purposes. I will continue to develop features and add new data to support with the performance of the model. If you have any thoughts or recomendations, please do not hesistate to reach out!


## 5. Looking Forward

Things to do:
   * Add more game data (weather, moving averages)
   * Generate more features through twitter data
   * Check regression in reverse order - tweets after a game
 
