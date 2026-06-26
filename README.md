# Customer Churn Prediction & Segmentation

## Executive Summary

This project presents an end-to-end Machine Learning pipeline for predicting telecom customer churn and generating business-oriented customer segments for targeted retention strategies.

Starting from exploratory data analysis and data preprocessing, the project builds multiple machine learning models, performs hyperparameter optimization, compares model performance, and applies K-Means clustering to transform churn predictions into actionable business insights.

The notebook demonstrates the complete workflow expected in a real-world data science project—from raw data to business recommendations.

---

## Project Objectives

* Predict telecom customer churn using supervised machine learning.
* Compare baseline and optimized classification models.
* Optimize model performance using RandomizedSearchCV.
* Compare Random Forest and XGBoost.
* Interpret model predictions through Feature Importance Analysis.
* Segment customers using K-Means clustering based on predicted churn probability and customer behavior.
* Generate business-oriented retention strategies for each customer segment.

---

## Repository Structure

```
customer-churn-segmentation/
│
├── dataset/
│   └── Telco_customer_churn.xlsx
│
├── source code/
│   ├── MB_CBSOT_Project1.ipynb
│   └── mb_cbsot_project1.py
│
├── optimized section/
│   └── optimized_code.ipynb
│
└── README.md
```

* **dataset/** – Telecom customer churn dataset.
* **source code/** – Original internship implementation.
* **optimized section/** – Improved notebook with optimized machine learning pipeline, model comparison, customer segmentation, and business insights.

---

## Project Workflow

1. Data Loading
2. Exploratory Data Analysis (EDA)
3. Data Cleaning
4. Feature Engineering
5. Train-Test Split (Stratified)
6. Baseline Random Forest
7. Hyperparameter Optimization using RandomizedSearchCV
8. XGBoost Model Training & Comparison
9. Final Model Selection
10. Model Evaluation
11. Feature Importance Analysis
12. Customer Segmentation using K-Means
13. Business Insights & Retention Strategy

---

## Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Matplotlib
* Seaborn
* OpenPyXL

### Machine Learning Algorithms

* Random Forest Classifier
* XGBoost Classifier
* K-Means Clustering

---

## Model Performance

Three models were evaluated:

| Model                  | Accuracy |     Recall |    ROC-AUC |
| ---------------------- | -------: | ---------: | ---------: |
| Baseline Random Forest |   79.28% |     52.67% |     0.8327 |
| Tuned Random Forest    |   80.77% |     52.41% |     0.8544 |
| XGBoost                |   80.62% | **54.28%** | **0.8565** |

### Final Model Selection

Rather than selecting the model solely based on Accuracy, the project uses a practical model selection strategy:

- Prefer the model with the highest Accuracy.
- If competing models differ by less than **0.5% Accuracy**, select the model with the higher Recall.

Using this strategy, **XGBoost** was selected as the final model because it achieved the highest Recall among the top-performing models while also obtaining the best ROC-AUC score.

---

## Evolution of the Optimization Strategy

This repository contains two optimization approaches that reflect the progression of the project.

### Phase 1 – Recall-Oriented Optimization (Internship Implementation)

The initial optimization focused on maximizing **Recall**, ensuring that as many potential churners as possible were identified for retention campaigns.

| Model | Accuracy | Recall | ROC-AUC |
|------|---------:|--------:|---------:|
| Optimized Random Forest | **74.38%** | **82.62%** | 0.8500 |
| XGBoost | 73.95% | 81.82% | 0.8485 |

This approach is well suited for business scenarios where **missing a customer likely to churn is significantly more expensive than contacting additional customers**, even if it results in more false positives.

---

### Phase 2 – Balanced Production-Oriented Optimization (Current Implementation)

The current notebook adopts a more balanced evaluation strategy by jointly considering **Accuracy, Recall, and ROC-AUC** during model selection.

Compared to the initial implementation:

- Improved Accuracy from **74.38% → 80.62%**
- Improved ROC-AUC from **0.8500 → 0.8565**
- Maintained competitive Recall while significantly reducing false-positive predictions
- Added systematic model comparison, feature importance analysis, customer segmentation, and business insight generation

This version better represents a production-ready machine learning workflow while preserving strong business relevance.

---

## Feature Importance

The project analyzes the contribution of every feature using the selected model.

The most influential features include:

* Internet Service (Fiber Optic)
* Electronic Check Payment Method
* Two-Year Contract
* One-Year Contract
* Dependents
* Internet Service Type
* Tenure Months
* Paperless Billing

This improves model interpretability and helps explain customer churn behavior.

---

## Customer Segmentation

Customers are clustered using **K-Means** on:

* Tenure
* Monthly Charges
* Total Charges
* Predicted Churn Probability

The Elbow Method was used to determine the optimal number of clusters.

Three business-friendly customer segments were identified:

### High Risk New Customers

* Short tenure
* Highest churn probability
* Require proactive onboarding and early retention campaigns

### Budget Loyal Customers

* Low monthly spending
* Stable customer base
* Best suited for loyalty rewards and affordable add-on services

### Loyal Premium Customers

* Long tenure
* High monthly spending
* Valuable customers requiring premium support and personalized offers

---

## Business Insights

The project identifies high-value customers who are simultaneously:

* High CLTV
* High predicted churn probability

These customers represent the highest retention priority.

Business recommendations are generated for every customer segment to support targeted retention campaigns.

---

## How to Run

1. Clone the repository.

```
git clone <repository-url>
```

2. Install the required libraries.

```
pip install pandas numpy scikit-learn matplotlib seaborn xgboost openpyxl
```

3. Open `optimized section/optimized_code.ipynb`.

4. Run all notebook cells from top to bottom.

---

## Future Improvements

* Optimize the probability threshold for different business objectives (maximize Recall vs maximize Precision).
* Perform cost-sensitive learning using customer lifetime value (CLTV).
* Add SHAP values for model explainability.
* Build an interactive Streamlit dashboard.
* Deploy the model using FastAPI or Flask.
* Automate retraining using an MLOps pipeline.

---

## Author

**Manav Bhatia**

Computer Science Engineering (AI/ML)
Faculty of Technology, University of Delhi
