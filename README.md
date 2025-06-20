**Objective**

This code is designed to forecast store sales 16 days into the future. The data holds sales per day collected between 2013 and July 2017, and is constructed as follows: each row describes the sales on that day for a specific store for a specific product family. The data holds information about the number of product that were on promotion that day. Other data sources provide information about national, regional or local holidays, geography and location of the stores, oil prices, and total transactions per day per store.
The results are evaluated with the metric Root Mean Logarithmic Error.

**Approach**

The task involves many different time-series, that is, for each pair (store number,family) we have a distinct time series. However, we will use machine-learning models to learn the dynamics of these time series, and since we believe that there are similarities between the dynamics of the different time-seires, we choose to feed our model with the entire data, categorized by store number and family, in order to help the model learn the patterns that are similar between these time series.
The model that was decided upon is a combination of XGBoost, light gbm, and catboost, for the following reasons.
Firstly, they are known to be efficient, robust to outliers, and capture well the non-linear relationships in tabular forecasting tasks.
Secondly, the high-cardinality nature of the data is compatible with these choices.
Another reason is the fact that these models are easy to program, and provide convenient tools to avoid overfitting including early stopping criteria.

The full code can be found [here](https://github.com/yonatansha/store-sales--time-series-forecasting/blob/main/store-sales-notebook%20(2).ipynb).
