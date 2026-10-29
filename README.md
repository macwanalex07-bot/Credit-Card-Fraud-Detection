💳 Credit Card Fraud Detection
Author: Macwan Alex David
Project Type: Machine Learning / Supervised Learning
Repository: https://github.com/macwanalex07-bot/Credit-Card-Fraud-Detection
📌 Project Overview
Credit Card Fraud Detection is a supervised machine-learning project that identifies potentially fraudulent transactions from transaction data. Fraud is a highly imbalanced classification problem: legitimate transactions greatly outnumber fraudulent ones. For that reason, this project evaluates models using fraud-class Precision, Recall, F1-score, and Precision–Recall AUC (PR-AUC), rather than relying on accuracy alone.

The project follows the practical workflow for loading and sampling data, exploratory analysis, feature engineering, scaling, imbalance handling, model training, hyperparameter tuning, threshold optimisation, cost-benefit analysis, and saving a final model pipeline.
🎯 Objectives
- Explore transaction data and measure the class imbalance.
- Engineer features from transaction Time and Amount.
- Compare methods for handling class imbalance.
- Train and evaluate Logistic Regression, Random Forest, and XGBoost models.
- Tune XGBoost hyperparameters using cross-validation.
- Optimise the fraud classification threshold.
- Compare models using fraud-class Precision, Recall, F1-score, and PR-AUC.
- Estimate business costs and benefits using the assumptions in the practical.
- Save a model pipeline for reuse.
📊 Dataset
Dataset: Credit Card Fraud Detection
Source: Kaggle — https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains anonymised transaction features, including PCA-transformed features V1–`V28`, plus Time, Amount, and the target column Class.
- Class = 0: Legitimate transaction
- Class = 1: Fraudulent transaction
Download the dataset from Kaggle and place the CSV file in the project folder. Update the path in the notebook if your CSV has a different filename. The dataset is not included in this repository unless it has been separately added.
🧰 Technologies and Libraries
- Python
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- imbalanced-learn (SMOTE and random undersampling)
- XGBoost
- Joblib
- Jupyter Notebook
🔍 Project Workflow
1. Problem Framing and Exploratory Data Analysis
- Load the dataset and inspect its shape and descriptive statistics.
- Check the fraud/legitimate class distribution.
- Explore Time and Amount.
- Plot class counts, distributions, and feature correlations.
2. Feature Engineering and Scaling
- Create Amount_log = log1p(Amount).
- Derive Hour from Time using the notebook's specified formula.
- Remove the original Time and Amount columns after feature creation.
- Apply StandardScaler to Amount_log and Hour; the PCA features are already scaled.
3. Train-Test Split and Imbalance Handling
- Use a stratified 80/20 train-test split.
- Compare the original imbalanced training set, SMOTE oversampling, and random undersampling.
- Apply resampling to training data only; leave the test set unchanged.
4. Model Training
- Logistic Regression on the original, SMOTE, and undersampled training sets.
- Random Forest using the selected imbalance strategy.
- Baseline XGBoost with class imbalance weighting.
- XGBoost hyperparameter tuning with RandomizedSearchCV, three-fold cross-validation, and average precision scoring.
5. Threshold Optimisation
- Compare the default classification threshold of 0.5 with an F1-optimal threshold.
- Find a threshold that achieves Recall of at least 0.90, when possible.
- Compare Precision, Recall, F1-score, and PR-AUC.
6. Business Cost-Benefit Analysis
The practical uses these assumptions:
- Average fraudulent transaction value: ₹4,500
- Investigation cost per flagged transaction: ₹150
- Money saved = TP × ₹4,500
- Investigation cost = (TP + FP) × ₹150
- Money lost = FN × ₹4,500
- Net benefit = Money saved − Investigation cost
These are educational assumptions, not a guarantee of real-world financial outcomes.
7. Saving the Model
The notebook saves a Joblib .pkl model artifact and demonstrates loading it to predict a sample of transactions. Use the exact input columns and preprocessing expected by the saved pipeline.
📈 Evaluation Metrics
Metric	Meaning
Precision (Fraud)	Of transactions flagged as fraud, the proportion that are truly fraudulent
Recall (Fraud)	Of actual fraud transactions, the proportion detected
F1-score (Fraud)	Harmonic mean of fraud precision and recall
PR-AUC / Average Precision	Summarises precision–recall performance across thresholds
Confusion matrix	Counts true positives, false positives, true negatives, and false negatives


Why not accuracy alone? A model can obtain high accuracy by predicting almost every transaction as legitimate while missing fraud. Precision–Recall metrics give a more useful view of minority-class detection.
⚙️ Installation
Use Python 3.10 or a compatible version supported by the installed packages.
1. Clone this repository:
   git clone https://github.com/macwanalex07-bot/Credit-Card-Fraud-Detection.git
   cd Credit-Card-Fraud-Detection
2. Install dependencies:
   pip install -r requirements.txt
   If requirements.txt is not yet in the repository, install the main packages with:
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost joblib jupyter
3. Download creditcard.csv from the Kaggle dataset page and place it in the project directory, or update the notebook's dataset path.
▶️ How to Run
1. Open the repository folder in Jupyter Notebook or JupyterLab.
2. Open the fraud-detection .ipynb notebook.
3. Verify the CSV path in the data-loading cell.
4. Run the notebook cells in order, from data loading through model evaluation and saving.
5. Review the printed class distributions, comparison tables, plots, selected threshold, and cost-benefit calculations.
6. Confirm that the model artifact was saved successfully.
If the notebook has a different filename in the repository, open the .ipynb file that contains the full practical workflow.
📁 Suggested Repository Structure
Credit-Card-Fraud-Detection/
├── README.md
├── requirements.txt
├── summary_report.md
├── fraud_detection_model.pkl
├── creditcard.csv                 # Download separately; do not commit sensitive data
└── FraudDetection_SupervisedLearning.ipynb
The exact notebook and model filenames may differ. Keep the README aligned with the files actually present in the repository.
🛡️ Limitations and Future Improvements
- Select thresholds on a validation set and reserve the test set for final evaluation.
- Evaluate performance on newer transaction data and monitor model drift.
- Track false-positive workload as well as missed-fraud rates.
- Add a feedback loop using confirmed fraud outcomes and analyst reviews.
- Consider real-time scoring, latency monitoring, model versioning, and secure access controls.
- Reassess the cost assumptions with actual business data before production deployment.
👤 Author
Macwan Alex David

GitHub: https://github.com/macwanalex07-bot
⚠️ Disclaimer
This project is intended for educational purposes and supervised-learning practical work. The model and cost calculations should be independently validated before any real financial decisions or production deployment.
