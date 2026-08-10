# Predicting Hotel Cancellations with PyTorch

## Overview

This project builds neural-network classifiers for resort-hotel bookings. Its primary task predicts whether a reservation will be cancelled; an extension reframes the target as a three-class reservation-status problem.

## Workflow

The notebook inspects approximately 40,060 bookings, removes leakage-prone or high-missingness columns, one-hot encodes categorical variables, converts arrays to PyTorch tensors, and trains fully connected networks.

### Binary classifier

The binary network uses 65 inputs, hidden layers with ReLU activations, a sigmoid output, binary cross-entropy loss, and Adam. After 1,000 epochs, the recorded training accuracy is about **72.22%** and held-out accuracy is **72.20%**.

### Multiclass extension

The extension uses a three-output network with cross-entropy loss to predict reservation status. Its training accuracy reaches about **84.75%** after 500 epochs. The notebook's final evaluation cell appears to reuse the binary model and variables rather than the multiclass model, so it does not establish a valid multiclass test result.

## Limitations

Accuracy should be supplemented with class-level precision, recall, F1, and a confusion matrix. Numeric feature scaling, validation-based early stopping, comparison with logistic/tree baselines, and correction of the multiclass evaluation would make the conclusions stronger. Care is also required to prevent any post-outcome reservation fields from leaking the answer.

## Run locally

Install `jupyter`, `pandas`, `numpy`, `scikit-learn`, and `torch`. The included file is named `hotel_bookings.csv`; update the notebook's dataset path if it expects a different directory or filename, then run `predict_hotel_cancellations.ipynb`.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
