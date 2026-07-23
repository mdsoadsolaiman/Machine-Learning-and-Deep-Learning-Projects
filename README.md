# Machine Learning and Deep Learning Projects

## Overview

This repository presents four university coursework projects reorganised as a professional machine-learning and deep-learning portfolio. The projects demonstrate image and tabular preprocessing, neural-network design, classical supervised learning, model evaluation, ablation studies and clustering while preserving the limitations of the original evidence.

## Portfolio Projects

| Project | Learning type | Problem | Primary models | Best verified result | Link |
|---|---|---|---|---|---|
| Butterfly CNN Classification | Supervised deep learning | Five-class image classification | Compact CNN | 72.22% internal test accuracy on 18 images | [Project](butterfly-cnn-classification/) |
| Diabetes MLP Classification | Supervised deep learning | Binary tabular classification | MLPs | Final test ROC-AUC 0.8480 | [Project](diabetes-mlp-classification/) |
| Blood-Cell MiniResNet Classification | Supervised deep learning | Eight-class image classification | MiniResNet, CNN and MLP | 97.66% peak validation accuracy; detailed loaded-state accuracy 96.88% | [Project](blood-cell-miniresnet-classification/) |
| MNIST Classification and Clustering | Supervised and unsupervised learning | Binary classification and digit-7 clustering | Logistic Regression, RBF SVM, PCA and K-Means | LR mean CV F1 1.0000; RBF SVM mean CV F1 ≈ 0.9699 | [Project](mnist-classification-and-clustering/) |

## Technical Skills

- Python, PyTorch, Torchvision and scikit-learn
- NumPy, Pandas, Matplotlib, Seaborn, OpenCV and Pillow
- Image and tabular-data preprocessing
- CNNs, MLPs and residual networks
- Logistic Regression, support vector machines, PCA and K-Means
- Hyperparameter tuning, class weighting and regularisation
- Model evaluation, confusion matrices, ROC-AUC and ablation studies

## Academic Context

All four projects originated as university coursework. They have been renamed, cleaned and documented for portfolio presentation without representing them as commercial deployments, clinical systems, peer-reviewed research or industry-validated models. The original academic reports are retained where available and are clearly identified.

## Dataset Availability

Raw datasets are excluded where redistribution permission, provenance or licence terms have not been confirmed. Each project contains a `data/README.md` describing the expected local structure and lawful configuration process. No fabricated download links are provided.

## Repository Structure

```text
machine-learning-and-deep-learning-projects/
├── butterfly-cnn-classification/
├── diabetes-mlp-classification/
├── blood-cell-miniresnet-classification/
├── mnist-classification-and-clustering/
├── README.md
├── LICENSE
├── .gitignore
└── requirements.txt
```

## Reproducibility

The notebooks use relative or environment-configurable dataset paths and provide readable errors when excluded data is unavailable. Random seeds have been added where practical. Exact historical dependency versions were not recorded, and expensive models were not retrained during portfolio preparation; exact numerical reproduction is therefore not guaranteed.

## Limitations

- Restricted or unverified datasets are not distributed.
- Several evaluations use small or validation-only splits.
- The blood-cell test set had no ground-truth labels.
- No blood-cell checkpoint is included.
- Original academic reports may preserve historical wording or discrepancies documented by their project READMEs.

## Author

Md Soad Solaiman

## Licence Scope

The MIT licence applies only to original code and newly authored repository documentation. Third-party datasets, academic course materials, reports and excluded data remain subject to their own terms.
