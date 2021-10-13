# DSI Capstone - Predicting NFL Player Fantasy Points

**Problem Statement**

Company: ESPN

Problem: ESPN is one of the largest providers of fantasy football services in the industry. Prior to each season they provide
their users with season long predictions for each player. They want to see if I can build a better model than their current lead
fantasy data scientist, Mike Clay. 

---
## Data Gathering:

Looked at 4 positions: Quarterback, Running Back, Wide Receiver, Tight End
Data from 5 full NFL seasons (2014-2018)
Traditional statistics (yards, TDs, carries, receptions, etc.) were scraped from pro-football-reference.com
Target column: fantasy points, also scraped from pro-football-reference.com

---
## Additional Features:
Acquired coaching and coordinator change data by hand (footballscopp.com and profootballrumors.com)

Aggregate preseason fantasy rankings by hundreds of experts pulled from FantasyPros.com

Salary data for each player from overthecap.com

Target data, i.e. the number of times a quarterback throws to a player whether he catches it or not. Known to be predictive in
fantasy football so I wanted to get players’ targets per game instead of total targets. This would adjust for any injuries or
games missed. Scraped from footballguys.com

Wanted to have a contract year column (1 or 0 if a player was in the last year of their contract) but after further research on
the subject, there didn’t seem to be a correlation between that and performance
(https://www.footballoutsiders.com/stat-analysis/2014/contract-year-phenomenon-revisited)

---
## Modeling:
Baseline RMSE: 88.61
5 models total: Linear Regression, Decision Tree, Gradient Boost, Random Forest, and a Neural Network
Linear Regression model explained 50.4% variance in data it had not yet seen with an RMSE of 62.34
Only model better was the Neural Network which had an RMSE of 61.74

I found ESPNs 2019 preseason predictions (done by their fantasy sports data scientist Mike Clay) but it was a pdf file so I had
to enter them into an excel sheet manually but the RMSE for his predictions was 59.76, just barely better than mine.

---
## Conclusions:
It is incredibly difficult to predict season long statistics for NFL players. There is far too much variability and noise of
the course of 16 NFL games (now 17) to get really accurate predictions. Mike Clay is little bit more accurate than me
but not by much. Plus Mike Clay has all the resources of ESPN, so not exactly a fair fight. But I think that speaks to how
difficult of a problem this is. Even one of top professionals in the industry doesn’t have a great RMSE
