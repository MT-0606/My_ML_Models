# Forecasting US Honey Production

## Overview

This introductory regression project examines annual US honey production and fits a straight-line trend over time. It demonstrates the complete basic scikit-learn workflow: aggregating tabular data, reshaping a feature for model input, fitting `LinearRegression`, visualising the fitted line, and extrapolating future values.

## Question

How has average honey production changed by year, and what would a simple linear trend predict through 2050?

## Data and method

`honey_production.csv` contains state-level observations. The notebook groups the records by year, uses `year` as the sole predictor, and models `totalprod` as the response. It then plots both the historical fit and predictions for 2013–2050.

## What the notebook demonstrates

- pandas grouping and aggregation
- NumPy reshaping for scikit-learn
- fitting and inspecting a linear model
- plotting historical observations, a fitted line, and future predictions
- interpreting a slope and intercept in context

## Limitations

The notebook fits and evaluates the trend on the same aggregated observations; it does not use a held-out test set or report an error metric. The 2050 estimate is therefore an illustration of extrapolation, not a validated forecast. A stronger follow-up would test nonlinear or time-series alternatives, use prediction intervals, and incorporate factors such as colony counts, climate, disease, and agricultural conditions.

## Run locally

Install `jupyter`, `pandas`, `numpy`, `matplotlib`, and `scikit-learn`. Keep `honey_production.csv` beside `honey_production.ipynb`, launch Jupyter, and run the cells in order.

## Files

- `honey_production.ipynb` — analysis and model
- `honey_production.csv` — source data used by the notebook

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
