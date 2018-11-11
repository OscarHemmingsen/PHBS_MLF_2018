# Outcome of NFL games based on the QB's performance
## PHBS_MLF_2018

ID# OscarHemmingsen - 1802010265 
& ID# ThanhVuongng - 1802010228

## Description

This project will use the statistics from different Quarterback (hereafter QB) performances over time dating back to 2002. Furthermore, we have collected the actual outcome of those game, so that we are able to match statistics from the QB's performance to the actual outcome. Hence, we will try to build a model that will be able to predict the outcome of an NFL-game based on the QB's performance.

## Data & Preprocessing

Our dataset was found on Kaggle in which all different quarterback performances from the late 90's up until 2016 was included. Here, various statistics such as attempts, completions, touchdowns etc. were included. However, we needed to find out whether the team actually lost or won that actual game. This statistic was not included in the dataset. Therefore, we found via NFL.com's database the actual outcome of that particular game in which we matched the year and the quarterback to the actual game.

Since the dataset was for ALL QBs that had played a game, it also included backup statistics e.g. when the team is leading by a lot and the team decides to rest the starting players. Therefore, we made a threshold in which all QBs had to at least make 15 attempts in the game. We felt this would give the indication that the QB had at least started the game and probably played at least half of the game. Our dataset is comprised of 1,214 QB stats where as 688 are wins and the rest (526) are losses.

Below is a snapshot of how our data is presented:


![data overview](https://user-images.githubusercontent.com/42951299/48195285-2aed8000-e38a-11e8-8c3d-7226dd9789d2.jpg)

First, we wanted to get visuals of the data, so we made some simple graphs and tables so we could maybe get some pre-indications for our model.


![mean win-loss stats](https://user-images.githubusercontent.com/42951299/48195951-fd093b00-e38b-11e8-84a8-b884dd0690b0.jpg)


Above is a mean computation of a winning and losing QB. It is interesting to see that a winning QB on average throws fewer times than a losing QB. We would assume based on the current state of the NFL and how the game is played now that the roles would have been switched. Other than that we conclude that the data is fairly logical in which the QB throws more touchdowns and less interceptions (when the opposing team catches the ball) when the team is winning.

Below are two simple versus tables for win or losses compared to touchdowns and interceptions.

![statistik over sejre 2](https://user-images.githubusercontent.com/42951299/48198984-a43ea000-e395-11e8-90bb-a098fd576f1e.png)

![statistik over sejre](https://user-images.githubusercontent.com/42951299/48198823-14005b00-e395-11e8-91d0-c8c96b123ec3.png)


It is very interesting to see that when a QB does not throw an interception his team is almost four times as likely to win a game. The ratio of winning a game compared to how many touchdowms the QB throws is very interesting. The team is twice as likely to lose the game when the QB does not throw a touchdown, and e.g. when he throws three or more they are almost guaranteed to win.

## Models & Graphs

To test our hypthosesis we have used different prediction and classifier models. Since our data comprises of a binary output we felt that a logistic regression would be the first natural step.

### Logistic regression

First, we started by checking the correlation of our chosen features. We excluded the feature home/away since only wanted data "produced" by the QB. We also deleted points, as this is a natural outcome of the game. Then, we also excluded "QB Rating" since this feature is a mathematical formula comprised of stats by the QB in regards to his completion percentage, touchdown thrown, interceptions thrown. We found, as expected, this feature had a very high correlation with the other features. Therefore, the following eight were chosen:

![correlation matrix](https://user-images.githubusercontent.com/42951299/48309037-c4e04300-e5ab-11e8-9dfb-ea539d4e844c.jpg)

As we can see there are only 2x2 features with high correlation which are attempts/completions and sack/loss. This is very naturally as if the QB throws more times he is much more likely to complete more times.
The same goes for sacks (when the QB is tackled by the opposing team) and loss (yards lost by being sacked).

We tested our logistic regression model with a train/test split of 0.2, = 80 % = train and 20 % = test and a random state of 42. Here we get an accuray of 79.42 %. We think this is fairly accurate, but we want to test our dataset further and see if we can get a better accurary. We tried a K-fold cross validation (K = 10) on our prediction model and came up with the following accurary = 76.71 %. With K = 5, the accurary increased to 76.82 % (up 0.11 percentage points), so there are not difference to K equal 5 or 10.

We then wanted to build a confusion matrix for our logistic regression model. Here, we get the following output where 1 = W and 0 = L

![confusion matrix](https://user-images.githubusercontent.com/42951188/48194979-74899b00-e389-11e8-9a3a-2a005d4da274.png)

As shown above we get the following ratios:

Accuracy = (121+72) / (121+18+72+32) = 79.42 %

Prediction = 121 / (121+32) = 79.08 % 

Recall = 121 / (121+18) = 87.05 %

Based on our confusion matrix and its ratios, we are fairly happy with its precision and the very good recall rate.

Next, and final for the regression is the 

### Decision tree

We build two decision tree models. One, where we decide via the gini and the second with the information gain

Gini index

<img width="697" alt="gini index" src="https://user-images.githubusercontent.com/42951188/48195642-2d040e80-e38b-11e8-9753-3827cd9a254c.png">

Information gain 

<img width="748" alt="information gain" src="https://user-images.githubusercontent.com/42951188/48195645-2d9ca500-e38b-11e8-91e1-cc638a9bcfe1.png">

### KNN with K=8

![knn](https://user-images.githubusercontent.com/42951299/48198815-0b0f8980-e395-11e8-8d42-1a70e8c5c7e1.jpg)




Cross-validated score

![cross-validation](https://user-images.githubusercontent.com/42951299/48198812-077c0280-e395-11e8-80c7-df11f8bdd19a.jpg)


## PCA Analysis

![covariance matrix](https://user-images.githubusercontent.com/42951299/48309064-4e901080-e5ac-11e8-9fa4-5f4ed6beacd7.jpg)

# Goal of the project

The goals of this project are the following:
- Ability to predict the outcome of an NFL-game based on the Quarterbacks (QB) performance.
- Group performances "together" and quantify a "bad", "medium" and "good" performance.
- Being able to show the changes in the game over time based on data from the early 2000's.


