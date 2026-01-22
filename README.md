# 💳 Fraud Detection using Supervised Machine Learning

## 📌 Project Overview
fraud detection is a high-risk, low-frequency problem where fraudulent transactions form a very small percentage of total activity. Missing even a single fraud can lead to significant financial loss, while excessive false alerts can harm customer trust.

This project simulates realistic transaction behavior using synthetic data and applies supervised machine learning models to detect fraudulent transactions under extreme class imbalance, focusing on recall, precision, and business impact rather than misleading accuracy alone.


## 📊 Dataset Description

- Dataset Type: Synthetic (used due to confidentiality of real financial data)
- Total Transactions: 7,000
- Fraud Rate: Extremely rare (<1%)
- Objective: Binary classification
  - 0 → Non-Fraud
  - 1 → Fraud

Synthetic data allows safe experimentation while closely mimicking real-world fraud patterns.

## 📋 Dataset Columns

| Column | Description |
|------|------------|
| user | Unique user identifier |
| Transaction_Amount | Transaction amount (₹), generated using exponential distribution |
| Transaction_Gap | Time gap (minutes) since previous transaction |
| Account_age_days | Account age in days |
| Num_prev_txns | Number of previous transactions |
| Fraud | Target variable (1 = Fraud, 0 = Non-Fraud) |


## 🧠 Fraud Label Generation Logic

Fraud labels were created using domain-inspired rules to simulate real fraud behavior.

A transaction is marked as fraudulent if all of the following conditions are met:

- Transaction_Amount > 4000
- Transaction_Gap < 3
- Num_prev_txns < 6

This represents high-value transactions, rapid transaction attempts, and new or low-activity accounts.

## 🔍 Exploratory Data Analysis (EDA)

### Data Quality
- Missing values: 0%
- Duplicate records: 0%

### Distribution Analysis
- Transaction amounts show positive skewness
- Exponential distributions reflect real financial behavior
- Log transformation applied to reduce skew and stabilize learning

### Class Imbalance
- Fraud transactions account for <1% of data
- Confirms a highly imbalanced classification problem

## ⚙ Data Preprocessing

- Feature scaling applied using StandardScaler
- Target variable excluded from scaling
- Train–test split used to avoid data leakage
- Random seed fixed for reproducibility

## 🤖 Models Implemented

### Logistic Regression (Class-Weighted)
- class_weight = 'balanced'
- Chosen for interpretability and strong baseline performance on imbalanced data

### Random Forest Classifier
- Ensemble-based model
- Captures non-linear relationships between transaction features

## 📈 Model Performance

### Logistic Regression Results

- Non-fraud correctly classified: ~98.5%
- Fraud recall: 100%
- Higher false positives due to aggressive fraud detection

Key Metrics:
- Accuracy: ~99%
- Precision (Fraud): Low
- Recall (Fraud): 100%
- F1-Score (Fraud): Low–Moderate

This model is suitable as a high-recall screening system.


### Random Forest Results

- Non-fraud correctly classified: 100%
- Fraud correctly detected: 100%
- False positives: 0
- False negatives: 0

Key Metrics:
- Accuracy: 100%
- Precision (Fraud): 100%
- Recall (Fraud): 100%
- F1-Score (Fraud): 100%

These results are influenced by the very small number of fraud samples and require validation on larger datasets.

## 💼 Business Impact Analysis

- False Negatives (Missed Fraud):
  - Direct financial loss
  - Regulatory and reputational risk

- False Positives (False Alerts):
  - Customer inconvenience
  - Increased operational cost

Recommended approach:
- Logistic Regression as first-level alert system
- Random Forest as secondary verification layer


## 🚀 Key Insights

- Extreme class imbalance strongly affects model evaluation
- Recall is more important than accuracy in fraud detection
- Rule-based logic combined with ML improves realism

## ⚠ Limitations

- Synthetic data may not capture all real-world fraud patterns
- Very small fraud sample size limits generalization
- Perfect accuracy does not imply production readiness

## 🔮 Future Improvements

- Apply SMOTE or oversampling techniques
- Perform cross-validation
- Tune classification thresholds based on business cost
- Add behavioral and temporal features

## ✅ Conclusion

This project demonstrates an end-to-end fraud detection workflow, from realistic data simulation to model evaluation and business interpretation. It highlights the importance of using domain-aware metrics rather than accuracy alone.


---
