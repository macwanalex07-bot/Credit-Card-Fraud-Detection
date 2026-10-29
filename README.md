# Credit Card Fraud Detection Using Supervised Learning

## 1. Project Overview

Credit Card Fraud Detection is a machine learning project that identifies fraudulent credit card transactions using supervised learning algorithms. The main objective is to distinguish legitimate transactions from fraudulent transactions and reduce financial losses caused by fraud.

This project uses Python, data analysis, data visualization, and machine learning techniques to build and evaluate fraud detection models.

## 2. Objectives

- Analyze credit card transaction data.
- Identify patterns in fraudulent and legitimate transactions.
- Handle the class imbalance problem.
- Train and compare multiple machine learning models.
- Evaluate models using precision, recall, F1-score, and PR-AUC.
- Select an appropriate classification threshold.
- Estimate the financial impact of fraud detection.
- Save the trained model for future predictions.

## 3. Dataset

Dataset Name: Credit Card Fraud Detection

Dataset Source: Kaggle

Dataset Link: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains transaction details and a target column named `Class`.

- Class = 0: Legitimate transaction
- Class = 1: Fraudulent transaction

The dataset includes `Time`, `Amount`, anonymized features `V1` to `V28`, and the target variable `Class`.

The dataset is highly imbalanced because legitimate transactions greatly outnumber fraudulent transactions.

## 4. Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn
- XGBoost
- Joblib

## 5. Project Workflow

### Step 1: Problem Framing

Define the fraud detection problem, understand the business requirements, and identify the importance of detecting fraudulent transactions.

### Step 2: Exploratory Data Analysis

- Load and inspect the dataset.
- Check missing values and data distributions.
- Analyze the number of legitimate and fraudulent transactions.
- Compare transaction amounts and transaction times.
- Visualize relationships between selected features.

### Step 3: Feature Engineering and Preprocessing

- Create a log-transformed transaction amount feature.
- Extract an hour feature from transaction time.
- Scale the selected features.
- Split the data into training and testing sets using stratification.
- Apply techniques to handle class imbalance.

### Step 4: Logistic Regression and Random Forest

Train Logistic Regression models using different class imbalance strategies.

Train a Random Forest classifier and evaluate its performance using fraud precision, fraud recall, F1-score, and PR-AUC.

### Step 5: XGBoost and Threshold Optimization

Train an XGBoost model and tune its hyperparameters.

Compare the baseline and tuned models. Optimize the classification threshold to balance fraud detection and false alarms.

### Step 6: Model Comparison

Compare the trained models using suitable evaluation metrics. Select a model based on fraud detection performance and business requirements rather than accuracy alone.

### Step 7: Cost-Benefit Analysis

Estimate the financial impact of model predictions using the following assumptions:

- Cost of an undetected fraudulent transaction: ₹4,500
- Cost of investigating a flagged transaction: ₹150

Calculate the estimated savings, investigation costs, losses from missed fraud, and net benefit according to the project's cost-benefit formula.

### Step 8: Model Saving and Reporting

Save the selected model and required preprocessing components using Joblib. Reload the saved model and test it on sample transactions.

Prepare a summary report containing the project objectives, methodology, evaluation results, limitations, and recommendations.

## 6. Evaluation Metrics

### Precision

Precision measures the proportion of transactions predicted as fraud that are actually fraudulent.

### Recall

Recall measures the proportion of actual fraudulent transactions correctly identified by the model.

### F1-Score

The F1-score is the harmonic mean of precision and recall.

### PR-AUC

Precision-Recall Area Under the Curve measures the trade-off between precision and recall across different classification thresholds. It is particularly useful for highly imbalanced datasets.

### Confusion Matrix

A confusion matrix summarizes correct and incorrect predictions using true positives, true negatives, false positives, and false negatives.

## 7. Installation

Install the required libraries using:

    pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost joblib jupyter

Download the dataset from Kaggle and place `creditcard.csv` in the appropriate project directory.

Open the Jupyter Notebook and execute the project steps in order.

## 8. Expected Outcome

The project aims to develop a machine learning model that can identify potentially fraudulent credit card transactions. Comparing different algorithms and imbalance-handling techniques helps determine a suitable model for the dataset.

Actual model performance must be reported using the results obtained from running the notebook.

## 9. Suggested Project Structure

Credit-Card-Fraud-Detection/

    README.md
    requirements.txt
    creditcard.csv
    Fraud_Detection.ipynb
    fraud_detection_model.pkl
    summary_report.md

Note: Include only files that actually exist in the repository. The dataset and trained model may be kept outside GitHub if they are too large or contain sensitive information.

## 10. Limitations

- The dataset contains anonymized transaction features.
- The dataset has a severe class imbalance.
- Model performance depends on the data, preprocessing, and classification threshold.
- False positives may affect legitimate customers.
- Fraud patterns can change over time, so real-world systems require monitoring and retraining.

## 11. Conclusion

Credit Card Fraud Detection demonstrates how supervised machine learning can be used to identify suspicious transactions. By applying exploratory data analysis, feature engineering, class imbalance handling, model training, and appropriate evaluation metrics, the project compares different approaches to fraud detection.

The final model should be selected based on measured performance, the cost of missed fraud, and the cost of investigating legitimate transactions incorrectly flagged as fraudulent.

## 12. Author

Macwan Alex David

Project: Credit Card Fraud Detection Using Supervised Learning

GitHub Repository: https://github.com/macwanalex07-bot/Credit-Card-Fraud-Detection.git

## Disclaimer

This project is intended for educational and academic purposes. Its predictions should not be used as the sole basis for real financial decisions without additional validation, security controls, and professional review.
