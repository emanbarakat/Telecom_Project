# Telecom Customer Churn Prediction

A machine learning project that explores customer churn in a large telecom dataset and builds predictive models to identify customers at higher risk of leaving.

The project combines exploratory data analysis, feature engineering, model comparison, performance evaluation, and business-oriented interpretation.

## Project Objective

The goal is to use customer-level telecom data to:

- understand the main factors associated with churn
- build models that can estimate churn risk
- compare multiple machine learning approaches
- identify the most influential features
- translate model results into practical business insights

## Dataset

- **100,000 rows**
- **100 columns**
- Target variable: customer churn
- Class distribution:
  - Non-churn: 50,438
  - Churn: 49,562

The target is close to balanced, which makes metrics such as ROC-AUC, recall, and accuracy useful for model comparison.

## Workflow

1. Data inspection and cleaning
2. Exploratory Data Analysis (EDA)
3. Feature preparation
4. Feature engineering
5. Model training
6. Cross-validation
7. Test-set evaluation
8. Feature-importance analysis
9. Business interpretation

## Models

The project evaluates multiple models, including:

- Random Forest
- CatBoost

### CatBoost

- 5-fold cross-validation ROC-AUC: **0.6873**
- Test ROC-AUC: **0.6878**

### Random Forest

- Test ROC-AUC: **0.6952**
- Accuracy: **0.63695**
- Recall: **0.65**

Random Forest achieved the strongest test ROC-AUC among the reported models.

## Important Features

Some of the most influential features include:

| Feature | Importance |
|---|---:|
| months | 14.58 |
| eqpdays | 12.21 |
| change_mou | 7.79 |
| mou_Mean | 7.59 |
| totmrc_Mean | 5.09 |

These features suggest that customer tenure, equipment age, changes in usage behavior, average minutes of use, and recurring charges are important signals for churn prediction.

## Feature Engineering Experiments

Additional engineered features were tested, including:

- `rev_per_min`
- `rev_ratio`

Reported ROC-AUC results:

- `rev_per_min`: **0.6876**
- `rev_ratio`: **0.6908**

## Customer Segmentation

Customers were also grouped into business-oriented segments:

- Low
- Medium
- High
- VIP

This supports more targeted retention strategies instead of treating all customers in the same way.

## Business Value

A churn model can help a telecom company prioritize retention activity by identifying customers who may need:

- proactive engagement
- targeted offers
- service-quality follow-up
- pricing or plan review
- loyalty interventions

The objective is not only to predict churn, but to support more focused business decisions.

## Repository Contents

- `Copy of Final Assignment  Original.ipynb` — full analysis and modeling notebook
- `Final Assignment.pdf` — project presentation / report

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- CatBoost
- Jupyter Notebook
- Matplotlib

## Key Takeaways

- Churn prediction in this dataset is challenging, with ROC-AUC values around 0.69.
- Random Forest produced the strongest reported test ROC-AUC.
- Behavioral and tenure-related features are among the most useful predictors.
- Feature engineering produced small but measurable improvements.
- Model outputs can be combined with customer segmentation to support retention decisions.

## Author

**Eman Barakat**

AI & Software Development | Data Analysis | Machine Learning | Generative AI
