# flightfare_accuracy_90.04-
FLIGHT-FARE PREDICTION For a traveller it is important to know the fare value of a trip, and as prices of flight ticket varies abruptly and it becomes hectic for a user to check different websites, use different deals. A flight fare prediction model will help inform the travellers with the optimal time to buy their flight tickets and understand trends in the airline industr
# STEPS
1.	Drop 1 row for missing values and checked for duplicates.
2.	Journey day, month and weekday extracted from datetime
3.	DOJ is dropped
4.	Duration is in hours and mins, converting that to mins
5.	Categorising departure and arrival time to morning, afternoon, evening, and night
6.	Refining total stops column (No stop converted to 0) and Additional info column (No info to No Info, cases matching)
7.	Route is dropped
8.	Relation between departure time and price is checked by sns pairplot. It is seen when the price of flights are high (in morning and evening)
9.	Checked for outliers in the price variable. Box plot q75, q25 = np.percentile(train.loc[:,i], [75 ,25]) iqr = q75 - q25 min = q25 - (iqr*1.5) max = q75 + (iqr*1.5) Values more than min value and values more than max value are dropped.
10.	Correlation between duration and price is checked and found out that they are moderately positively correlated.
11.	Label encoding for all the categorical variables are done and standardisation of the numerical variables are done.
12.	data is divided into x and y and they are converted to array to make sure only numerical values are going into the model
13.	learning_rate':[0.01,0.05,0.1],'max_depth':[1,2,3],'n_estimators':[100,200,500] XGB and GBM hyperparameters
14.	knn k value is checked between 1 and 20
15.	n_estimators':[500], "max_features" : ["auto", "log2", "sqrt"],"bootstrap": [True, False], • If “auto”, then max_features=n_features. • If “sqrt”, then max_features=sqrt(n_features). • If “log2”, then max_features=log2(n_features). Whether bootstrap samples are used when building trees. If False, the whole dataset is used to build each tree.
16.	Cross validation with accuracy with k=5.

# MODELS USED:
Random Forest : 90.04%
KNN : 75.7%
Xgboost : 87.48%
Gradientboost : 87.59%
