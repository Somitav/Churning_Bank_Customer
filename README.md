
# 🏦 Customer Churn Prediction (Banking)

This project predicts **customer churn** (whether a customer will exit the bank) using statistical analysis and machine learning models.  

We analyze customer demographics, account activity, and product usage to identify churn drivers and build predictive models to reduce customer loss.

---

## 📂 Project Structure
```
├── data/
│   └── Bank_Churn.csv              # Dataset
├── notebooks/
│   ├── EDA_and_HypothesisTesting.ipynb
│   ├── LogisticRegression_Model.ipynb
│   └── XGBoost_Model.ipynb
├── models/
│   ├── logistic_regression.pkl
│   └── xgboost_model.pkl
├── README.md
└── requirements.txt
```

---

## 🎯 Objectives
- Perform **Exploratory Data Analysis (EDA)** and identify churn trends.
- Use **statistical hypothesis testing** to determine significant churn predictors.
- Build and evaluate machine learning models (**Logistic Regression** and **XGBoost**).
- Compare models to identify the best approach for predicting churn.

---

## 📊 Dataset Overview
| Feature                | Description                                  |
|------------------------|----------------------------------------------|
| CreditScore            | Customer's credit score                     |
| Geography              | Country of the customer                     |
| Gender                 | Male / Female                               |
| Age                    | Age of the customer                         |
| Tenure                 | Years with the bank                         |
| Balance                | Account balance                             |
| NumOfProducts          | Number of products purchased                |
| IsActiveMember         | Whether the customer is active (0/1)        |
| EstimatedSalary        | Estimated salary of the customer            |
| Exited (Target)        | 1 if customer churned, 0 if stayed          |

---

## 🔍 Statistical Hypothesis Testing
Performed tests to determine which features significantly affect churn:

| Feature           | Test Used                | Result (Significance)             |
|-------------------|------------------------|-----------------------------------|
| Geography         | Chi-square test         | ✅ Significant                    |
| Gender            | Chi-square test         | ✅ Significant                    |
| Age               | t-test / ANOVA          | ✅ Significant                    |
| Balance           | t-test / ANOVA          | ✅ Significant                    |
| NumOfProducts     | ANOVA                   | ✅ Significant                    |
| IsActiveMember    | Chi-square test         | ✅ Significant                    |
| CreditScore       | t-test                  | ✅ Significant                    |
| Tenure, Salary, Card Type, Points Earned | Various tests | ❌ Not significant |

**Conclusion:** `Age, Geography, Gender, Balance, NumOfProducts, IsActiveMember, CreditScore` are **key churn predictors**.

---

## 🧠 Models & Results

### 1️⃣ Logistic Regression
| Metric                  | Score |
|------------------------|-------|
| Accuracy               | 81%   |
| ROC-AUC                | 0.78  |
| Churn Recall (Class 1) | 20%   |

**Feature Odds Ratios:**  
`Geography_Germany > Age > Balance > IsActiveMember (negative) > Gender_Male (negative)`

---

### 2️⃣ XGBoost Classifier
| Metric                  | Score |
|------------------------|-------|
| Accuracy               | 80%   |
| ROC-AUC                | 0.87  |
| Churn Recall (Class 1) | 76%   |

**Top Features:**  
`NumOfProducts > IsActiveMember > Age > Geography_Germany > Gender > Balance > CreditScore`


---

## ⚙️ Tech Stack
- **Python**: pandas, numpy, matplotlib, seaborn
- **Scikit-learn**: Logistic Regression, metrics
- **XGBoost**: Gradient boosting model
- **SciPy/Statsmodels**: Hypothesis testing
- **Jupyter Notebook** for experimentation

---

## 🚀 How to Run
```bash
# Clone this repo
git clone https://github.com/Somitav/Churning_Bank_Customer.git
cd customer-churn-prediction

# Install dependencies
pip install -r requirements.txt


```

---

## 📌 Key Learnings
- **Statistical tests before modeling** help identify significant features.
- Logistic Regression gives **interpretability** (odds ratios).
- XGBoost significantly improves **recall for churners**.
- Predicting churn early can help businesses take **retention actions**.

---

