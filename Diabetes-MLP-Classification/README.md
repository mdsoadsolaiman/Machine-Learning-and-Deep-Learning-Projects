# 🩺 Diabetes Prediction using Multi-Layer Perceptron (PyTorch)

> An end-to-end deep learning project that develops, compares, and evaluates multiple Multi-Layer Perceptron (MLP) architectures for diabetes prediction using clinical measurements.

![Validation Comparison](figures/validation-experiment-comparison.png)

---

## Project Overview

Early identification of diabetes can support timely clinical intervention and reduce long-term health complications. This project develops an MLP classifier in **PyTorch** using the **Pima Indians Diabetes Dataset** and systematically compares three neural network architectures under identical experimental conditions.

The final model was selected using **ROC-AUC**, providing a clinically meaningful assessment of discrimination performance beyond simple accuracy.

---

## Dataset

The dataset contains **768 patient records** with eight clinical features:

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Diabetes Pedigree Function
- Age

Target:
- Outcome (0 = Non-diabetic, 1 = Diabetic)

---

## Data Preprocessing

The preprocessing pipeline included:

- Exploratory data analysis (histograms, boxplots, density plots and correlation heatmap)
- Identification of physiologically impossible zero values
- Mean imputation for Blood Pressure and Skin Thickness zeros
- Class-wise IQR outlier treatment for Glucose and BMI
- Z-score feature standardisation
- Stratified train/validation split

![Feature Distributions](figures/cleaned-feature-distributions.png)

![Correlation Heatmap](figures/feature-correlation-heatmap.png)

---

## Model Development

All models were implemented using:

- PyTorch
- ReLU activation
- Adam optimiser
- BCEWithLogitsLoss
- Dropout regularisation
- Early stopping
- Mini-batch training

| Model | Hidden Layers | LR | Dropout |
|-------|---------------|----:|---------:|
| Exp1 Small | 32 → 16 | 0.0100 | 0.20 |
| Exp2 Baseline | 64 → 32 | 0.0010 | 0.20 |
| **Exp3 Large** | **128 → 64** | **0.0005** | **0.30** |

---

## Validation Performance

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|------|---------:|----------:|-------:|---:|--------:|
| Exp1 Small | 0.7931 | 0.6429 | **0.9000** | **0.7500** | 0.8655 |
| Exp2 Baseline | 0.7845 | 0.6415 | 0.8500 | 0.7312 | 0.8632 |
| **Exp3 Large** | 0.7759 | 0.6346 | 0.8250 | 0.7174 | **0.8704** |

The Large MLP achieved the highest validation ROC-AUC and was selected as the final model.

![Training Curves](figures/training-loss-curves.png)

---

## Final Test Performance

| Metric | Score |
|--------|------:|
| Accuracy | **74.51%** |
| Precision | **63.64%** |
| Recall | **73.68%** |
| F1-score | **68.29%** |
| ROC-AUC | **0.8480** |

![Confusion Matrix](figures/test-confusion-matrix.png)

The selected model demonstrated good generalisation while maintaining strong sensitivity for identifying diabetic patients.

---

## Repository Structure

```text
diabetes-mlp-classification/
├── data/
├── figures/
├── notebooks/
├── reports/
├── results/
└── README.md
```

---

## Technologies

- Python
- PyTorch
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## Key Learning Outcomes

- Clinical data preprocessing
- Exploratory data analysis
- Neural network design
- Hyperparameter comparison
- Medical AI evaluation
- ROC-AUC based model selection

---

## Acknowledgement

This repository is a professionally documented version of an academic coursework project. The underlying methodology and experimental findings remain unchanged while the documentation has been redesigned for reproducibility and portfolio presentation.
