# credit-risk-machine-learning-analysis
Machine learning project analyzing two large credit risk datasets using data preprocessing, exploratory data analysis, Random Forest, and Logistic Regression to predict default risk, evaluate model performance, and generate business insights.

# Credit Risk Machine Learning Analysis

## Project Overview

This project presents a comparative machine learning analysis on two real-world credit risk datasets to predict borrower default probability. The complete workflow includes data exploration, preprocessing, feature engineering, visualization, model training, evaluation, feature importance analysis, and model comparison using Random Forest and Logistic Regression.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Plotly
- Matplotlib
- Scikit-learn
- Imbalanced-learn (SMOTE)

---

# Repository Structure

```
credit-risk-machine-learning-analysis/
│
├── Dataset1_Home_Credit_Implementation.ipynb
├── Dataset2_DeFi_Credit_Implementation.ipynb
├── Dataset_1_Result.png
├── Dataset_2_Result.png
└── README.md
```

---

# Dataset 1 : Home Credit Default Risk

Dataset Source:
https://www.kaggle.com/competitions/home-credit-default-risk/data

## Data Exploration

| Item | Value |
|------|-------|
| Dataset Shape | (307511, 123) |
| Numerical Features | 106 |
| Categorical Features | 17 |
| Duplicate Records | 0 |
| Features with Missing Values | 67 |

Target Distribution

- Loan Repaid (0): **282,686 (91.93%)**
- Loan Default (1): **24,825 (8.07%)**

---

## Data Preprocessing

- Removed features having excessive missing values.
- Filled remaining missing values.
- Encoded categorical variables.
- Removed 41 features.
- Final processed dataset shape:

**(307511, 82)**

Remaining Missing Values

**0**

---

## Train-Test Split

| Dataset | Shape |
|----------|--------|
| Training Features | (246008, 80) |
| Testing Features | (61503, 80) |

Training Target Distribution

- Class 0 : 226148
- Class 1 : 19860

---

## Data Balancing

SMOTE was applied to balance the minority class.

Balanced Training Dataset

- Class 0 : 226148
- Class 1 : 226148

Final Shape

**(452296, 80)**

---

## Models Used

- Random Forest Classifier
- Logistic Regression

---

## Random Forest Performance

| Metric | Score |
|---------|--------|
| Accuracy | **0.8463** |
| Precision | 0.1838 |
| Recall | 0.2628 |
| F1 Score | 0.2163 |
| ROC-AUC | 0.6967 |

Top Important Features

- EXT_SOURCE_3
- AMT_REQ_CREDIT_BUREAU_YEAR
- EXT_SOURCE_2
- NAME_EDUCATION_TYPE
- WEEKDAY_APPR_PROCESS_START

---

## Logistic Regression Performance

| Metric | Score |
|---------|--------|
| Accuracy | 0.6917 |
| Precision | 0.1594 |
| Recall | **0.6594** |
| F1 Score | **0.2567** |
| ROC-AUC | **0.7398** |

---

## Dataset 1 Conclusion

- Random Forest achieved the highest overall accuracy (**84.63%**).
- Logistic Regression achieved the highest Recall (**65.94%**) and ROC-AUC (**0.7398**).
- Logistic Regression was more effective at identifying loan default customers.

---

# Dataset 2 : DeFi Credit Scoring Dataset

Dataset Source:
https://huggingface.co/datasets/spectrallabs/credit-scoring-training-dataset

---

## Data Exploration

| Item | Value |
|------|-------|
| Dataset Shape | (442961, 78) |
| Numerical Features | 77 |
| Categorical Features | 1 |
| Duplicate Records | 7 |
| Missing Values | 0 |

Target Distribution

- Low Risk (0): **276,761 (62.48%)**
- High Risk (1): **166,200 (37.52%)**

---

## Data Preprocessing

- Removed wallet address feature.
- No missing values.
- No categorical encoding required.

Final Dataset Shape

**(442961, 77)**

---

## Exploratory Data Analysis

Key Insights

- Default wallets showed higher average risk factor.
- High-risk wallets experienced more liquidations.
- Wallet age was generally lower for high-risk borrowers.
- Borrow count was significantly higher among risky wallets.
- Risk factor showed the strongest correlation with the target variable.

Top Correlated Features

- risk_factor
- time_since_last_liquidated
- liquidation_count
- borrow_timestamp
- borrow_block_number

---

## Train-Test Split

| Dataset | Shape |
|----------|--------|
| Training Features | (354368, 76) |
| Testing Features | (88593, 76) |

Training Distribution

- Class 0 : 221408
- Class 1 : 132960

---

## Data Balancing

SMOTE Applied

Balanced Dataset

- Class 0 : 221408
- Class 1 : 221408

Final Shape

**(442816, 76)**

---

## Models Used

- Random Forest Classifier
- Logistic Regression

---

## Random Forest Performance

| Metric | Score |
|---------|--------|
| Accuracy | **0.8318** |
| Precision | **0.7999** |
| Recall | **0.7357** |
| F1 Score | **0.7665** |
| ROC-AUC | **0.8969** |

Top Important Features

- risk_factor
- max_risk_factor
- risk_factor_above_threshold_daily_count
- avg_risk_factor
- time_since_last_liquidated

---

## Logistic Regression Performance

| Metric | Score |
|---------|--------|
| Accuracy | 0.6799 |
| Precision | 0.6148 |
| Recall | 0.3932 |
| F1 Score | 0.4797 |
| ROC-AUC | 0.6703 |

---

## Dataset 2 Conclusion

- Random Forest outperformed Logistic Regression across all evaluation metrics.
- Highest ROC-AUC obtained was **0.8969**.
- Risk-related blockchain features were the strongest predictors of borrower risk.

---

# Overall Dataset Comparison

| Metric | Dataset 1 Best | Dataset 2 Best |
|---------|----------------|----------------|
| Dataset Size | 307,511 | **442,961** |
| Features | **123** | 78 |
| Best Accuracy | 0.8463 | 0.8318 |
| Best Precision | 0.1838 | **0.7999** |
| Best Recall | 0.6594 | **0.7357** |
| Best F1 Score | 0.2567 | **0.7665** |
| Best ROC-AUC | 0.7398 | **0.8969** |

---

# Final Observations

- Dataset 1 is a highly imbalanced traditional banking credit dataset where Logistic Regression demonstrated superior default detection despite lower accuracy.
- Dataset 2 is a blockchain-based credit scoring dataset where Random Forest achieved excellent predictive performance across all evaluation metrics.
- Risk-related financial indicators were the most influential features in both datasets.
- Random Forest performed best overall on Dataset 2 with a ROC-AUC of **0.8969**, while Logistic Regression provided better default detection capability on Dataset 1.

---

# Future Improvements

- Hyperparameter Optimization
- XGBoost and LightGBM Models
- Ensemble Learning
- Explainable AI (SHAP/LIME)
- Deep Learning-based Credit Risk Prediction

---

# M NITHIN SAI CHOWDARY

**Credit Risk Machine Learning Analysis**

Comparative study of traditional banking credit risk and decentralized finance (DeFi) credit scoring using machine learning.
