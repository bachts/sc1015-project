# Welcome to SC1015-project repository
## About
Our mini-project for SC1015 (Introduction to Data Science and Artificial Intelligence) focuses on dark chocolate bar ratings from [Flavors of Cacao's database](http://flavorsofcacao.com/chocolate_database.html). Our dataset was acquired from a previously scraped and cleaned dataset on [Kaggle](https://www.kaggle.com/datasets/soroushghaderi/chocolate-bar-2020?select=chocolate.csv)
## Problem Definition
- Can we find out what makes a dark chocolate product highly rated by experts?
## Content of code
1. [Data Cleaning](https://github.com/bachts/sc1015-project/blob/main/Data%20cleaning.ipynb)
- Remove unrelated variables: company location, review date, review reference number
- Replaced binary categorical values with numerical values
- Reclassified rating to fit our problem statement
- Added the "number_of_taste" column  
2. [Exploratory Data Analysis ](https://github.com/bachts/sc1015-project/blob/main/Data%20visualization.ipynb)
- Creates a helper function to visualize the percentage and proportion of the two ratings for different variables
- Examine the distribution of high vs. not-high rating for different ingredients.
- Examine the distribution of high vs. not-high rating for the number of ingredients and number of tastes
- Correlation and chi-squared test for each ingredients respective to rating category
- Examine the distribution of high vs. not-high rating for country of bean origin and taste
- Overall distribution between different groups of variables
This helped us drop columns such as cocoa_butter due to little correlation, as well as sweetener_with_salt due to its perfect negative correlation with sugar.
3. [Machine Learning](https://github.com/bachts/sc1015-project/blob/main/Machine%20learning.ipynb)
- One-hot encoding for multi-class categorical variables
country_of_bean_origin and the four taste columns have a lot of classes in it, which we dealt with by using one-hot encoder. The four taste columns are appended to a list, to ensure it does not discriminate between first_taste, second_taste, third_taste and fourth_taste
- Creates a helper function that cross-validate the model, and test the model on a train-test-split
Repeated Stratified K-fold cross-validation with k_fold = 5, number of repetition = 3. The train-test split has a test ratio of 0.2, stratify according the response variable
- Decision Tree
A very basic model used to see whether our dataset can be predicted easily. Results from cross-validation and fitting on a train-test set are bad, with low recall and accuracy.
- Random Forest
  - Showed better recall value and accuracy, better true positive and negative rate, however worse false positive rate.
- Upsampling data with different variants of SMOTE()
  - We fit the data on various SMOTE variants, and found that in general, the ADASYN model gave better accuracy, true negative rate and false positive rate.
- Removing minority classes
  - The country_of_bean_origin column is heavily skewed towards the right with a long tail, with skewness value of 2.22 and kurtosis value of 4.53. 35 counts was the chosen cut-off point as it gave acceptable skewness and kurtosis value of 0.98 and -0.53, respectively, while also retaining the most data points.
The result after applying both methods returned better recall, but worse accuracy. However, true positive rate gone up, but false positive rate went down.
- Gradient Boosting
  - This model returned the best accuracy and precision, with worse recall value but still in a respectable amount. True positive did went down, but false positive rate  and true negative were the best among all models.
## Outcome
- We discovered some variables that could influence the rating of a chocolate bar, such as number of ingredients, the taste of it, and the country of origin of the cocoa bean.
- However, the variables in the dataset was not sufficient to predict the rating of a chocolate bar perfectly, but had somewhat acceptable accuracy, and was able to point out a large number of highly rated chocolate bars, despite a roughly 0.30 false positive rate.
- Interesting thing to note: almost all chocolate bars used either sweetener or sugar, but rarely both. This could be some sort of standard in the dark chocolate industry, as without sugar it could lead to a bitter taste, which tends to lead to a not high rating illustrated in the EDA part.
## Data-driven insights
- Number and types of tastes is very important for a chocolate bar.
- Some of the most prevalent tastes in highly rated chocolate bars are rich and creamy.
- Ecuador and Guatemala tend to produce cocoa beans that are used in more highly rated bars.
- Most high-rated chocolate bars tend to have cocoa percent in the range of 70-73%.
## Recommendation
- More data, so that some data points do not have to be dropped.
- A more detailed dataset with more variables are recommended, such as the percentages of the ingredients, rather than a binary have vs. not have status, as well as a cleaner taste dataset.
- Better feature engineering of the taste columns, such as grouping similar classes like "cocoa", "mild cocoa", "rich cocoa", which has a lot of minority classes
- Utilize Natural Language Processing, specifically sentiment analysis for classes in taste such as "why bother", "wtf". This could further be utilized to deal with text reviews, such as from a survey, in the form of a description.
## What did we learn
- Dealing with imbalanced data
- Utilizing cross-validation for tuning models
- Collaborating through github
- Dealing with categorical predictor variables
## New techniques used
- SMOTE() and its variations
- KFold cross validation
- Random Forest and Gradient Boosting
- One-hot encoding
- Chi-square Test
## Contributors
- @bachts: SMOTE, Cross-validation, Gradient Boosting. 
- @Brybn: Random Forest, Removal of minority classes.
- @evangeline1234: Decision Tree, Data cleaning, Data visualization.
## References
Adasyn. ADASYN - Version 0.9.0.(n.d.). Retrieved from https://imbalanced-learn.org/stable/references/generated/imblearn.over_sampling.ADASYN.html#imblearn.over_sampling.ADASYN

Alakh Sethi. (2020, June 25). Categorical encoding: One hot encoding vs label encoding. Analytics Vidhya. Retrieved from https://www.analyticsvidhya.com/blog/2020/03/one-hot-encoding-vs-label-encoding-using-scikit-learn/

Brownlee, J. (2019, October 21). A Gentle Introduction to the Chi-Squared Test for Machine Learning. Machine Learning Mastery. Retrieved from https://machinelearningmastery.com/chi-squared-test-for-machine-learning/

Brownlee, J. (2021, April 26). Gradient boosting with Scikit-learn, XGBoost, LIGHTGBM, and CatBoost. Machine Learning Mastery. Retrieved from https://machinelearningmastery.com/gradient-boosting-with-scikit-learn-xgboost-lightgbm-and-catboost/

Brownlee, J. (2020, August 14). How to configure the gradient boosting algorithm. Machine Learning Mastery. Retrieved from 
https://machinelearningmastery.com/configure-gradient-boosting-algorithm/

Brownlee, J. (2021, March 16). Smote for imbalanced classification with python. Machine Learning Mastery. Retrieved from 
https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/

Dark chocolate market size, share, scope, Opportunities & Forecast. Verified Market Research. (2021, November 24). Retrieved from https://www.verifiedmarketresearch.com/product/global-dark-chocolate-market/

Gupta, (2022). Module 4 Topic 1: Binary Classification [PowerPoint Slides]. Retrieved from NTULearn course site.

RandomForestClassifier (2022). scikit-learn. Retrieved from https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html

MediLexicon International. (n.d.). Chocolate: Health benefits, facts, and research. Medical News Today. Retrieved from https://www.medicalnewstoday.com/articles/270272#benefits

RandomForestClassifier (2022). scikit-learn. Retrieved from https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html

Wilson, M. (2021, March 18). What is the cutoff for Skewness and kurtosis? Restaurantnorman.com. Retrieved from 
https://www.restaurantnorman.com/what-is-the-cutoff-for-skewness-and-kurtosis/#What_is_the_cutoff_for_skewness_and_kurtosis
