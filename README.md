# LOS_forecasting
In this project, I develop a predictive model for length of stay (LOS) using the hospital dataset provided by Microsoft

## 1.1 Problem Statement
The goal of this project is to develop a predictive model that would be used to predict patients who will likely stay seven or more days in the hospital. Accurate predictive models help healthcare providers in resource allocation and patient management. 
## 1.2 Dataset
Original Data set contained 100,000 patients with 28 features.The dataset used in this analysis contains information about patients, including medical history, number of previous admissions as well as various diagnostic codes and lab results.
## 2.1 Data Cleaning
The dataset was free of missing values. 
## 2.2 Data Transformation
After checking for missing values we then examined our variables to identify variables that would require some sort of transformation for our model. We decided to use an encoder to encode the gender variable along with standardizing our continuous laboratory measurements.
## 3. Feature Engineering
 In this set of our model development we decided to create a new variable called “number_of_issues” that would represent the total number of medical conditions . By doing this we were able to reduce the number of features for our regressor by 11 features. In this step we also removed unnecessary features that were not important when it came to predicting the length of stay. Also in this step we create a binary variable to represent length of stay greater than 7 as this is what we will be using our remaining features to predict. 
## 4. Model Building
In this section, we run multiple ML models and we split and we use an 80% training and 20% testing split for our dataset. We considered adding a hold Each model is 5-fold cross-validated and a random search is run through each model type to explore and find the best hyperparameters. The models we used were Logistic Regression, SVM, Random Forest, and GBM.

## 5 Results 
We found the tree based methods were the best performing models given the data set since it is highly imbalanced. Using ROC-AUC we found that GBM performed the best.
