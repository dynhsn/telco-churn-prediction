# 📊 Telco Customer Churn Prediction

**Capstone Project — Data Science and Python Course**
Instructor: **Dayyan Hasan**

An end-to-end machine learning project that predicts whether a telecom customer is likely to churn (leave the company), built using Python, Pandas, and Scikit-Learn.

---

## 🎯 Problem Statement

Customer churn — when a customer stops using a company's service — directly hurts revenue. Acquiring a new customer typically costs far more than retaining an existing one. This project builds a classification model that identifies customers at high risk of churning, so a business can act *before* they leave, not after.

---

## 🗂️ Dataset

- **Name:** Telco Customer Churn
- **Source:** [Kaggle — blastchar/telco-customer-churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Size:** ~7,000 customer records, 21 columns
- **Target variable:** `Churn` (Yes / No)
- **Features:** Customer demographics, account information (tenure, contract type, payment method), and subscribed services (internet, streaming, tech support, etc.)

> The raw CSV is included in this repo (bur you can also see [Original_source](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)). Download it and place it in the project root — see **Setup** below.

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-Learn |
| Environment | Jupyter Notebook |

---

## 🔄 Project Workflow

1. **Exploratory Data Analysis (EDA)** — inspected shape, data types, missing values, churn distribution, and relationships between key features.
2. **Data Cleaning** — fixed the `TotalCharges` column (mis-typed as text), imputed missing values.
3. **Feature Engineering** — one-hot encoded categorical variables, scaled numeric features with `StandardScaler`.
4. **Model Training** — trained and compared:
   - Logistic Regression (baseline)
   - Decision Tree Classifier
5. **Bonus — Customer Segmentation** — applied K-Means clustering on tenure and monthly charges to explore natural customer segments.
6. **Model Evaluation** — compared models using Accuracy, Precision, Recall, and Confusion Matrices, with Recall prioritized as the key business metric (missing a churner is costlier than a false alarm).
7. **Feature Importance** — identified the strongest drivers of churn from the Decision Tree model.

---

## 📈 Key Results

| Model | Accuracy | Precision | Recall |
|---|---|---|---|
| Logistic Regression | `0.806` | `0.659` | `0.559` |
| Decision Tree | `0.794` | `0.631` | `0.54` |

**Top churn drivers:** *tenure, InternetService_Fiber optic, TotalCharges*

**Business insight:** *tenure biggest driver (~ 0.42 importance) — new customers churn most, long-tenure customers stay. Fiber optic internet close 2nd (~ 0.36) — fiber customers churn far more than DSL/no-internet, likely price or service quality issue. TotalCharges, Electronic check payment, MonthlyCharges also matter but much smaller weight. Two-year contract + TechSupport_Yes → lower churn risk (protective factors).")*

---

## 📁 Repository Structure

```
telco-churn-prediction/
│
├── Capstone_Telco_Churn_Project.ipynb   # Main notebook — full analysis & modeling
├── WA_Fn-UseC_-Telco-Customer-Churn.csv # Dataset (download separately, see below)
├── README.md                            # Project documentation
└── requirements.txt                     # Python dependencies
```

---

## ⚙️ Setup & How to Run

1. **Clone this repository**
   ```bash
   git clone https://github.com/<your-username>/telco-churn-prediction.git
   cd telco-churn-prediction
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Download the dataset**
   Get `WA_Fn-UseC_-Telco-Customer-Churn.csv` from [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) and place it in the project root folder.

4. **Launch the notebook**
   ```bash
   jupyter notebook Capstone_Telco_Churn_Project.ipynb
   ```

5. Run the cells in order — each section is explained with markdown notes as you go.

---

## 🚀 Future Improvements

- Try additional models (Random Forest, XGBoost) for comparison
- Perform hyperparameter tuning (GridSearchCV)
- Handle class imbalance with SMOTE or class weighting
- Deploy the model as a simple web app (Streamlit / Flask)

---

## 👤 Author

**Dayyan Hasan**
Instructor — Data Science and Python Course
*Feel free to connect or reach out with feedback!*

---

## 📄 License

This project is for educational purposes as part of the Data Science and Python course capstone.
