# Identifying Flags with a Decision Tree

## Overview

This project uses physical and design characteristics of national flags to predict their continent of origin. Its central experiment varies maximum tree depth to show how model complexity changes accuracy.

## Data and method

`flags.csv` describes colours, shapes, symbols, and other flag attributes. The notebook first trains a tree using selected colour-count features, then expands the feature set and evaluates depths from 1 through 20 on a train/test split.

## Recorded results

The colour-count-only model recorded **34.69%** test accuracy. With the broader feature set, the strongest recorded result was **55.10%** at maximum depths 4 and 5. Accuracy declined at greater depths, illustrating that a more complex tree does not automatically generalise better.

## Skills demonstrated

- feature selection for categorical prediction
- train/test splitting
- decision-tree fitting and scoring
- depth-based hyperparameter experimentation
- visual comparison of model performance

## Limitations

The dataset is small and country flags do not form evenly distributed continent classes. The notebook selects depth using repeated inspection of the same test set, which can make that set part of the tuning process. A stronger evaluation would reserve a final test set or use cross-validation, report class-level metrics, and compare against a majority-class baseline.

## Run locally

Install `jupyter`, `pandas`, `matplotlib`, and `scikit-learn`. Keep `flags.csv` beside `find_the_flag.ipynb` and run the notebook from this directory.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
