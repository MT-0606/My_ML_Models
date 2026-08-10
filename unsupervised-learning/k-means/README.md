# Handwritten Digit Clustering with K-Means

## Overview

This project applies K-means to scikit-learn's handwritten-digits dataset. Unlike supervised digit recognition, the algorithm is trained without target labels: it groups 1,797 images by pixel similarity and produces representative cluster-centre images.

## Data and method

Each sample is an 8×8 grayscale image represented by 64 numeric pixel features. The notebook plots inertia across candidate values of `k`, selects **10 clusters**, fits K-means, and visualises each centroid as an image. Because cluster numbers are arbitrary, a manual mapping connects centroids to digits before predicting four new samples.

## Skills demonstrated

- loading a built-in scikit-learn dataset
- reshaping flat feature vectors into images
- using inertia to study the number of clusters
- interpreting cluster centres
- translating arbitrary cluster IDs into domain labels

## Limitations

Choosing ten clusters is supported both by the task domain and the inertia plot; it is not a fully label-free model-selection conclusion. K-means assumes roughly spherical clusters and Euclidean distance, and visually similar digits can overlap. Future work could report silhouette scores and adjusted Rand index, repeat fitting across random seeds, use PCA before clustering, and compare with Gaussian mixtures or supervised classifiers.

## Run locally

Install `jupyter`, `numpy`, `matplotlib`, and `scikit-learn`, then run `handwriting_recognition.ipynb`. The digits dataset is bundled with scikit-learn, so no separate download is required.

This project was completed as part of Codecademy's Build a Machine Learning Model skill path.
