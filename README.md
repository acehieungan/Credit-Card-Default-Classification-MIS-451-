# Credit Card Default Classification MIS 451

This project aims to build and evaluate machine learning models to predict credit card default risk using the UCI "Default of Credit Card Clients" dataset. By analyzing customer demographic and payment behavior data, we attempt to classify clients into two categories: those likely to default and those not likely to default.

## Project Overview

| Item                        | Description                                |
|----------------------------|--------------------------------------------|
| Dataset Source             | UCI Machine Learning Repository             |
| Records                    | 30,000 credit card clients (Taiwan)        |
| Features                   | 23 variables + 1 binary target (default)    |
| Target Variable            | Default payment next month (0 or 1)         |
| Class Imbalance            | ~77% No Default, ~23% Default               |
| Tools Used                 | Python, Pandas, Scikit-learn, Keras         |
| Key Techniques             | EDA, Feature Engineering, SMOTE, Modeling   |

---

## Exploratory Data Analysis (EDA)

Initial analysis revealed a clear class imbalance and a few categorical anomalies. Key points include:

- **Most predictive features**: Recent payment delays (PAY_0, PAY_2, PAY_3)
- **Weak predictors**: Gender, Age, Education, Marital Status
- **No missing or duplicate values**
  

---

## Data Preprocessing

To prepare the data, we applied the following steps:

- **Invalid category handling**: Mapped undefined EDUCATION & MARRIAGE values to "others"
- **One-hot encoding**: Categorical features encoded to binary
- **Feature engineering**: Aggregated six-month bill/payment totals
- **Scaling**: Standardized features using `StandardScaler`
- **Balancing**: Applied SMOTE to training set to fix class imbalance

---

## 🧠 Models and Results

| Model                  | Accuracy | F1-Score (Default) | ROC-AUC |
|------------------------|----------|--------------------|---------|
| Logistic Regression    | 64%      | 0.44               | 0.7089  |
| Random Forest          | 78%      | 0.50               | 0.7356  |
| Support Vector Machine | 77%      | 0.52               | 0.7469  |
| MLP Neural Network     | **80%**  | **0.52**           | **0.7572** |

> 💡 The MLP Neural Network model delivered the best overall performance, especially in handling class imbalance and predicting minority cases.

---

## 💡 Key Insights

- Recent payment behavior is the strongest indicator of default risk.
- Complex models (Neural Networks, SVM) handle feature interactions better.
- Demographics have little standalone predictive power.
- Class balancing (SMOTE) is essential to avoid bias in predictions.

---

## Challenges & Solutions

| Challenge                      | Solution                                                              |
|-------------------------------|-----------------------------------------------------------------------|
| Class imbalance               | Used SMOTE to synthetically balance minority class                    |
| Irregular categorical values  | Grouped undefined values into “Others” to reduce noise                |
| Poor precision in base models | Tuned thresholds and selected better models (Random Forest, MLP)      |
| Feature scaling               | Standardized inputs for SVM and neural network compatibility           |

---

## References

UCI Machine Learning Repository. (n.d.). https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)

---

## Team Members

| Name                      | Student ID     |
|---------------------------|----------------|
| Nguyễn Thanh Giang        | 2132300593     |
| Bùi Gia Tuệ               | 2132300511     |
| Bùi Thị Thanh Thảo        | 2232300157     |
| Trần Tiến Thảo Hiếu Ngân  | 2032300513     |

---

## Conclusion

This project highlights the importance of proper preprocessing, model selection, and threshold tuning when working with imbalanced financial datasets. Our work not only improves default prediction but also deepens understanding of client behavior—a key asset for credit risk management.



