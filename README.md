Telco Customer Churn Prediction

This project aims to predict customer churn in the telecommunications industry using a real-world dataset. Churn refers to customers who cancel their subscription, which is a major concern for companies due to lost revenue and increased acquisition costs.

---

## 🎯 Objective

- Identify customers at risk of churn
- Understand key drivers of churn behavior
- Provide actionable insights to support retention strategies
- Build and evaluate predictive models using machine learning

---

## 📂 Dataset

- Source: IBM Sample Telco Dataset
- Rows: ~7,000 customers
- Target: `Churn` (Yes/No)
- Features include:
  - Demographics: gender, senior citizen, etc.
  - Services: internet, contract type, etc.
  - Charges: monthly and total
  - Tenure and contract details

---

## 🔧 Step-by-Step Workflow

### 🧼 1. Data Cleaning

- Converted `TotalCharges` from object to numeric
- Dropped rows with missing values (`NaN`)
- Removed irrelevant column: `customerID`
- Encoded target variable: `Churn` → 1 for Yes, 0 for No

### 📊 2. Exploratory Data Analysis (EDA)

- Visualized churn distribution (26.5% churn rate)
- Analyzed patterns in tenure, monthly charges, contract type
- Discovered:
  - Customers with monthly contracts and short tenure churn more
  - Higher monthly charges also correlated with higher churn

### 🔄 3. Data Preprocessing (Refine Data)

- Applied one-hot encoding for categorical features
- Scaled numerical features using `StandardScaler`
- Split data into training (80%) and test (20%) sets
- Prepared `X_train`, `X_test`, `y_train`, and `y_test`

---

## 🧪 4. Model Building & Evaluation

### ✅ Logistic Regression
- Base model, interpretable
- Accuracy: 80%
- F1-score (Churn class): **0.61**
- ROC AUC: 0.836

### 🌳 Random Forest
- Non-linear, more flexible
- Accuracy: 79%
- F1-score (Churn class): 0.56
- ROC AUC: 0.816

> Logistic Regression performed better overall in both recall and F1-score for churn detection.

---

## 🔍 5. Cross-Validation (5-Fold)

| Model               | Mean F1 | Std Dev |
|---------------------|---------|---------|
| Logistic Regression | 0.598   | 0.0187  |
| Random Forest       | 0.548   | 0.0178  |

> Logistic Regression showed higher and more consistent performance.

---

## 🛠️ 6. Model Refinement (Hyperparameter Tuning)

### Best Parameters Found:

- **Logistic Regression**: `C=1`, `solver=liblinear`
- **Random Forest**: `max_depth=10`, `n_estimators=100`, `bootstrap=True`

Final Test Results:

| Model               | Final F1 | Recall (Churn) |
|---------------------|----------|----------------|
| Logistic Regression | **0.61** | **0.57**        |
| Random Forest       | 0.56     | 0.51            |

---

## ✅ Conclusion

Logistic Regression was selected as the final model due to:
- Better recall and F1-score on test data
- Stable performance during cross-validation
- Easier to interpret and explain to stakeholders

> With this model, the company can detect over 57% of potential churns and take early retention actions such as discounts, better contract options, or customer service interventions.

---

## 🚀 Next Steps

- Deploy model into CRM system for real-time scoring
- Visualize churn risk in dashboard (Looker/Tableau)
- Design marketing campaign based on churn probability

---

## 🙌 Author

**Muhammad Rahman Shiddiq**  
_Data Analyst & Machine Learning Enthusiast_  
[LinkedIn](www.linkedin.com/in/rahmanshiddiq) | [GitHub]([https://github.com/](https://github.com/rahmanS1d1q))

