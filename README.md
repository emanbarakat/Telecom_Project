# Telecom Customer Churn Prediction

A machine learning project for predicting telecom customer churn and translating model results into practical retention opportunities.

The project merges customer-profile and usage records, performs exploratory data analysis, trains a CatBoost classifier, engineers behavioral features, evaluates churn risk, and creates business-oriented customer segments.

## Dataset

Two source files are merged on `Customer_ID`:

- `Client.csv`
- `Record.csv`

The merged dataset in the recorded experiment contained:

- **100,000 customers**
- **100 columns**
- **50,438 non-churned customers**
- **49,562 churned customers**

The raw telecom data is not committed to this repository.

## Modeling Approach

The workflow uses:

- an 80/20 stratified train/test split
- CatBoost for mixed numerical and categorical data
- 5-fold stratified cross-validation
- ROC-AUC as the primary model metric

### Feature Engineering

The final model adds:

- `rev_per_min`
- `rev_ratio`
- `mou_ratio`
- `eqp_years`
- `overage_ratio`
- `revenue_per_month`

## Recorded Results

| Experiment | ROC-AUC |
| --- | ---: |
| CatBoost baseline, 5-fold CV | **0.6876** |
| CatBoost + engineered features, 5-fold CV | **0.6965** |
| Final engineered model, held-out test | **0.6952** |

Additional held-out test metrics:

- **Accuracy:** 0.63695
- **Recall for churn:** 0.65

The model is intended primarily to rank customers by churn risk rather than optimize accuracy alone.

## Business Insights

The analysis also creates practical retention segments.

Recorded observations include:

- Older-device customers: **55.38% churn**
- Newer-device customers: **43.79% churn**
- Customers with declining usage and revenue: **51.80% churn**
- Customers with inactive lines: **56.02% churn**
- High-value customers with older devices: **55.67% churn**

These patterns suggest opportunities for:

- device-upgrade campaigns
- proactive outreach to declining-usage customers
- retention offers for high-value customers
- plan reviews for customers with inactive lines

These are dataset associations and should not be interpreted as causal effects.

## Repository Structure

```text
telecom-churn-prediction/
├── telecom_churn_analysis.ipynb
├── Final Assignment.pdf
├── requirements.txt
├── .gitignore
└── README.md
```

The PDF contains the original project presentation/report.

## Run Locally

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Add the data

Create:

```text
telecom/
├── Client.csv
└── Record.csv
```

### 3. Open the notebook

```text
telecom_churn_analysis.ipynb
```

## Tech Stack

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- CatBoost
- Jupyter Notebook

## Possible Next Improvements

- hyperparameter optimization
- probability calibration
- SHAP explanations
- LightGBM/XGBoost comparison
- time-based validation
- cost-sensitive retention thresholds

## Author

**Eman Barakat**
