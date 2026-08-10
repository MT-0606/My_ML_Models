# Predicting Residential EV Charging Loads

## Overview

This PyTorch regression project predicts energy delivered during residential electric-vehicle charging sessions. It combines Norwegian charging-session records with hourly local traffic data, establishes a linear-regression baseline, and trains a feed-forward neural network to capture nonlinear relationships.

## Data preparation

The notebook merges charging and traffic records by hour, removes identifiers and unsuitable text columns, converts European decimal commas, and uses an 80/20 train/test split. The target is `El_kWh`; predictors include session duration, temporal indicators, parking type, traffic counts, and related numeric variables.

## Models

- **Baseline:** scikit-learn linear regression, with instructional guidance indicating MSE around 131.4 (RMSE about 11.5 kWh)
- **Neural network:** two ReLU hidden layers with 56 and 26 units, one regression output, MSE loss, and Adam optimisation
- **Training:** 3,000 epochs at learning rate 0.0007; the exercise also refers to a separately trained 4,500-epoch model with instructional test MSE around 115.2

The repository notebook does not contain saved numeric output for its own baseline or neural-network test cells, and the referenced `.pth` model files are not included. The figures above are therefore exercise reference values, not independently preserved run results.

## Run locally

Install `jupyter`, `pandas`, `numpy`, `scikit-learn`, and `torch`. The notebook currently refers to shortened paths under `datasets/`; either update those paths to the filenames in this folder or arrange local copies accordingly. It also refers to saved model files that must be generated or supplied before the loading cells can run.

## Improvements

Useful next steps include feature scaling, a validation set with early stopping, reproducible model checkpoints, MAE/RMSE reporting, residual analysis, and ablation tests to determine whether traffic data improves predictions.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
