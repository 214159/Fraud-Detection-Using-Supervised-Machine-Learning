# Fraud-Detection-Using-Supervised-Machine-Learning

## 📌 Project Overview
This project focuses on detecting fraudulent transactions using machine learning models.  
A synthetic dataset was generated to simulate transaction data because real-world fraud data is confidential. The goal is to train models that can accurately classify transactions as fraud or non-fraud and evaluate their performance using standard metrics.

---

## 🧩 Dataset
- Synthetic dataset created with features such as transaction amount, transaction gap, and number of previous transactions.  
- The dataset is **imbalanced**, with most transactions being non-fraudulent.  
- Training-test split: **75% training, 25% testing**.

---

## 🔧 Preprocessing
- Features were **scaled using StandardScaler** to normalize numerical variables, ensuring all features contribute equally to the model.  
- This improves convergence and performance for models like Logistic Regression.

---

## 🤖 Models Trained
### Model 1: Logistic Regression
- Trained on the scaled dataset.  
- Evaluated using confusion matrix, precision, recall, F1-score, and accuracy.

### Model 2: Random Forest
- Trained on the same dataset for a fair comparison.  
- Evaluated with the same metrics to assess performance.

---

## 📊 Model Evaluation
- **Confusion Matrix:** Shows the number of correct and incorrect predictions for each class (True Positives, True Negatives, False Positives, False Negatives).  
- **Classification Report:** Provides precision, recall, F1-score, and support for each class.  

**Logistic Regression:**
- High recall for fraud cases, but low precision (0.04) indicating some false positives.  
- Accuracy overall: 0.99.  

**Random Forest:**
- Perfect performance for both fraud and non-fraud classes (precision, recall, F1-score = 1).  
- Accuracy: 1.0.  

---

## 🔍 Insights
- The dataset is highly imbalanced, making fraud detection challenging.  
- Logistic Regression identifies most frauds but has low precision, while Random Forest detects all fraud and non-fraud transactions accurately.  
- Random Forest is the most effective model and is ideal for deployment in real-world scenarios.

---

## ✅ Conclusion
Random Forest outperforms Logistic Regression in this project, achieving perfect metrics across all classes. This demonstrates the importance of selecting robust models for imbalanced datasets and shows how machine learning can be applied to fraud detection in real-world scenarios.

---

## 📈 Future Work
- Experiment with other ensemble models for performance comparison.  
- Extend the project for real-time transaction monitoring.  
- Explore more feature engineering for better fraud detection accuracy.

---

## 📂 Repository Structure
