# Tweet Classification Investigations

## Overview

This cumulative supervised-learning project contains three related Twitter investigations. Together they cover structured-feature classification, text vectorisation, imbalanced targets, model comparison, and multiclass prediction.

## Notebooks

### `viral_tweets.ipynb`

Uses tweet length, follower count, and friend count with a scaled K-nearest-neighbours classifier to predict whether a tweet is viral. The recorded test accuracy with `k=5` is **58.87%**. The notebook also plots accuracy across values of `k` and explores adding more user-level features.

### `tweet_location.ipynb`

Uses `CountVectorizer` and multinomial Naive Bayes to classify tweets as originating from New York, London, or Paris. The recorded held-out accuracy is **67.79%**, and a confusion matrix is used to inspect which cities are confused.

### `favourites.ipynb`

Investigates whether text can distinguish tweets with unusually high favourite counts. Because only about 6% of the target examples are positive, a majority baseline reaches **93.97% accuracy** while finding no positive cases. Naive Bayes produces the same outcome. Logistic regression reduces overall accuracy but achieves **51.11% recall** and **15.08% F1** for the positive class, demonstrating why accuracy is misleading under class imbalance.

## Datasets

Download `london.json`, `new_york.json`, `paris.json`, and `random_tweets.json` from the repository's [Tweet Classification Datasets release](https://github.com/MT-0606/My_ML_Models/releases/tag/supervised-learning), then place them in this directory. See [DATASET.md](DATASET.md).

## Limitations and improvements

The projects use relatively simple bag-of-words and account-metadata features. Results may be affected by language, collection period, class definitions, and location-specific names. Improvements could include stratified cross-validation, class weighting or resampling, TF-IDF and n-grams, stronger baselines, and explicit checks for data leakage.

## Run locally

Install `jupyter`, `pandas`, `numpy`, `matplotlib`, and `scikit-learn`. Download the four JSON files, keep them beside the notebooks, and run each notebook independently.

These projects were completed as part of Codecademy's Build a Machine Learning Model skill path.
