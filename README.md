# Build a Machine Learning Model

## Overview
This repository is a portfolio of machine learning projects from Codecademy's **Build a Machine Learning Model** skill path. Each folder concerns a major field of machine learning (see the `Project Index` below for more information). 

## Project Index

| ML Area | Project | ML Technique | Focus |
|---|---|---|---|
| Regression | [US honey production](supervised-learning/linear-regression/) | Linear regression | Models and extrapolates honeybee population/honey production decline |
| Classification | [Flag identification](supervised-learning/intro-to-classification/decision-trees/) | Decision tree | Tests how tree depth affects accuracy |
| Classification | [Income prediction](supervised-learning/intro-to-classification/random-forests/) | Random forest | Predicts with 82.2% accuracy the effect of selected census features on income |
| Text classification | [Email similarity](supervised-learning/advanced-classification/naive-bayes/) | Multinomial Naïve Bayes | Distinguishes newsgroup topics from word counts |
| Classification | [Baseball strike zones](supervised-learning/advanced-classification/support-vector-machines/) | Support vector machine | Visualises player-specific decision boundaries |
| Applied classification | [Tweet investigations](supervised-learning/cumulative-project/) | KNN, Naive Bayes, logistic regression | Studies virality, location, and favourites |
| Applied regression | [Yelp rating prediction](supervised-learning/regression-cumulative-project/) | Multiple linear regression | Best tested feature set reaches a test R² of about 0.678 |
| Clustering | [Handwritten digits](unsupervised-learning/k-means/) | K-means | Learns ten image centroids without using labels for training |
| Clustering | [Masculinity survey](unsupervised-learning/cumulative-project/) | K-means | Explores behavioural and demographic response patterns |
| Neural networks | [EV charging loads](neural-networks/intro-to-pytorch-neural-networks/) | PyTorch regression | Compares a neural network with a linear baseline |
| Neural networks | [Hotel cancellations](neural-networks/pytorch-for-classification/) | PyTorch classification | Builds binary and multiclass classifiers |
| Capstone | [OKCupid Date-A-Scientist](capstone/) | Logistic regression and random forest | Tests a self-defined question under severe class imbalance |

## Tools
* **Language:** Python
* **IDE:** Jupyter Notebooks (using Anaconda)
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, and PyTorch.

## Running the notebooks

Clone the repository, create a Python environment, and install the common dependencies:

```bash
git clone https://github.com/MT-0606/My_ML_Models.git
cd My_ML_Models
python -m venv .venv
```

Activate the environment, then install:

```bash
pip install jupyter pandas numpy matplotlib seaborn scikit-learn torch
jupyter notebook
```

Each project README identifies its notebook, data files, extra setup, recorded results, and known limitations. Large datasets are stored as GitHub Release assets where noted.

## Portfolio context

These notebooks retain their instructional structure so the learning progression remains visible. Results are reported as recorded in the notebooks; training-set measurements are labelled as such and are not presented as estimates of generalisation. Future revisions can add dependency pinning, automated tests, cross-validation, and clearer separation between reusable code and exploratory analysis.

