# Pump-it-up project
### Can you predict which water pumps are faulty?
## Goal
Using data from Taarifa and the Tanzanian Ministry of Water, predict which pumps are functional, which need some repairs, and which don't work at all based on a number of variables about what kind of pump is operating, when it was installed, and how it is managed.

A smart understanding of which waterpoints will fail can improve maintenance operations and ensure that clean, potable water is available to communities across Tanzania.

In my research I've first performed an **exploratory data analysis**. In the beginning I calculated a preliminary/baseline accuracy score which means that a model predicting with the accuracy less than 54.31% is not adding any value, so it would not be better than an uneducated guess. I then splited the data into numerical and categorical columns, identified missing values to deal with in the preprocessing phase, searched for outliers in the data and assessed correlations among attributes.

In the next step I've performed **data cleaning and preprocessing**. First of all I dropped features containing similar information to avoid multicollinearity. Then I filled missing values, reduced cardinality of several categorical features that had many types of values to be able to encode them. I performed ordinal encoding for those variables where it made sense and one-hot encoding for the rest of variables. Finally, I used feature engineering to create new predictors (including LDA, binning, binary variables, turning a date-time variable into a continious numerical variable).

After all the preprocessing I performed feature selection based on L1 regularization with logistic regression that yielded 80 most important variables out of 90 total columns.

In the final step I first **tested multiple models** with standard parameters and plotted the results on a graph.

The top 3 models for this project are:

- Random Forest
- Gradient Boosting Classifier
- Light Gradient Boosting Classifier

Hyperparameter tuning has only slightly improved the scores. Surprisingly retraining didn't improve the scores, this needs to be further investigated. Principle Component Analysis didn't improve the scores either as well as a Voting classifier I created using all 3 top models listed above.

**I achieved the maximum of 79.71% accuracy on the validation data and 79.6% accuracy on the test data submitted to the competition on DrivenData with the Random Forest model.**
