# Length of Stay (LOS) Forecasting

This project involves developing a predictive model for length of stay (LOS) using MIMIC-IV. The MIMIC-IV dataset (Medical Information Mart for Intensive Care IV) is a publicly available dataset that contains comprehensive and de-identified health-related data for critical care patients. It is widely used in the medical and machine learning communities for research in healthcare, particularly in areas like predictive modeling, clinical decision support, and patient outcome analysis. The goal is to enable healthcare providers to allocate resources more efficiently and manage patient care effectively.

## 1. Problem Statement

### 1.1 Objective
The primary objective of this project is to create a predictive model capable of identifying patients who are likely to stay in the hospital for seven or more days. Accurate predictions of LOS allow healthcare systems to optimize resource allocation, improve operational efficiency, and enhance patient outcomes.

### 1.2 Dataset Overview
The original dataset consists of 100,000 patient records and includes 28 features. It contains comprehensive information about patients, such as:
- Medical history
- Number of previous admissions
- Diagnostic codes
- Laboratory test results

These features provide the foundation for building and validating predictive models for LOS.

## 2. Data Preparation

### 2.1 Data Cleaning
The dataset was notably clean, containing no missing values. This eliminated the need for imputation or other data-filling techniques and allowed us to focus on feature engineering and modeling.

### 2.2 Data Transformation
To prepare the dataset for modeling, the following transformations were applied:
- **Encoding categorical variables**: The gender variable was encoded to a numerical format to ensure compatibility with machine learning algorithms.
- **Standardizing continuous variables**: Continuous laboratory measurements were standardized to ensure that all features were on a comparable scale, improving model convergence and performance.

## 3. Feature Engineering

Feature engineering was conducted to refine the dataset and improve the predictive power of the model:

- **Creation of the `number_of_issues` feature**:  
  A new feature was derived to represent the total number of medical conditions a patient had. This helped to consolidate information and reduced the number of input features by 11, simplifying the model.
- **Feature selection**:  
  Unnecessary features that did not significantly contribute to predicting LOS were removed.
- **Target variable transformation**:  
  A binary target variable was created to represent whether a patient’s LOS was greater than 7 days. This binary classification approach aligns with the project objective.

## 4. Model Development

Multiple machine learning models were tested to identify the best-performing approach for LOS prediction. Key steps included:

### 4.1 Data Splitting
- The dataset was split into training (80%) and testing (20%) subsets to evaluate model performance.
- A holdout validation set was considered to ensure robust evaluation.

### 4.2 Cross-Validation and Hyperparameter Tuning
- **5-Fold Cross-Validation**: This was employed to ensure model stability and prevent overfitting.
- **Random Search**: Hyperparameters were tuned using random search for each model type, optimizing performance metrics.

### 4.3 Models Tested
The following models were explored:
1. Logistic Regression
2. Support Vector Machines (SVM)
3. Random Forest
4. Gradient Boosting Machine (GBM)

## 5. Results

### 5.1 Performance Evaluation
Given the imbalanced nature of the dataset, tree-based methods outperformed other models due to their ability to handle complex feature interactions and class imbalance effectively. Evaluation metrics included:
- **ROC-AUC Score**: This was used as the primary metric to assess model performance.

### 5.2 Best Model
- **Gradient Boosting Machine (GBM)**:  
  GBM emerged as the best-performing model with the highest ROC-AUC score, demonstrating its ability to make accurate predictions even with an imbalanced dataset.

## 6. Conclusion

This project successfully developed a predictive model for hospital length of stay, providing actionable insights to improve healthcare management. By leveraging advanced machine learning techniques and rigorous evaluation, the GBM model offers a reliable tool for predicting extended patient stays, enabling better resource planning and patient care.
