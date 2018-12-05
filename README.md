# Customer-Churn
The objective of this Case is to predict customer behaviour.

## Tools Used:
##### Python
##### Jupyter Notebook
##### Git

## Python libraries
##### sklearn
##### pandas
##### numpy
##### os
##### fancyimpute
##### seaborn

## Information about the data:
The attributes in the data provided are as follows: 
##### account length 
##### international plan 
##### voicemail plan 
##### number of voicemail messages 
##### total day minutes used 
##### day calls made 
##### total day charge 
##### total evening minutes 
##### total evening calls 
##### total evening charge 
##### total night minutes 
##### total night calls 
##### total night charge 
##### total international minutes used 
##### total international calls made 
##### total international charge  
##### number of customer service calls made 
##### Churn: if the customer has moved (1=yes; 0 = no)


## Problem Statement
The objective of this Case is to predict customer behaviour. We are providing you a public dataset that has customer usage pattern and if the customer has moved or not. We expect you to develop an algorithm to predict the churn score based on usage pattern.

## Findings of EDA:
No missing values present in the dataset. As we see from the data, the state variable has 51 unique states encoded with 2 letter string of the state's name. Variables international plan and voice mail plan have yes/no as answers. The target variable Churn has true/false values. These variables contain labels so they need to be encoded. We use LabelEncoder to do that. We see that each phone number is unique for all observations, so we can remove it as it does not add any information to the data. Outliers were present in the data and were treated with the custom function which finds and treats outliers till there are no outliers left. The mean imputation technique took 3 iterations to completely remove the outliers from the data. Looking at the visualizations, we see that most numerical predictors have similar median value for churning and categorical predictors do have some effect on the target. Next we performed Feature Selection. We use correlation to find correlated numerical variables and remove one of them and for Categorical variables we'll use chi-square test to find association between categorical predictors and target.

## Models used:
##### Logistic Regression: The model was used for classifications twice, once without balancing the classes and once with class weights to balance the classes.

## Model Evaluation:
#### Logistic Regression
##### Unbalanced Classes: The iteration with no class weights assigned, the model had an accuracy of 87% but it had a large Flase Negative Rate of 88% which means that the classifier missed 88% of the customers who churned. This is a really bad classifier for the company as it misses 88% of the churning customers. 
##### Balanced Classes: To reduce the false negative rate, we used class weights to balance the classes. The model resulted had an accuracy of 71.8%  and a low Flase Negative Rate of 34.37%  and False Positive Rate of 27.2%.

## Conclusion:

Logistic Regression with balanced classes resulted in a better classifier for the as it had low FPR and FNR. I'll be trying more models on this data to find a better classifier.