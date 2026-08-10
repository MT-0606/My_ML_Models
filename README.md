# Machine Learning Models

A portfolio of machine-learning notebooks completed while studying Codecademy's **Build a Machine Learning Model** skill path. The repository progresses from foundational regression and classification to clustering, natural-language processing, and PyTorch neural networks. The capstone extends the guided coursework into an independently scoped investigation of whether health-related profile attributes can predict relationship status.

## Project index

| Area | Project | Technique | Result or focus |
|---|---|---|---|
| Regression | [US honey production](supervised-learning/linear-regression/) | Linear regression | Models annual production and explores long-range extrapolation |
| Classification | [Flag identification](supervised-learning/intro-to-classification/decision-trees/) | Decision tree | Tests how tree depth affects generalisation |
| Classification | [Income prediction](supervised-learning/intro-to-classification/random-forests/) | Random forest | Achieves about 82.2% held-out accuracy with selected census features |
| Text classification | [Email similarity](supervised-learning/advanced-classification/naive-bayes/) | Multinomial Naive Bayes | Distinguishes newsgroup topics from word counts |
| Classification | [Baseball strike zones](supervised-learning/advanced-classification/support-vector-machines/) | RBF support-vector machine | Visualises player-specific decision boundaries |
| Applied classification | [Tweet investigations](supervised-learning/cumulative-project/) | KNN, Naive Bayes, logistic regression | Studies virality, location, and favourites |
| Applied regression | [Yelp rating prediction](supervised-learning/regression-cumulative-project/) | Multiple linear regression | Best tested feature set reaches a test R² of about 0.678 |
| Clustering | [Handwritten digits](unsupervised-learning/k-means/) | K-means | Learns ten image centroids without using labels for training |
| Clustering | [Masculinity survey](unsupervised-learning/cumulative-project/) | K-means | Explores behavioural and demographic response patterns |
| Neural networks | [EV charging loads](neural-networks/intro-to-pytorch-neural-networks/) | PyTorch regression | Compares a neural network with a linear baseline |
| Neural networks | [Hotel cancellations](neural-networks/pytorch-for-classification/) | PyTorch classification | Builds binary and multiclass classifiers |
| Capstone | [OKCupid Date-A-Scientist](capstone/) | Logistic regression and random forest | Tests a self-defined question under severe class imbalance |

## Tools

Python, Jupyter, pandas, NumPy, Matplotlib, seaborn, scikit-learn, and PyTorch.

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

