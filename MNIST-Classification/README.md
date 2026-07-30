# ✍️ Handwritten Digit Classification and Clustering using Machine Learning   ---- ok

### Comparative Analysis of Logistic Regression, RBF Kernel SVM, PCA, and K-Means Clustering on MNIST Digits

> A machine learning study that combines supervised classification and unsupervised clustering to investigate handwritten digit recognition. The project evaluates Logistic Regression and RBF Kernel Support Vector Machine (SVM) for binary digit classification while using Principal Component Analysis (PCA) and K-Means clustering to analyse writing style variations of handwritten digit **7**.

<p align="center">
<img src="figures/PCA Projection of Handwritten Digits 1 and 7.png" width="850">
</p>

---

# Overview

Handwritten digit recognition is a fundamental computer vision problem that has played a significant role in the development of modern machine learning. Beyond accurate classification, understanding the structural variations of handwritten digits provides valuable insight into pattern recognition and feature learning.

This project investigates both **supervised** and **unsupervised** learning techniques using the MNIST handwritten digit dataset.

The study focuses on binary classification of handwritten digits **1** and **7**, followed by clustering analysis of digit **7** to explore different handwriting styles.

The complete workflow includes:

- Data preprocessing
- Exploratory visualisation
- Principal Component Analysis (PCA)
- K-Means clustering
- Cluster validation
- Logistic Regression classification
- RBF Kernel Support Vector Machine
- Hyperparameter optimisation
- Performance evaluation

---

# Methodology

The project uses images from the **MNIST handwritten digit dataset**, one of the most widely used benchmark datasets in machine learning.

Two complementary learning tasks were performed.

## Supervised Learning

Binary classification was developed to distinguish handwritten digits **1** and **7** using:

- Logistic Regression
- RBF Kernel Support Vector Machine (SVM)

Performance was evaluated using:

- Confusion Matrix
- Cross-validation
- F1-score
- Classification accuracy

---

## Unsupervised Learning

To better understand writing style variation, only images of handwritten digit **7** were extracted and analysed using K-Means clustering.

The workflow included:

- Elbow Method
- Silhouette Analysis
- K-Means clustering
- Cluster centre visualisation
- Representative image selection
- Cluster distribution analysis

---

# Exploratory Analysis

## Average Digit Appearance

<p align="center">
<img src="figures/Average Digit 1.png" width="350">
<img src="figures/Average Digit 7.png" width="350">
</p>

The average images illustrate the common structural characteristics learned from each digit class. Digit **1** demonstrates consistent vertical strokes, whereas digit **7** exhibits greater variation in horizontal bars and diagonal writing styles.

---

## PCA Projection

<p align="center">
<img src="figures/PCA Projection of Handwritten Digits 1 and 7.png">
</p>

Principal Component Analysis projects the high-dimensional pixel space into two principal components, allowing visual inspection of class separability. The projection demonstrates that digits **1** and **7** form distinct clusters with only limited overlap, indicating that they are well suited for binary classification.

---

# K-Means Clustering

To investigate handwriting diversity, K-Means clustering was applied exclusively to handwritten digit **7**.

---

## Selecting the Optimal Number of Clusters

### Elbow Method

<p align="center">
<img src="figures/Elbow Method for Optimal Number of Clusters.png">
</p>

The Elbow Method evaluates clustering compactness by measuring within-cluster inertia across different values of **k**.

---

### Silhouette Analysis

<p align="center">
<img src="figures/Silhouette Scores for Different Cluster Sizes.png">
</p>

Silhouette analysis was used alongside the Elbow Method to assess cluster separation and cohesion. Based on both criteria, **k = 9** was selected for the final clustering model.

---

## Cluster Centres

<p align="center">
<img src="figures/Cluster Centers for Handwritten Digit 7.png">
</p>

Each cluster centre represents the average writing style of its assigned group, highlighting differences in stroke angle, horizontal bar length, and digit curvature.

---

## Representative Samples

<p align="center">
<img src="figures/Representative Handwritten Digit 7 Samples.png">
</p>

Representative samples provide real handwritten examples from each cluster, demonstrating the diversity of writing styles captured by the clustering process.

---

## Cluster Distribution

<p align="center">
<img src="figures/Digit 7 Cluster Distribution.png">
</p>

The distribution of samples across the nine clusters indicates that multiple handwriting styles occur naturally within the dataset while remaining reasonably balanced.

---

# Supervised Classification

Two machine learning classifiers were implemented and compared for binary digit recognition.

| Model | Classification Accuracy |
|-------------------------|:----------------:|
| Logistic Regression | **100%** |
| RBF Kernel SVM | **100%** |

Both models achieved perfect classification on the evaluation dataset.

---

# Logistic Regression

## Confusion Matrix

<p align="center">
<img src="figures/Confusion Matrix - Logistic Regression.png" width="500">
</p>

Logistic Regression correctly classified every evaluation sample, demonstrating that the selected feature representation effectively separates handwritten digits **1** and **7**.

---

# Support Vector Machine

## Hyperparameter Optimisation

<p align="center">
<img src="figures/RBF SVM Hyperparameter Tuning Mean CV F1-score.png">
</p>

A grid search was performed across multiple combinations of **C** and **Gamma** values. Cross-validation F1-score was used to identify the optimal model configuration.

---

## Confusion Matrix

<p align="center">
<img src="figures/Confusion Matrix - RBF Kernel SVM.png" width="500">
</p>

The tuned RBF Kernel SVM also achieved perfect classification performance on the evaluation dataset, confirming the strong separability of digits **1** and **7**.

---

# Results Summary

| Analysis | Result |
|-----------------------------|----------------|
| PCA | Clear separation between digits |
| Optimal K | **9 clusters** |
| Clustering Method | K-Means |
| Logistic Regression Accuracy | **100%** |
| RBF SVM Accuracy | **100%** |
| Best SVM Selection | Grid Search + Cross Validation |

The results demonstrate that combining supervised and unsupervised learning provides complementary insights into handwritten digit recognition. While supervised models achieve highly accurate classification, clustering reveals meaningful structural variations in handwriting styles.

---

# Repository Structure

```text
handwritten-digit-classification/
│
├── notebooks/
│   └── handwritten-digit-classification.ipynb
│
├── figures/
│
├── reports/
│
├── results/
│
├── data/
│
├── README.md
│
└── requirements.txt
```

---

# Technologies

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- PCA
- K-Means Clustering
- Logistic Regression
- Support Vector Machine (RBF Kernel)

---

# Reproducing the Project

To reproduce the experiments:

1. Clone this repository.
2. Install the required Python packages.
3. Download the MNIST dataset.
4. Open the notebook:

```bash
jupyter notebook notebooks/handwritten-digit-classification.ipynb
```

Running the notebook reproduces the preprocessing pipeline, clustering analysis, model training, hyperparameter tuning, evaluation metrics, and visualisations presented in this repository.

---

# Limitations

- The classification task is limited to handwritten digits **1** and **7**, rather than the full ten-class MNIST dataset.
- Clustering analysis focuses exclusively on digit **7** to investigate handwriting variability.
- The reported perfect classification accuracy should therefore be interpreted within the scope of this binary classification problem.

---

# Acknowledgement

This repository presents a professionally organised version of a university machine learning project. The methodology, implementation, and experimental results remain unchanged, while the repository structure, documentation, and presentation have been redesigned to showcase the project as part of a professional machine learning portfolio.