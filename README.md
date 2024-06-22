# Optiver - Trading-at-the-Close
Last fall (2023) I participated in another Kaggle competition [Optiver - Trading-at-the-Close](https://www.kaggle.com/competitions/optiver-trading-at-the-close) whose goal was to predict US stocks closing movements during the Nasdaq closing cross auction.

I ended up being 2444-th out of 4436 teams with the score of 5.5565 (the best score was 5.4030) in the MAE metric.

## The competition
Optiver provided closing data (last 10 minutes) for 199 stocks traded on Nasdaq, including traditional order book and auction book data. The goal was to predict the 60 second future move in the weighted average price of each stock. Submissions were evaluated using the mean absolute error between the predicted return and the observed target.

## Datasets
 - 'train.csv' - contains 10-decond data for several types of prices (reference price, far price, near price, bid/ask price, weighted average price) and volumes (imbalance size, matched size) for all 199 stocks.
 -  'test.csv' - containс the same data as the train set minus the target column.

The files can be downloaded from the competition page [https://www.kaggle.com/competitions/g-research-crypto-forecasting/data](https://www.kaggle.com/competitions/optiver-trading-at-the-close/data)

## Solution
My solution relied on feature engineering and using the Optuna package to find optimal parameters for XGBoost (see [gresearch-model-2.ipynb](gresearch-model-2.ipynb)). I also tried
a LightGBM model, but somehow XGBoost performed better.
