# 💳 Credit Card Fraud Detection Pipeline (SMOTE, ML Models, and Evaluation)

This project develops a complete end-to-end pipeline for detecting fraudulent credit card transactions using a highly imbalanced dataset. The process includes data preprocessing, SMOTE oversampling, training several classifiers, evaluating them rigorously, and exporting structured results for reporting or dashboards.

---

## 🔢 Dataset Overview

- **Source**: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Samples**: 284,807 transactions over 2 days
- **Frauds**: 492 (~0.172% of the data)
- **Features**:
  - 28 anonymized PCA components
  - `Amount` and `Time`
  - `Class` (Label: 1 = Fraud, 0 = Normal)

---

## 📊 Pipeline Architecture

The notebook follows a structured and interpretable modeling pipeline, inspired by the [Fraud Detection Handbook](https://fraud-detection-handbook.github.io/fraud-detection-handbook/Foreword.html):

### 1. 📦 Data Preprocessing
- Drop non-predictive fields (`Time`)
- Scale `Amount` using `StandardScaler`

### 2. ⚖️ Resampling Strategy
- **SMOTE** is applied on the training data to balance classes.
- No undersampling is used to avoid information loss.

### 3. 🤖 Model Training
Trained and compared using the same pipeline:
- Logistic Regression
- Random Forest
- XGBoost
- LightGBM
- CatBoost
- Optional: Ensemble stacking (planned)

### 4. 📏 Model Evaluation
Each model is evaluated using:
- Accuracy, Precision, Recall, F1-score
- ROC Curve & AUC
- Confusion Matrix

### 5. 📁 Output & Reporting
All outputs (predictions, metrics, AUC scores) are saved to:
```
Data/output/
```
This allows easy integration with reporting tools like Power BI or Streamlit dashboards.

---

## 📂 Key Files

- `CreditCard_Full_Modeling_Pipeline_mod_annotated.ipynb`: Fully annotated modeling notebook with markdown explanations before every step.
- `Data/output/`: Folder where all result `.csv` files are saved (metrics, predictions, AUC, etc.)
- `requirements.txt`: Environment setup

---

## 🚀 How to Run the Notebook

```bash
# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook CreditCard_Full_Modeling_Pipeline_mod_annotated.ipynb
```

---

## 📚 References

- Dal Pozzolo et al. (2015) – *Calibrating Probability with Undersampling*
- Carcillo et al. (2018) – *Scarff: Streaming Credit Card Fraud Detection*
- [Fraud Detection Handbook](https://fraud-detection-handbook.github.io/fraud-detection-handbook/Foreword.html) – Theory and practice behind many modeling choices here.

---

## 🔮 Future Development: Deep Learning Roadmap

While the current pipeline covers classical models and structured ML evaluation, we plan to introduce deeper modeling architectures, particularly suited for extreme imbalance and real-time behavioral tracking.

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

## 🙌 Contributions

Contributions, suggestions, and collaborations are welcome — especially around ensembling, tabular DL, or deployment integration.
