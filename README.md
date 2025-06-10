# :credit_card: Credit Card Default Classification MIS 451

This project aims to develop and evaluate machine learning models to predict credit card default risk, drawing from the UCI "Default of Credit Card Clients" dataset. Examining customer demographic profiles and payment habits allows us to classify clients into two groups: those at risk of defaulting and those not, providing valuable insights for business decision-making


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :rocket: Project Overview


| Item                        | Description                                |
|-----------------------------|--------------------------------------------|
| Dataset Source              | UCI Machine Learning Repository            |
| Records                     | 30,000 credit card clients (Taiwan)        |
| Features                    | 23 variables + 1 binary target (default)   |
| Target Variable             | Default payment next month (0 or 1)        |
| Class Imbalance             | ~77% No Default, ~23% Default              |
| Tools Used                  | Python, Pandas, Scikit-learn, Keras        |
| Key Techniques              | EDA, Feature Engineering, SMOTE, Modeling  |


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :bar_chart: Exploratory Data Analysis (EDA)


Initial findings highlight a clear class imbalance and some unusual categorical data. Key observations include:

- **Most predictive features**: Recent payment delays (PAY_0, PAY_2, PAY_3) 
- **Weak predictors**: Gender, Age, Education, Marital Status 
- **No missing or duplicate values**


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :gear: Data Preprocessing



To enhance data quality for analysis, we carefully applied these steps:

- **Invalid category handling**: Reassigned undefined EDUCATION & MARRIAGE values to "others" 
- **One-hot encoding**: Converted categorical features into binary format 
- **Feature engineering**: Summarized six-month bill and payment totals 
- **Scaling**: Used `StandardScaler` to standardize features 
- **Balancing**: Implemented SMOTE on the training set to correct class imbalance


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :chart_with_upwards_trend: Models and Results

| Model                  | Accuracy | F1-Score (Default) | ROC-AUC |
|------------------------|----------|--------------------|---------|
| Logistic Regression    | 64%      | 0.44               | 0.7089  |
| Random Forest          | 78%      | 0.50               | 0.7356  |
| Support Vector Machine | 77%      | 0.52               | 0.7469  |
| MLP Neural Network     | **80%**  | **0.52**           | **0.7572** |

> The MLP Neural Network model stood out, effectively managing class imbalance and accurately predicting rare default cases, making it a strong choice for business applications. :star2:


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :bulb: Key Insights


- Recent payment patterns serve as the most reliable indicators of default risk, crucial for timely interventions. 
- Advanced models (Neural Networks, SVM) better capture complex feature interactions, enhancing predictive power. 
- Demographic details alone offer limited predictive value, suggesting focus on behavioral data. 
- Class balancing with SMOTE is vital to ensure unbiased predictions, supporting fair risk assessment.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :hammer_and_wrench: Challenges & Solutions


| Challenge                      | Solution                                                              |
|-------------------------------|-----------------------------------------------------------------------|
| Class imbalance               | Applied SMOTE to artificially balance the minority class              |
| Irregular categorical values  | Grouped undefined values into “Others” to reduce data noise           |
| Poor precision in base models | Fine-tuned thresholds and selected top models (Random Forest, MLP)    |
| Feature scaling               | Standardized inputs for optimal SVM and neural network performance    |


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :books: References


  UCI Machine Learning Repository. (n.d.).  
  [https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)

  
-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## 👨‍👩‍👧‍👦 Team Members


| Name                      | Student ID     |
|---------------------------|----------------|
| Nguyễn Thanh Giang        | 2132300593     |
| Bùi Gia Tuệ               | 2132300511     |
| Bùi Thị Thanh Thảo        | 2232300157     |
| Trần Tiến Thảo Hiếu Ngân  | 2032300513     |


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


## :tada: Conclusion


This project highlights the importance of proper preprocessing, model selection, and threshold tuning when working with imbalanced financial datasets. Our work not only improves default prediction but also deepens understanding of client behavior—a key asset for credit risk management. :moneybag:



