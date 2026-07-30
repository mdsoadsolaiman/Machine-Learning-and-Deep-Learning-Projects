# 🩺 Deep Learning for Diabetes Prediction
### Comparative Evaluation of Multi-Layer Perceptron Architectures in PyTorch

<p align="center">

<img src="figures/ROC curve.png" width="800">

</p>

<p align="center">

<img src="https://img.shields.io/badge/Python-3.12-blue">
<img src="https://img.shields.io/badge/PyTorch-Deep%20Learning-red">
<img src="https://img.shields.io/badge/Binary-Classification-success">
<img src="https://img.shields.io/badge/Healthcare-Machine%20Learning-brightgreen">
<img src="https://img.shields.io/badge/Status-Completed-success">

</p>

---

## Overview

This project develops and evaluates multiple **Multi-Layer Perceptron (MLP)** architectures for diabetes prediction using clinical health indicators.

Rather than training a single neural network, this study investigates how network capacity influences predictive performance by comparing **Small**, **Medium**, and **Large** MLP architectures under identical preprocessing and training conditions.

The complete workflow includes:

- Exploratory Data Analysis (EDA)
- Data preprocessing and feature engineering
- Missing-value treatment
- Neural network development in PyTorch
- Hyperparameter comparison
- Model evaluation using multiple performance metrics
- Final model selection using ROC-AUC

---

# Dataset

The model uses eight routinely collected clinical measurements.

| Feature |
|----------|
| Pregnancies |
| Glucose |
| BloodPressure |
| SkinThickness |
| Insulin |
| BMI |
| DiabetesPedigreeFunction |
| Age |

Target variable:

- **Outcome = 0** → Non-diabetic
- **Outcome = 1** → Diabetic

---

# Exploratory Data Analysis

The initial analysis identified skewed feature distributions, missing-value patterns represented by physiologically impossible zero values, and varying relationships between clinical variables.

## Correlation Matrix

<img src="figures/Correlation Heatmap.png">

Glucose exhibited the strongest positive relationship with diabetes outcome, followed by BMI, Age, and Pregnancies.

---

## Raw Data Distribution

<img src="figures/Histogram of the raw data.png">

---

## Raw Feature Boxplots

<img src="figures/Boxplot for the Raw dataset.png">

---

# Data Preprocessing

A structured preprocessing pipeline was implemented before model training.

### Cleaning Steps

- Detection of impossible zero values
- Mean imputation for selected clinical variables
- Class-wise IQR filtering
- Feature scaling
- Stratified train-validation-test split

The cleaned dataset exhibits more realistic feature distributions while preserving important clinical variation.

---

## Cleaned Feature Distributions

<img src="figures/Density curve for the cleaned data.png">

---

## Cleaned Feature Boxplots

<img src="figures/Boxplot for the cleaned dataset.png">

---

# Model Development

Three fully connected neural network architectures were implemented in **PyTorch**.

| Model | Hidden Layers | Dropout |
|---------|--------------|---------|
| Exp1 Small | 32 → 16 | 0.20 |
| Exp2 Medium | 64 → 32 | 0.20 |
| Exp3 Large | 128 → 64 | 0.30 |

Each model uses

- ReLU activation
- Adam optimizer
- Binary Cross Entropy loss
- Early stopping
- Mini-batch gradient descent

---

# Learning Curves

## Small Network

<img src="figures/Loss curve of the Small Hidden Layers.png">

---

## Medium Network

<img src="figures/Loss curve of the Medium Hidden Layers.png">

---

## Large Network

<img src="figures/Loss curve of the Large Hidden Layers.png">

The larger architecture demonstrated the most stable optimisation behaviour while achieving the highest validation ROC-AUC.

---

# Model Performance

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---------|---------|----------|--------|---------|---------|
| Small | 79.31% | 64.29% | **90.00%** | **75.00%** | 0.8655 |
| Medium | 78.45% | 64.15% | 85.00% | 73.12% | 0.8632 |
| **Large** | 77.59% | 63.46% | 82.50% | 71.74% | **0.8704** |

Although the Small network produced the highest accuracy and F1-score, the Large model achieved the strongest ROC-AUC and was therefore selected as the final model.

---

# ROC Analysis

<img src="figures/ROC curve.png">

The selected model achieved an **Area Under the ROC Curve (AUC) of approximately 0.87**, indicating good discrimination between diabetic and non-diabetic patients across varying classification thresholds.

---

# Validation Confusion Matrix

<img src="figures/Confusion Matrix.png">

---

# Final Test Results

The final selected model was evaluated on an unseen test dataset.

<img src="figures/Confusion Matrix -  Test Set.png">

| Metric | Score |
|---------|------:|
| Accuracy | 72.55% |
| Precision | 61.19% |
| Recall | 71.93% |
| F1-score | 66.13% |

---

# Repository Structure

```text
diabetes-prediction-mlp/
│
├── data/
├── figures/
├── notebooks/
├── reports/
├── results/
├── README.md
└── requirements.txt
```

---

# Technologies

- Python
- PyTorch
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

# Key Learning Outcomes

This project demonstrates practical experience in:

- Clinical data preprocessing
- Exploratory data analysis
- Feature engineering
- Neural network implementation
- Binary classification
- Performance evaluation
- ROC analysis
- Model comparison
- Deep learning using PyTorch

---

# Limitations

- Relatively small dataset
- Limited to MLP architectures
- Not intended for clinical diagnosis
- Additional external validation would be required before deployment

---

# Author

**Md Soad Solaiman**

---