# Data Science in Industry — IndabaX Zimbabwe

Presenter: [YOUR FULL NAME]  
Event: IndabaX Zimbabwe  
Date: [DATE]  
Contact: [YOUR EMAIL] · [linkedin.com/in/YOUR-HANDLE] · [github.com/YOUR-HANDLE]

---

## Overview

This repository contains the materials from the IndabaX Zimbabwe tutorial session on applied data science. The session runs for 20 minutes of live coding followed by a 10-minute discussion.

The central question throughout the tutorial is a real one: a bank runs outbound telephone campaigns to sell term deposit products. Given what we know about each customer, which ones should we call? The goal is not simply to build an accurate model — it is to show how a predictive model translates into a concrete operational decision that saves money and improves outcomes.

The workflow follows the same sequence a working data scientist would use on the job.

---

## Repository Contents

```
.
├── IndabaX_Zimbabwe_Tutorial_PRESENTER.ipynb   # Main tutorial notebook (presenter version)
├── README.md                                   # This file
└── datasets/                                   # Practice datasets for hands-on sessions
    ├── telco_churn.csv                         # Customer churn — binary classification
    ├── credit_risk.csv                         # Loan default prediction
    ├── hr_attrition.csv                        # Employee resignation risk
    ├── diabetes.csv                            # Patient health risk screening
    └── titanic.csv                             # Entry-level classification (well-documented)
```

---

## What the Tutorial Covers

**Section 1 — Environment setup and data loading**  
Imports, reproducible data loading, and an offline fallback in case the venue has no internet access.

**Section 2 — Exploratory data analysis**  
Understanding the dataset before modelling: class imbalance, conversion rates by customer segment, and correlations among numerical features.

**Section 3 — Data cleaning and feature engineering**  
Creating new variables from domain reasoning, building a scikit-learn preprocessing pipeline, and avoiding data leakage — specifically why call duration cannot be used as a predictor in production.

**Section 4 — Building and comparing models**  
Training three classifiers (Logistic Regression, Random Forest, Gradient Boosting) and comparing them on held-out data using ROC-AUC and confusion matrices.

**Section 5 — Model validation**  
Cross-validation for stability, feature importance, probability calibration, and learning curves to diagnose overfitting.

**Section 6 — Translating predictions into business decisions**  
Finding the optimal decision threshold, segmenting customers by predicted priority, and quantifying the financial impact of using the model versus calling everyone.

**Section 7 — Written recommendations**  
A short memo summarising the five actionable findings from the analysis, written for a non-technical audience.

---

## Practice Datasets

The `datasets/` folder contains five real-world datasets for attendees to use in their own hands-on sessions after the tutorial. Each one maps directly to a business problem and can be dropped into the tutorial notebook with minimal changes.

| File | Business problem | Target variable | Size |
|------|-----------------|-----------------|------|
| `telco_churn.csv` | Which customers are likely to cancel their subscription? | Churn: Yes / No | ~7 000 rows |
| `credit_risk.csv` | Which loan applicants are likely to default? | Default: Yes / No | ~30 000 rows |
| `hr_attrition.csv` | Which employees are at risk of resigning? | Attrition: Yes / No | ~1 500 rows |
| `diabetes.csv` | Which patients should be referred for further screening? | Diabetic: 1 / 0 | ~768 rows |
| `titanic.csv` | Survival prediction — a well-documented classification benchmark | Survived: 1 / 0 | ~891 rows |

All five are binary classification problems, so the full tutorial pipeline applies to each one without structural changes. The Titanic dataset is the most beginner-friendly due to the volume of public documentation available. The Telco Churn and HR Attrition datasets are the most directly transferable to workplace problems.

**Data sources**  
Telco Churn and HR Attrition are available on [Kaggle](https://www.kaggle.com). Credit Risk and Diabetes originate from the [UCI Machine Learning Repository](https://archive.ics.uci.edu). Titanic is available via `seaborn.load_dataset('titanic')` or Kaggle.

The notebook uses the [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing), a real-world record of a Portuguese bank's telemarketing campaigns between 2008 and 2013. It contains approximately 41 000 rows and 21 columns.

The notebook loads the dataset directly from a public URL. If the URL is unavailable, it generates a synthetic dataset with the same structure and column names so the tutorial runs without interruption.

**Citation:**  
Moro, S., Cortez, P., & Rita, P. (2014). A data-driven approach to predict the success of bank telemarketing. *Decision Support Systems*, 62, 22–31.

---

## Running the Notebook

The notebook is designed to run on Google Colab with no local setup required.

1. Open [Google Colab](https://colab.research.google.com)
2. Select **File > Upload notebook** and upload `IndabaX_Zimbabwe_Tutorial_PRESENTER.ipynb`
3. Select **Runtime > Run all**

All required libraries (pandas, numpy, matplotlib, seaborn, scikit-learn) are available in Colab by default. No additional installation is needed.

To run locally:

```bash
git clone https://github.com/YOUR-HANDLE/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook IndabaX_Zimbabwe_Tutorial_PRESENTER.ipynb
```

---

## Key Takeaways

The tutorial makes three points that apply beyond this specific dataset.

First, exploratory data analysis is not optional. Patterns visible in the data before any model is built — such as the much higher conversion rate for customers with a successful prior campaign outcome — can inform strategy directly and validate that the model is learning sensible things.

Second, production readiness requires deliberate choices. Dropping the call duration column because it is not available at prediction time is the kind of decision that separates a notebook exercise from something that would actually work when deployed.

Third, the output of a data science project is a decision, not a model. The ROI comparison in Section 6 is the part a business leader will remember and act on. The model is the mechanism; the recommendation is the deliverable.

---

## Adapting This Work

The workflow in this notebook is not specific to bank marketing. The same structure applies to any binary classification problem. The five datasets in the `datasets/` folder are ready starting points — pick the one closest to your area of interest and work through the same sections.

To adapt the notebook to a new dataset:

- Replace the dataset loading in Section 1 with `pd.read_csv('datasets/your_file.csv')`
- Rewrite the feature engineering in Section 3 using knowledge of your domain
- Update the business assumptions (revenue per conversion, cost per action) in Section 6
- Rewrite the recommendations in Section 7 based on what your data shows

If you build something with this as a starting point, feel free to open a pull request or tag [YOUR FULL NAME] on LinkedIn.

---

## License

This tutorial is shared for educational use. You are welcome to adapt and redistribute the code with attribution.

---

*IndabaX Zimbabwe · Building Africa's data science community*
