# 🩺 Deep Learning for Diabetes Prediction
### Comparative Evaluation of Multi-Layer Perceptron Architectures using PyTorch

> A comparative deep learning study evaluating multiple Multi-Layer Perceptron (MLP) architectures for binary diabetes prediction using clinical health indicators, with systematic preprocessing, controlled model comparison, and comprehensive performance evaluation.

<p align="center">
<img src="figures/ROC curve.png" width="850">
</p>

---

# Overview

Early identification of diabetes enables timely clinical intervention and reduces the risk of long-term complications. Machine learning provides an effective approach for analysing clinical measurements and estimating diabetes risk.

This project investigates the effectiveness of **Multi-Layer Perceptron (MLP)** models for binary diabetes classification using routinely collected medical information. Instead of training a single neural network, three architectures with different network capacities were developed and compared under identical preprocessing and training conditions.

The complete workflow includes:

- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Missing value treatment
- Feature engineering
- Neural network implementation in PyTorch
- Comparative model evaluation
- Final model selection using ROC-AUC
- Performance analysis on unseen test data

---

# Methodology

The project uses the well-known **Pima Indians Diabetes Dataset**, containing clinical measurements collected from female patients.

The predictor variables include:

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Diabetes Pedigree Function
- Age

The target variable is:

- **Outcome = 0** → Non-diabetic
- **Outcome = 1** → Diabetic

Before model development, the dataset underwent a structured preprocessing pipeline designed to improve data quality and model generalisation.

The preprocessing process included:

- Identification of physiologically impossible zero values
- Missing-value imputation
- Outlier investigation
- Feature scaling
- Stratified train-validation-test split

---

# Exploratory Data Analysis

## Correlation Analysis

<p align="center">
<img src="figures/Correlation Heatmap.png">
</p>

The correlation matrix shows that **Glucose** exhibits the strongest relationship with diabetes outcome, followed by **BMI**, **Age**, and **Pregnancies**, indicating that these variables provide the greatest predictive value.

---

## Raw Data Distribution

<p align="center">
<img src="figures/Histogram of the raw data.png">
</p>

The raw feature distributions reveal substantial skewness and unrealistic zero values in several medical variables, motivating the need for data cleaning before model training.

---

## Raw Feature Boxplots

<p align="center">
<img src="figures/Boxplot for the Raw dataset.png">
</p>

The boxplots highlight numerous outliers and physiologically impossible observations, particularly within **Insulin**, **Skin Thickness**, and **Blood Pressure**.

---

# Data Cleaning

After preprocessing, feature distributions became more consistent while preserving clinically meaningful variability.

## Cleaned Feature Distributions

<p align="center">
<img src="figures/Density curve for the cleaned data.png">
</p>

---

## Cleaned Feature Boxplots

<p align="center">
<img src="figures/Boxplot for the cleaned dataset.png">
</p>

The cleaned dataset demonstrates improved feature consistency and reduced noise, providing a stronger foundation for model training.

---

# Deep Learning Models

Three fully connected neural network architectures were implemented using **PyTorch**.

| Model | Hidden Layers | Dropout |
|:------|:-------------:|:--------:|
| Exp1 Small | 32 → 16 | 0.20 |
| Exp2 Medium | 64 → 32 | 0.20 |
| Exp3 Large | 128 → 64 | 0.30 |

All models were trained using:

- PyTorch
- Adam Optimiser
- Binary Cross-Entropy Loss
- Early Stopping
- Mini-batch Gradient Descent

---

# Training Behaviour

## Small MLP

<p align="center">
<img src="figures/Loss curve of the Small Hidden Layers.png">
</p>

---

## Medium MLP

<p align="center">
<img src="figures/Loss curve of the Medium Hidden Layers.png">
</p>

---

## Large MLP

<p align="center">
<img src="figures/Loss curve of the Large Hidden Layers.png">
</p>

The larger architecture demonstrated the most stable learning behaviour while achieving the highest validation ROC-AUC.

---

# Model Comparison

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|:------|---------:|----------:|--------:|---------:|---------:|
| Exp1 Small | **79.31%** | **64.29%** | **90.00%** | **75.00%** | 0.8655 |
| Exp2 Medium | 78.45% | 64.15% | 85.00% | 73.12% | 0.8632 |
| **Exp3 Large** | 77.59% | 63.46% | 82.50% | 71.74% | **0.8704** |

Although the Small model achieved the highest validation accuracy and F1-score, the Large model produced the strongest ROC-AUC, providing the best overall discrimination capability and was therefore selected as the final model.

---

# ROC Analysis

<p align="center">
<img src="figures/ROC curve.png" width="750">
</p>

The selected model achieved an **Area Under the ROC Curve (AUC) of approximately 0.86**, demonstrating strong discrimination between diabetic and non-diabetic patients across varying classification thresholds.

---

# Validation Performance

<p align="center">
<img src="figures/Confusion Matrix.png">
</p>

The validation confusion matrix indicates that the model correctly identifies the majority of diabetic and non-diabetic cases while maintaining a balanced trade-off between sensitivity and specificity.

---

# Final Test Evaluation

<p align="center">
<img src="figures/Confusion Matrix - Test Set.png">
</p>

The final model was evaluated on an unseen test dataset.

| Metric | Value |
|:-------|------:|
| Accuracy | 72.55% |
| Precision | 61.19% |
| Recall | 71.93% |
| F1-score | 66.13% |

These results demonstrate that the selected model generalises reasonably well to previously unseen data while maintaining useful predictive performance.

---

# Repository Structure

```text
Diabetes-MLP-Classification/
│
├── notebooks/
│   └── diabetes-mlp-classification.ipynb
│
├── figures/
│
├── data/
│
├── reports/
│
├── results/
│
├── README.md
│
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

- Medical data preprocessing
- Exploratory data analysis
- Feature engineering
- Deep neural network development
- Binary classification
- Model comparison
- ROC analysis
- Performance evaluation
- PyTorch implementation
- Healthcare machine learning

---

# Reproducing the Project

To reproduce the experiments:

1. Clone this repository.
2. Install the required Python dependencies.
3. Place the dataset in the `data/` directory.
4. Run:

```bash
jupyter notebook notebooks/diabetes-mlp-classification.ipynb
```

Training the notebook will reproduce the preprocessing pipeline, model comparison experiments, evaluation metrics, and visualisations presented in this repository.

---

# Limitations

- The dataset is relatively small compared with modern clinical datasets.
- Only fully connected neural networks were investigated.
- Hyperparameter optimisation was intentionally limited.
- This model is intended for educational and research purposes only and should not be used for clinical diagnosis.

---

# Acknowledgement

This repository presents a professionally organised version of a university deep learning project. The implementation, methodology, and reported experimental results remain unchanged, while the repository structure, documentation, and presentation have been redesigned to showcase the project as part of a professional machine learning portfolio.