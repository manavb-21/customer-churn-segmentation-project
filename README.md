# Customer Churn Prediction & Segmentation

## Executive Summary
This project outlines a complete Machine Learning workflow designed to predict telecom customer churn and segment users based on their risk profiles. The repository demonstrates the progression from initial exploratory data analysis to an optimized machine learning pipeline, bridging the gap between predictive modeling and actionable business strategy.

**Project Objective:**
Build a robust classification model to identify at-risk customers and implement a K-Means clustering workflow to group them into targeted retention segments.

## Repository Structure
* **`dataset/`**: Contains the source dataset (`Telco_customer_churn.xlsx`).
* **`source code/`**: Contains the foundational Exploratory Data Analysis (EDA), data cleaning, and baseline modeling (`MB_CBSOT_Project1.ipynb`).
* **`optimized section/`**: Contains the advanced feature engineering, threshold-tuned classification, and K-Means customer segmentation implementation (`optimized_code.ipynb`).

## Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn
* **Algorithms:** Random Forest Classifier, K-Means Clustering

## Model Performance & Key Metrics
The optimized classification model was trained and evaluated on a held-out test set, with a specific focus on maximizing **Recall** to ensure the business does not miss identifying at-risk customers.

* **Accuracy:** ~78%
* **ROC-AUC:** ~85%
* **Primary Metric:** High Recall (Optimized for retention campaigns)

## Business Actions & Customer Segmentation
Using K-Means clustering on predicted churn probabilities, the customer base was partitioned into three actionable business personas:

1. **High Risk New Customers:** 
   * *Action:* Launch early-life retention offers and proactive onboarding during the first 6 months.
2. **Budget Loyal Customers:** 
   * *Action:* Protect value perception with low-cost loyalty rewards and promote add-on services selectively without hurting affordability.
3. **Premium Stable Customers:** 
   * *Action:* Deliver white-glove premium support and offer targeted upsell bundles to deepen engagement rather than broad discounting.

## How to Run
1. Clone this repository to your local machine.
2. Ensure you have Jupyter Notebook or VS Code with the Jupyter extension installed.
3. Install the required dependencies: `pip install pandas numpy scikit-learn matplotlib seaborn openpyxl`.
4. Run the notebooks from top to bottom, starting with the `source code` for EDA, followed by the `optimized section` for the final pipeline.