# OKCupid Date-A-Scientist Capstone

## Overview

This independently scoped capstone asks whether health-related profile attributes can predict a user's relationship status on OKCupid. It combines exploratory analysis, missing-data strategy, one-hot encoding, class-imbalance analysis, baseline construction, cross-validated hyperparameter search, and comparison of logistic regression with random forests.

## Research question

How accurately can body type, diet, drinking, drug-use, and smoking attributes predict whether a user is single, available, seeing someone, married, or in an open relationship?

## Data and preparation

The notebook selects health-related categorical fields from `profiles.csv`. Missing disclosures—especially prevalent for diet and drug use—are retained as an `unknown` category rather than deleting most of the observations. The target is extremely imbalanced: more than 92% of profiles are labelled `single`. A stratified split and balanced-accuracy scoring are therefore used alongside ordinary accuracy and macro F1.

## Model comparison

| Model | Held-out balanced accuracy | Overall accuracy |
|---|---:|---:|
| Majority-class baseline | 25.00% | 93% |
| Tuned random forest | 36.33% | 57% |
| Selected logistic regression | 34.95% | 49% |

The cross-validation search favoured logistic regression in the notebook's comparison, although the final held-out random-forest balanced accuracy is slightly higher. The notebook ultimately selects logistic regression and discusses its interpretability and search result. Its macro F1 is about 21%, with very low precision for several minority classes.

## Conclusion

Health attributes alone do not reliably predict relationship status. The exercise also shows why high raw accuracy can be deceptive: the 93% baseline simply predicts the dominant class, while balanced accuracy exposes its failure on minority categories. More complex models improve minority-class recognition only modestly.

## Limitations and next steps

The analysis relies on self-reported historical profile data and should not be used to judge individuals. Missingness may itself be informative, and the rare target classes make estimates unstable. Proposed extensions include age, education, location, orientation, and separated child-status/preferences; NLP could examine essay text with appropriate privacy and bias safeguards.

## Files and setup

- `date-a-scientist.ipynb` — full analysis
- `Date-A-Scientist-Presentation.pptx` — presentation summary
- [DATASET.md](DATASET.md) — data instructions

Download `profiles.csv` from the repository's [OKCupid Dataset release](https://github.com/MT-0606/My_ML_Models/releases/tag/capstone-dataset) and place it in this directory. Install `jupyter`, `pandas`, `matplotlib`, `seaborn`, and `scikit-learn`, then run the notebook in order.

The source dataset and initial capstone framework were provided through Codecademy's Build a Machine Learning Model skill path; the research question, analysis choices, interpretation, and presentation are documented in this portfolio.
