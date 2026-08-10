# Classifying Email Topics with Naive Bayes

## Overview

This text-classification project uses the scikit-learn 20 Newsgroups dataset to distinguish messages from two selected discussion categories. Raw text is converted into bag-of-words counts and classified with multinomial Naive Bayes.

## Workflow

1. Fetch two labelled newsgroup categories.
2. Inspect message text and target labels.
3. Fit `CountVectorizer` on the training messages.
4. Train `MultinomialNB` on the resulting word-count matrix.
5. Transform the test messages with the same vocabulary and evaluate accuracy.

## Recorded results

The notebook records **97.24%** accuracy for its first category pair and **98.61%** after changing the categories. These results demonstrate that some topic pairs have highly distinguishable vocabularies.

## Limitations

Accuracy alone does not show which category generates errors. Bag-of-words features ignore word order and context, and message headers may make classification easier without reflecting body-text understanding. A stronger extension would remove headers, compare TF-IDF, report a confusion matrix and per-class metrics, and test category pairs with more overlapping language.

## Run locally

Install `jupyter` and `scikit-learn`, then run `email_similarity.ipynb`. The first execution requires internet access so scikit-learn can download the 20 Newsgroups dataset if it is not already cached.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
