# Predicting Income with Random Forests

## Overview

This notebook trains random-forest classifiers on census-style demographic and employment variables to predict whether income is above or below $50,000. It incrementally adds encoded categorical features to measure whether they improve held-out accuracy.

## Features and method

The model begins with age, capital gains, capital losses, and hours worked per week. It then encodes sex and country information numerically and compares performance after each addition. Data is split into training and test subsets before fitting `RandomForestClassifier`.

## Recorded results

| Feature version | Test accuracy |
|---|---:|
| Numeric features without encoded sex | 82.23% |
| Numeric features plus encoded sex | 82.25% |
| Numeric features plus encoded sex and country grouping | 82.23% |

The added variables changed accuracy only marginally in this experiment. That result is useful: increasing the feature count does not guarantee a meaningful improvement.

## Skills demonstrated

- cleaning inconsistent category text
- encoding categorical variables
- ensemble classification
- controlled feature-set comparisons
- interpreting small changes in test performance

## Limitations and responsible use

Income is affected by structural, historical, and socioeconomic factors that this small feature set cannot represent. Sex and nationality-related variables are sensitive attributes and should not be used uncritically in real hiring, credit, or eligibility decisions. Future work should include class balance, precision/recall, cross-validation, feature importance, fairness testing, and a simple baseline.

## Run locally

Install `jupyter`, `pandas`, and `scikit-learn`. Keep `income.csv` beside `predict_incomes.ipynb` and run the cells in order.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
