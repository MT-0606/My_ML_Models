# Clustering Masculinity Survey Responses

## Overview

This cumulative unsupervised-learning project applies K-means to responses from a FiveThirtyEight/WNYC masculinity survey. It asks whether behavioural responses form simple “masculine” and “feminine” groups, then extends the analysis to demographic and self-perception features.

## Workflow

- inspect 1,189 survey responses and missing values
- map ordered text responses such as “Often” and “Never” to numeric scales
- visualise relationships between selected survey questions
- cluster seven behavioural variables into two groups
- profile clusters using education and age distributions
- extend the investigation with additional cleaning, feature selection, scaling, and four-cluster exploration

## Main finding

The initial two-cluster solution did not separate respondents into opposing masculine/feminine profiles. One centroid was higher across all seven activity features, suggesting a distinction closer to overall reported activity or willingness to engage. Cluster membership also differed by education and age, motivating the notebook's later demographic exploration.

## Interpretation cautions

Clusters are descriptive, not objective human categories. The numerical mappings impose distances between survey responses, missing-data removal may alter the sample, and K-means results can vary with scaling and random initialisation. The survey's readership is not necessarily representative of a wider population. Future work should document cluster stability, choose `k` with quantitative diagnostics, and avoid treating correlation or cluster membership as causation.

## Run locally

Install `jupyter`, `pandas`, `numpy`, `matplotlib`, and `scikit-learn`. Keep `masculinity.csv` and `masculinity-survey.pdf` beside `masculinity_project.ipynb`, then run the notebook in order.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path using survey materials credited in the notebook to FiveThirtyEight and WNYC.
