# Welcome to SC1015-project repository
## About
Our mini-project for SC1015 (Introduction to Data Science and Artificial Intelligence) focuses on dark chocolate bar ratings from [Flavors of Cacao's database](http://flavorsofcacao.com/chocolate_database.html). Our dataset was acquired from a previously scraped and cleaned dataset on [Kaggle](https://www.kaggle.com/datasets/soroushghaderi/chocolate-bar-2020?select=chocolate.csv)
## Content of code
1. [Data Cleaning](https://github.com/bachts/sc1015-project/blob/main/Data%20cleaning.ipynb)
- Remove unrelated variables: company location, review date, review reference number
- Replaced binary categorical values with numerical values
- Reclassified rating to fit our problem statement
- Added the "number_of_taste" column  
2. [Exploratory Data Analysis ](https://github.com/bachts/sc1015-project/blob/main/Data%20visualization.ipynb)
- Examine the distribution of high vs. not-high rating for different ingredients.
- Examine the distribution of high vs. not-high rating for the number of ingredients and number of tastes
- Correlation and chi-squared test for each ingredients respective to rating category
- Examine the distribution of high vs. not-high rating for country of bean origin and taste
- Overall distribution between different groups of variables
3. [Machine Learning](https://github.com/bachts/sc1015-project/blob/main/Machine%20learning.ipynb)
- One-hot encoding for multi-class categorical variables
- Decision Tree
- Random Forest
- Upsampling data with different variants of SMOTE()
- Removing minority classes
- Gradient Boosting
## Contributors
- @bachts: SMOTE, Cross-validation, Gradient Boosting. 
- @Brybn: Random Forest, Removal of minority classes.
- @evangeline1234: Decision Tree, Data cleaning, Data visualization.
## Problem Definition
- Can we find out what makes a dark chocolate product highly rated by experts?
## Techniques Used
- SMOTE() and its variations
- KFold cross validation
- Decision Tree, Random Forest and Gradient Boosting
- One-hot encoding
## Outcome
- We discovered some variables that could influence the rating of a chocolate bar, such as number of ingredients, the taste of it.
- However, the variables in the dataset was not sufficient to predict the rating of a chocolate bar perfectly, but had somewhat acceptable accuracy, and was able to point out a large number of highly rated chocolate bars, despite a roughly 0.30 false positive rate.
- A more detailed dataset with more variables are recommended, such as the percentages of the ingredients, as well as a cleaner taste dataset.
## What did we learn
- Dealing with imbalanced data
- Utilizing cross-validation for tuning models
- Collaborating through github
- Dealing with categorical predictor variables
## References
Dark chocolate market size, share, scope, Opportunities & Forecast. Verified Market Research. (2021, November 24). Retrieved from https://www.verifiedmarketresearch.com/product/global-dark-chocolate-market/
Alakh Sethi. (2020, June 25). Categorical encoding: One hot encoding vs label encoding. Analytics Vidhya. Retrieved from https://www.analyticsvidhya.com/blog/2020/03/one-hot-encoding-vs-label-encoding-using-scikit-learn/
MediLexicon International. (n.d.). Chocolate: Health benefits, facts, and research. Medical News Today. Retrieved from https://www.medicalnewstoday.com/articles/270272#benefits
Gupta, (2022). Module 4 Topic 1: Binary Classification [PowerPoint Slides]. Retrieved from NTULearn course site.
RandomForestClassifier (2022). scikit-learn. Retrieved from https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html
Brownlee, J. (2019, October 21). A Gentle Introduction to the Chi-Squared Test for Machine Learning. Machine Learning Mastery. Retrieved from https://machinelearningmastery.com/chi-squared-test-for-machine-learning/
Brownlee, J. (2021, April 26). Gradient boosting with Scikit-learn, XGBoost, LIGHTGBM, and CatBoost. Machine Learning Mastery. Retrieved from https://machinelearningmastery.com/gradient-boosting-with-scikit-learn-xgboost-lightgbm-and-catboost/
https://imbalanced-learn.org/stable/references/generated/imblearn.over_sampling.ADASYN.html#imblearn.over_sampling.ADASYN
https://www.restaurantnorman.com/what-is-the-cutoff-for-skewness-and-kurtosis/#What_is_the_cutoff_for_skewness_and_kurtosis
https://machinelearningmastery.com/configure-gradient-boosting-algorithm/
https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/

