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
- [Fraud Detection Handbook](https://fraud-detection-handbook.github.io/fraud-detection-handbook/Chapter_3_GettingStarted/SimulatedDataset.html), which includes a simulator and detailed methodologies for real-world credit card fraud detection.

## 🔮 Future Development: Deep Learning Roadmap

While the current approach leverages classical machine learning models (e.g., Logistic Regression, Random Forest, XGBoost), future iterations of this project will explore deep learning techniques inspired by the [Fraud Detection Handbook](https://fraud-detection-handbook.github.io/fraud-detection-handbook/Chapter_3_GettingStarted/SimulatedDataset.html). These approaches aim to better capture complex transaction patterns and improve generalization.

### 🚀 Planned Enhancements

- **Autoencoder for Anomaly Detection**
  - Train on non-fraudulent transactions only.
  - Use reconstruction error to flag anomalies.
  - Especially effective in extreme class imbalance scenarios.

- **Recurrent Models (e.g., LSTM)**
  - Model transaction sequences over time per user or card.
  - Detect temporal anomalies and behavioral shifts.

- **Tabular Deep Learning Models**
  - Implement architectures like TabNet or FT-Transformer that are designed for structured/tabular data.
  - Explore self-supervised pretraining for better representations.

- **Hybrid Stacking**
  - Combine classical model predictions (e.g., XGBoost) with deep features from autoencoders or transformers.
  - Use meta-learning for final fraud probability estimation.

- **Contrastive Learning & Siamese Networks**
  - Learn embeddings that distinguish fraudulent vs. normal transaction pairs.
  - Effective for downstream few-shot detection tasks.

### 📏 Evaluation Considerations

All deep learning extensions will adhere to the best practices emphasized in the Handbook:
- **Temporal validation** to prevent data leakage.
- Emphasis on **AUPRC**, **MCC**, and **cost-sensitive metrics** over accuracy.
- Careful hyperparameter tuning and model calibration.

---

We welcome contributions or suggestions on integrating these techniques into the pipeline.


