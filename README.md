# Financial Transaction Fraud Detection
An end-to-end Machine Learning portfolio project that builds a transaction-level fraud classifier, compares supervised and unsupervised algorithms, and exports predictions for a Power BI interactive dashboard.

## 📌 Project Overview
Fraud detection is a classic highly imbalanced classification challenge. This project implements a full ML pipeline using **Scikit-Learn** to handle preprocessing, model training, threshold tuning, and comparison between multiple classification techniques.

### Key Features Included:
* **Data Preprocessing:** Imputation and robust scaling (`RobustScaler`) to handle extreme outliers in financial values.
* **Supervised Classifiers:** Logistic Regression, Decision Tree, and Random Forest.
* **Unsupervised Anomaly Detection:** Isolation Forest.
* **Performance Optimization:** Threshold tuning utilizing Precision-Recall curves rather than standard ROC-AUC.
* **Dashboard Export:** Ready-to-use curated dataset (`fraud_predictions_powerbi.csv`) designed directly for Power BI visualization.

---

## 📊 Model Comparison & Results
Below is a summary of the models trained on the dataset:

* **Random Forest:** Offers high discriminative power (PR-AUC) but requires careful threshold tuning in highly imbalanced domains.
* **Decision Tree & Logistic Regression:** Adjusted with balanced class weights to maximize recall for catching critical fraud cases.
* **Isolation Forest:** Built completely unsupervised to flag anomalies without relying on prior fraud labels.

Results are saved in `outputs/model_comparison.csv`.

---

## 🛠️ How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/mutungu/fraud_detection.git
   cd fraud_detection
   ```
2. Install requirements:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn joblib
   ```
3. To use the real 284k transaction benchmark dataset instead of synthetic data, download the `creditcard.csv` from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) and place it in the `data/` directory.

---

## 🖥️ Power BI Dashboard Integration
Import `outputs/fraud_predictions_powerbi.csv` into Power BI to build:
1. **KPI Cards:** Displaying total transactions, flagged transactions, and actual fraud cases.
2. **Confusion Matrix:** Showing True Positives vs False Positives visually.
3. **Risk Level Distribution:** Grouped by Low, Medium, and High risk profiles.
