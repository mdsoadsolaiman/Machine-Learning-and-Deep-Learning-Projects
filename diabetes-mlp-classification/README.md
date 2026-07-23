# Diabetes MLP Classification

> This project was originally completed as part of university coursework and has been reorganised and documented for professional portfolio presentation.

## Project Overview

A tabular deep-learning study comparing three multilayer perceptron configurations for diabetes classification.

## Academic Context

The work was completed as a university coursework project. The public version retains the original technical evidence while improving naming, navigation, transparency and evaluation context.

## Problem Statement

Evaluate how MLP capacity, learning rate and dropout affect classification performance on a de-identified academic dataset.

## Dataset

The CSV files are excluded pending licence verification. The source description is retained at [data-description.txt](data/data-description.txt).

## Data Preparation

Zero-value handling, mean imputation, class-wise IQR filtering, standardisation and a stratified 80/20 training-validation split were applied.

## Methodology

Three MLP configurations were selected using validation evidence, followed by a separate final test evaluation.

## Model Architecture

The selected large MLP uses hidden layers of 128 and 64 units, ReLU activation, 0.3 dropout and a weighted binary cross-entropy objective.

## Experimental Design

The large MLP was selected for the highest validation ROC-AUC (0.8704), not the highest validation accuracy.

## Results

On 153 cleaned test records, the selected model achieved 0.7451 accuracy, 0.6829 F1 and 0.8480 ROC-AUC. See [final test results](results/final-test-results.csv).

## Key Findings

Validation ROC-AUC provided a clearer model-selection criterion than accuracy alone for the imbalanced target.

## Limitations

Dataset provenance and licence remain unresolved. This is not a clinical diagnostic tool, and the academic report contains a raw-count discrepancy documented here.

## Technologies

Python, PyTorch, NumPy, Pandas, Matplotlib and scikit-learn.

## Repository Structure

```text
notebooks/  Cleaned portfolio notebook
reports/    Original academic report
figures/    Preprocessing and model-evaluation visuals
results/    Validation and final-test tables
data/       Description and access guidance
```

## Reproduction Instructions

Install the root requirements, lawfully obtain the CSV files, set `DIABETES_DATA_DIR`, and run the notebook sequentially.
