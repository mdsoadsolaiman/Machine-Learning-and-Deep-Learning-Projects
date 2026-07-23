# MNIST Classification and Clustering

> This project was originally completed as part of university coursework and has been reorganised and documented for professional portfolio presentation.

## Project Overview

A combined supervised and unsupervised study of digits 1 and 7 using classifier tuning, PCA and K-Means.

## Academic Context

The work was completed as a university coursework project. The public version retains the original technical evidence while improving naming, navigation, transparency and evaluation context.

## Problem Statement

Compare linear and kernel classifiers, then investigate visual variation within digit 7 through clustering.

## Dataset

The NPZ subset is excluded pending provenance and licence documentation; see [data access](data/README.md).

## Data Preparation

Images were flattened, normalised, standardised and projected with PCA where appropriate.

## Methodology

Logistic Regression and RBF SVM used five-fold stratified cross-validation and grid search. Digit-7 clustering evaluated k=2–99 before retaining k=9 as an interpretable local solution.

## Model Architecture

The supervised models are scikit-learn Logistic Regression and RBF SVM; unsupervised analysis uses PCA and K-Means.

## Experimental Design

The training subset contains 50 examples per class. Classifier evidence is training and cross-validation evidence; no held-out classifier test evaluation was completed.

## Results

Mean CV F1 was 1.0000 for Logistic Regression and approximately 0.9699 for RBF SVM. k=2 had the highest global silhouette score; k=9 was retained for more granular interpretation.

## Key Findings

The project combines discriminative modelling, hyperparameter search, dimensionality reduction and cluster interpretation.

## Limitations

The NPZ provenance remains unresolved. The original academic report incorrectly states the digit-7 test count and some cluster percentages; corrected values are used here.

## Technologies

Python, NumPy, Pandas, Matplotlib, Seaborn and scikit-learn.

## Repository Structure

```text
notebooks/  Cleaned portfolio notebook
reports/    Original academic report
figures/    Classification, PCA and clustering visuals
results/    Corrected tuning and cluster summaries
data/       Access and licensing guidance
```

## Reproduction Instructions

Install the root requirements, obtain an authorised NPZ subset, set `MNIST_SUBSET_PATH`, and run the notebook sequentially.
