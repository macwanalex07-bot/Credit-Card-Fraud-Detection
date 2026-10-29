# Summary Report: Credit Card Fraud Detection

## 1. Business Problem and Accuracy Limitation

The objective of this project is to identify fraudulent credit-card transactions while limiting unnecessary alerts on legitimate customers. The dataset is highly imbalanced: fraudulent transactions represent only a very small proportion of all transactions. In this situation, accuracy alone can be misleading. A model that predicts every transaction as legitimate could achieve very high accuracy while failing to detect any fraud. Therefore, this project evaluates fraud-class Precision, Recall, F1-score, and Precision–Recall AUC (PR-AUC), with special attention to how many fraud cases are detected and how many legitimate transactions are incorrectly flagged.

## 2. Imbalance Handling Strategy

The practical compares three approaches: the original imbalanced training set with `class_weight='balanced'`, SMOTE oversampling, and random undersampling. The original strategy keeps all available training records and increases the penalty for mistakes on the minority fraud class. SMOTE creates synthetic minority-class examples, while undersampling reduces the number of legitimate examples. The best Logistic Regression strategy should be selected from the executed comparison table using PR-AUC, rather than assumed in advance. All resampling is applied only to training data; the test set remains unchanged for evaluation.

## 3. Model and Threshold Recommendation

The project compares Logistic Regression, Random Forest, baseline XGBoost, and tuned XGBoost. XGBoost is tuned using `RandomizedSearchCV` with average precision as the scoring metric. The default threshold of 0.5 is compared with an F1-optimal threshold and a threshold intended to achieve Recall of at least 0.90. The recommended model and threshold should be selected using the actual results in the notebook. If the business prioritises catching at least 90% of fraud, the recall-target threshold may be appropriate if its precision and investigation workload are acceptable. Otherwise, the F1-optimal threshold provides a balanced starting point. The final threshold and metrics must be copied from the executed notebook rather than guessed.

## 4. Cost–Benefit Analysis

The practical assumes an average fraudulent transaction value of ₹4,500 and an investigation cost of ₹150 for each flagged transaction. Money saved is calculated as `TP × ₹4,500`; investigation cost as `(TP + FP) × ₹150`; money lost as `FN × ₹4,500`; and net benefit as money saved minus investigation cost. Insert the actual values from Step 7 into this section: **Net benefit per 50,000 transactions: ₹[enter the value produced by your notebook]**. This is an estimate under the exam's assumptions, not a guarantee of real-world savings. The business-optimal threshold may differ from the F1-optimal threshold because the costs of missed fraud and false alarms are different.

## 5. Production Improvements

For production use, the model should be integrated into a low-latency scoring service that evaluates transactions as they occur. Monitoring should track PR-AUC, precision, recall, false-positive rates, data quality, and changes in transaction patterns. Model drift alerts can identify when fraud behaviour changes and retraining may be needed. Confirmed fraud outcomes and investigator feedback should be collected in a controlled feedback loop for future model improvement. Thresholds should be validated on a separate validation set and reviewed with risk and operations teams before final testing and deployment. Access to transaction data and saved model files should also be restricted appropriately.

---

**Author:** Macwan Alex David

**Project:** Credit Card Fraud Detection — Supervised Learning Set C

**Note:** Replace the bracketed net-benefit value and add your final model name, optimal threshold, and measured metrics from the executed notebook before submission.
