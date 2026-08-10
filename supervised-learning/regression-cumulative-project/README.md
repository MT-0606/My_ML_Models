# Predicting Yelp Ratings with Multiple Linear Regression

## Overview

This cumulative regression project combines business, review, user, check-in, tip, and photo data to investigate which measurable features help explain restaurant star ratings. It moves from data inspection and cleaning to correlations, feature-subset experiments, coefficient interpretation, and a hypothetical restaurant prediction.

## Modelling approach

The target is a business's Yelp `stars` value. Candidate predictors include review sentiment and age, business attributes, review and user activity, and check-in patterns. Models are fitted on an 80/20 train/test split and compared using R².

## Recorded results

| Feature set | Train R² | Test R² |
|---|---:|---:|
| Average review length and age | 0.083 | 0.081 |
| Review sentiment | 0.612 | 0.611 |
| Binary business features | 0.012 | 0.010 |
| Numeric features | 0.673 | 0.671 |
| All available model features | 0.681 | 0.678 |
| Custom subset | 0.662 | 0.659 |

The all-features model records the strongest test result, while review length and age alone explain little of the rating variance. Similar train and test scores suggest limited overfitting within this split, but they do not establish causal relationships.

## Datasets

Download the seven `yelp_*.json` assets from the repository's [Yelp Datasets release](https://github.com/MT-0606/My_ML_Models/releases/tag/regression), then place them in this directory. See [DATASET.md](DATASET.md).

## Limitations

Star ratings are ordinal and bounded, while ordinary linear regression assumes a continuous response and linear additive relationships. The project uses a single split and may include correlated or platform-specific features. Future work could add cross-validation, RMSE/MAE and residual diagnostics, regularisation, tree-based comparisons, and time-aware validation.

## Run locally

Install `jupyter`, `pandas`, `numpy`, `matplotlib`, and `scikit-learn`. Download the release assets and run `yelp_regression.ipynb` from this directory.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
