# Handwritten Digit Classification and Clustering

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB" alt="Python">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E" alt="Scikit-Learn">
  <img src="https://img.shields.io/badge/Machine%20Learning-1565C0" alt="Machine Learning">
  <img src="https://img.shields.io/badge/PCA-6A1B9A" alt="PCA">
  <img src="https://img.shields.io/badge/K--Means-2E7D32" alt="K-Means">
  <img src="https://img.shields.io/badge/SVM-C62828" alt="Support Vector Machine">
</p>

This machine learning project investigates handwritten digit recognition by combining supervised classification and unsupervised clustering techniques. Logistic Regression and Support Vector Machines were developed to distinguish handwritten digits **1** and **7**, while Principal Component Analysis (PCA) and K-Means clustering were used to explore the natural variation in handwriting styles within digit **7**.

---

# Project Overview

Handwritten digit recognition is a classic pattern recognition problem that demonstrates the capabilities of machine learning for image classification. While supervised learning focuses on predicting the correct digit label, unsupervised learning can reveal hidden structure and stylistic variation within the data.

This project integrates both approaches into a single workflow by:

- preprocessing handwritten image data,
- reducing dimensionality using PCA,
- building supervised classification models,
- optimising model hyperparameters,
- evaluating predictive performance, and
- analysing handwriting style variation using K-Means clustering.

The project demonstrates an end-to-end classical machine learning pipeline using the Scikit-Learn ecosystem.

---

# Objectives

The project aims to:

- classify handwritten digits **1** and **7** using supervised learning;
- compare Logistic Regression and RBF Kernel SVM performance;
- optimise model performance using cross-validation and grid search;
- visualise high-dimensional image data using PCA;
- identify natural handwriting style groups within digit **7** using K-Means clustering; and
- interpret cluster characteristics through centroid and representative image analysis.

---

# Dataset

The project uses a subset of the MNIST handwritten digit dataset containing digits **1** and **7**.

Each image:

- grayscale
- 28 × 28 pixels
- flattened into numerical feature vectors
- standardised before model training

*The dataset itself is not included in this repository. Refer to the `data/README.md` for dataset access and licensing information.*

---

# Machine Learning Workflow

```text
MNIST Dataset
        │
        ▼
Data Preprocessing
        │
        ▼
Feature Scaling
        │
        ▼
Principal Component Analysis
        │
 ┌─────────────────────────────┐
 │                             │
 ▼                             ▼
Supervised Learning      Unsupervised Learning
 │                             │
 ▼                             ▼
Logistic Regression      K-Means Clustering
RBF Kernel SVM           Elbow Method
Grid Search              Silhouette Analysis
Cross Validation         Cluster Interpretation
 │                             │
 └──────────────┬──────────────┘
                ▼
        Performance Evaluation
```

---

# Exploratory Data Analysis

Principal Component Analysis (PCA) was applied to visualise the high-dimensional image space in two dimensions.

The projection shows that handwritten digits **1** and **7** occupy largely distinct regions, providing an intuitive explanation for the strong classification performance achieved by the supervised models.

<p align="center">
<img src="figures/pca_projection.png" width="750">
</p>

---

# Supervised Classification

Two classical machine learning algorithms were implemented and compared.

## Logistic Regression

Logistic Regression provides a strong linear baseline for binary image classification.

Performance was evaluated using:

- five-fold stratified cross-validation;
- confusion matrix analysis; and
- F1-score.

<p align="center">
<img src="figures/logistic_confusion_matrix.png" width="550">
</p>

---

## Support Vector Machine (RBF Kernel)

A nonlinear Support Vector Machine with an RBF kernel was developed to capture more complex decision boundaries.

Hyperparameters were optimised using Grid Search Cross Validation.

Parameters explored included:

- C
- Gamma

<p align="center">
<img src="figures/svm_gridsearch_heatmap.png" width="700">
</p>

---

# Classification Results

The supervised models demonstrated excellent discrimination between handwritten digits.

| Model | Performance |
|---------|-------------|
| Logistic Regression | Perfect classification on the evaluation subset |
| RBF Kernel SVM | Mean Cross-Validation F1 ≈ 0.97 |

Both models successfully distinguished handwritten digits despite natural variation in handwriting style.

---

# Unsupervised Learning

To investigate variation within a single digit class, K-Means clustering was applied exclusively to handwritten digit **7**.

Unlike supervised learning, clustering identifies naturally occurring handwriting styles without using class labels.

---

## Selecting the Number of Clusters

Two complementary techniques were used:

- Elbow Method
- Silhouette Analysis

A solution of **k = 9** was selected to provide a meaningful balance between cluster compactness and interpretable handwriting variation.

<p align="center">
<img src="figures/elbow_method.png" width="700">
</p>

<p align="center">
<img src="figures/silhouette_scores.png" width="700">
</p>

---

## Cluster Centres

Each cluster centroid represents the average appearance of a handwriting style within digit **7**.

These centroid images summarise common writing patterns learned by the clustering algorithm.

<p align="center">
<img src="figures/cluster_centers.png" width="800">
</p>

---

## Representative Samples

Representative images from each cluster illustrate the visual differences captured by the algorithm.

Examples include differences in:

- stroke thickness;
- top-bar curvature;
- writing angle;
- vertical alignment; and
- digit proportions.

<p align="center">
<img src="figures/representative_samples.png" width="800">
</p>

---

## Cluster Distribution

Cluster frequencies reveal that some handwriting styles occur much more frequently than others within the dataset.

<p align="center">
<img src="figures/cluster_distribution.png" width="750">
</p>

---

# Key Findings

- Logistic Regression achieved perfect classification on the evaluation subset.
- RBF Kernel SVM achieved a mean cross-validation F1-score of approximately **0.97** after hyperparameter tuning.
- PCA effectively visualised the separation between handwritten digits **1** and **7**.
- K-Means clustering identified nine interpretable handwriting style groups for digit **7**.
- Cluster centroids and representative samples provided meaningful insight into variation within a single handwritten digit class.

---

# Technologies

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-Learn
- PCA
- Logistic Regression
- Support Vector Machine (RBF Kernel)
- K-Means Clustering

---

# Repository Structure

```text
handwritten-digit-classification-clustering/
│
├── data/
│   └── README.md
│
├── figures/
│
├── notebooks/
│
├── reports/
│
├── results/
│
├── README.md
│
└── LICENSE
```

---

# Reproducing the Project

1. Clone the repository.

```bash
git clone https://github.com/mdsoadsolaiman/handwritten-digit-classification-clustering.git
```

2. Install the required packages.

```bash
pip install -r requirements.txt
```

3. Obtain the authorised MNIST subset.

4. Configure the dataset path as described in `data/README.md`.

5. Run the notebook sequentially.

---

# Limitations

- The classification results are based on the coursework evaluation subset rather than a separate held-out benchmark dataset.
- The project focuses on classical machine learning methods rather than deep neural networks.

---

# Acknowledgements

This project was originally completed as part of university coursework and has been reorganised and documented for professional portfolio presentation. All portfolio improvements focus on reproducibility, transparency, and technical communication while preserving the original analytical work.