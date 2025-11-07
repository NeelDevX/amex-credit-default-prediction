# Amex Credit Default Prediction

End-to-end **Machine Learning project** on American Express credit default prediction — featuring memory-efficient data loading, advanced feature engineering, and model development using **XGBoost** and **LightGBM**.

---

## Project Overview

This project predicts the **probability of customer credit default** using the **American Express (Amex) dataset**.  
It demonstrates the complete lifecycle of an ML project — from large-scale data preprocessing to feature engineering and model training — optimized for handling millions of records efficiently.

---

## 🎯 Objectives

- Predict whether a customer will default on their credit payments.
- Design a scalable ML pipeline for large datasets.
- Optimize model accuracy and interpretability for real-world credit risk applications.

---

## Dataset

- **Source:** [American Express Default Prediction Dataset (Kaggle)](https://www.kaggle.com/competitions/amex-default-prediction)
- **Files used:**
  - `train_data.csv`
  - `train_labels.csv`
- **Size:** ~20M+ rows (loaded in chunks for efficiency)

### Data Highlights:

- **Customer_ID:** Unique identifier per customer.
- **S_2:** Statement date (converted to datetime).
- **Target:** 1 → customer defaulted, 0 → no default.
- **Categorical Columns:** `B_30, B_38, D_114, D_116, D_117, D_120, D_126, D_63, D_64, D_66, D_68`

---

## ⚙️ Data Preprocessing Pipeline

1. **Chunked Data Loading:**  
   Loaded CSV files in chunks of 100,000 rows to handle large data efficiently.

2. **Data Sampling:**  
   Randomly sampled 20% of data (`frac=0.2`) for rapid experimentation.

3. **Merging:**  
   Merged `train_labels` with `train_data` using `customer_ID`.

4. **Feature Engineering:**

   - Converted `S_2` to datetime.
   - One-hot encoded key categorical variables.
   - Dropped unnecessary columns (`S_2`, `customer_ID`, `target`) from feature list.

5. **Exported Processed Data:**  
   Saved merged and preprocessed data to `merged_sample_data.csv` for downstream modeling.

---

## 🧠 Machine Learning Pipeline

> _(This section describes typical workflow steps implemented or planned in subsequent notebooks.)_

- **Feature Scaling:** Standardization/Normalization for numerical columns.
- **Model Training:** Gradient boosting algorithms — **XGBoost**, **LightGBM**, and **CatBoost**.
- **Evaluation Metrics:**
  - ROC-AUC
  - American Express custom metric (weighted Gini coefficient)
- **Hyperparameter Tuning:** Grid search / Optuna for model optimization.
- **Model Interpretation:** Feature importance visualization and SHAP analysis.

---

## 🧰 Tech Stack

| Category            | Tools                                                      |
| :------------------ | :--------------------------------------------------------- |
| **Language**        | Python                                                     |
| **Libraries**       | pandas, scikit-learn, numpy, xgboost, lightgbm, matplotlib |
| **Data Handling**   | Chunked loading via `pandas.read_csv(chunksize=10**5)`     |
| **Environment**     | Jupyter Notebook                                           |
| **Version Control** | Git & GitHub                                               |

---

## 🧑‍💻 Author

**Neelkumar Kalavadiya**  
M.S. in Business Analytics & AI @ UT Dallas  
💼 Data & AI Engineer | Python | SQL | PySpark | Azure | Databricks | Snowflake  
🔗 [LinkedIn](https://www.linkedin.com/in/neelkumarkalavadiya)

---

## 🌟 Future Improvements

- Implement model ensemble and stacking.
- Add real-time scoring API using FastAPI or Streamlit.
- Deploy model pipeline on Azure Databricks / MLflow for experiment tracking.

---

## 🏁 How to Run Locally

```bash
# Clone this repository
git clone git@github.com:neelkumarkalavadiya/amex-credit-default-prediction.git
cd amex-credit-default-prediction

# Run the notebook
jupyter notebook CreditRisk_MLProject.ipynb
```
