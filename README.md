# Credit Card Fraud Detection – SMOTE, Undersampling, and Model Evaluation

This project explores fraud detection using real-world credit card transaction data. The dataset is highly imbalanced, with fraudulent transactions comprising just 0.172% of the data.

## 🔍 Dataset
- **Source**: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Transactions**: 284,807 over 2 days
- **Fraud cases**: 492
- **Features**: 28 PCA components + Time + Amount
- **Label**: `Class` (1 = fraud, 0 = normal)

## ⚙️ Techniques Used

- **Standardization** of `Amount` and `Time`
- **Resampling**:
  - `RandomUnderSampler` for logistic regression
  - `SMOTE` for Random Forest, XGBoost, and LightGBM
- **Modeling**:
  - Logistic Regression
  - Random Forest
  - XGBoost (with GridSearchCV)
  - LightGBM (with GridSearchCV)
- **Evaluation Metrics**:
  - Precision-Recall Curve (AUPRC)
  - F1 Score
  - Confusion Matrix & Classification Report

## 📈 Key Outputs

- Comparison of F1-score and AUPRC across all four models
- Precision-Recall curves for each approach

## 📂 Files

- `fraud_detection_modeling.ipynb`: Main notebook
- `requirements.txt`: Environment setup

## 🚀 How to Run

1. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

2. Run the notebook:  
   ```bash
   jupyter notebook fraud_detection_modeling.ipynb
   ```

## 📚 References

- Dal Pozzolo et al. (2015) *Calibrating Probability with Undersampling*
- Carcillo et al. (2018) *Scarff: a scalable framework for streaming credit card fraud detection*
- [Fraud Detection Handbook](https://fraud-detection-handbook.github.io)

