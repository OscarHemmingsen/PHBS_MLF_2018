# PHBS_MLF_2018

ID# OscarHemmingsen - 1802010265 & ID# ThanhVuongng - 1802010228

# Outcome of NFL games based on the QB's performance

# Description

This project will use the statistics from different Quarterback performances over time dating back to 2002. Furthermore, we have collected the actual outcome of those game, so that we are able to match statistics from the QB's performance to the actual outcome. Hence, we will try to build a model that will be able to predict the outcome of an NFL-game based on the QB's performance.

## Data & Preprocessing

Data is presented the following way:

![data overview](https://user-images.githubusercontent.com/42951299/48195285-2aed8000-e38a-11e8-8c3d-7226dd9789d2.jpg)

We then wanted to get a visual on the means of a win and a loss as well as tables of the features vs the game outcome

![mean win-loss stats](https://user-images.githubusercontent.com/42951299/48195951-fd093b00-e38b-11e8-84a8-b884dd0690b0.jpg)




## Models & Graphs

### Logistis regression

First, we stated trying to build a logistic regression model. This was mainly due to its simplicity and the fact we have a binary output

<img width="590" alt="logistic regression" src="https://user-images.githubusercontent.com/42951188/48195643-2d9ca500-e38b-11e8-96e2-2a8f1cfa2dbc.png">

### Decision tree

We build two decision tree models. One, where we decide via the gini and the second with the information gain

Gini index

<img width="697" alt="gini index" src="https://user-images.githubusercontent.com/42951188/48195642-2d040e80-e38b-11e8-9753-3827cd9a254c.png">

Information gain 

<img width="748" alt="information gain" src="https://user-images.githubusercontent.com/42951188/48195645-2d9ca500-e38b-11e8-91e1-cc638a9bcfe1.png">


### Confusion matrix and ratios 

Below is our confusion matrix and the following ratios

![confusion matrix](https://user-images.githubusercontent.com/42951188/48194979-74899b00-e389-11e8-9a3a-2a005d4da274.png)

Accuracy, Prediction and Recall

<img width="254" alt="accuracy_prediction_recall" src="https://user-images.githubusercontent.com/42951188/48195644-2d9ca500-e38b-11e8-9bf8-cea2e7d7de16.png">




# Goal of the project

The goals of this project are the following:
- Ability to predict the outcome of an NFL-game based on the Quarterbacks (QB) performance.
- Group performances "together" and quantify a "bad", "medium" and "good" performance.
- Being able to show the changes in the game over time based on data from the early 2000's.


