# Modelling Baseball Strike Zones with Support Vector Machines

## Overview

This project trains radial-basis-function support-vector machines to distinguish called strikes from balls using pitch location. It visualises learned decision boundaries for Aaron Judge, David Ortiz, and José Altuve and explores how `gamma` and `C` reshape the boundary.

## Data and features

The three CSV files contain Statcast-style pitch records. The model uses:

- `plate_x` — horizontal pitch location
- `plate_z` — vertical pitch location
- a binary label derived from the recorded pitch description/type

Rows with missing locations are removed before modelling.

## Recorded result

For Aaron Judge, the notebook reports **96.30% accuracy** with `gamma=100` and `C=100`. This score is calculated on the same data used to fit that model, so it demonstrates fit rather than held-out predictive performance.

## Skills demonstrated

- cleaning and relabelling pitch data
- fitting nonlinear SVM decision boundaries
- experimenting with regularisation and kernel width
- comparing player-specific strike-zone visualisations

## Limitations

The main accuracy is a training score, and tuning is performed by inspecting results rather than cross-validation. Real called-strike decisions also depend on batter stance, count, catcher framing, umpire tendencies, and measurement uncertainty. A follow-up should introduce train/test splits, a parameter grid, class-level metrics, and calibrated comparisons across players.

## Run locally

Install `jupyter`, `pandas`, `matplotlib`, and `scikit-learn`. Keep the three CSV files and `svm_visualisation.py` beside `baseball_strike_zones.ipynb`, then run the notebook from this directory.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
