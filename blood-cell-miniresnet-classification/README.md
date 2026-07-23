# Blood-Cell MiniResNet Classification

> This project was originally completed as part of university coursework and has been reorganised and documented for professional portfolio presentation.

## Project Overview

An eight-class image-classification study using a compact residual network, baseline comparisons and controlled ablations.

## Academic Context

The work was completed as a university coursework project. The public version retains the original technical evidence while improving naming, navigation, transparency and evaluation context.

## Problem Statement

Assess whether residual learning, class weighting, label smoothing and optimiser design improve validation performance.

## Dataset

All 4,200 university-provided images are excluded. The 1,000 test images had no ground-truth labels; see [data access](data/README.md).

## Data Preparation

Images were checked for corruption and blur, resized to 224×224, normalised and augmented. Blurred images were retained.

## Methodology

MiniResNet was compared with SimpleCNN and MLP baselines, followed by ablations for class weighting, label smoothing and optimiser/scheduler design.

## Model Architecture

A compact residual architecture uses four two-block stages with 32, 64, 128 and 256 channels, adaptive average pooling and an eight-class head.

## Experimental Design

The 3,200 labelled images were split into 2,560 training and 640 validation samples using a seeded random split.

## Results

Peak validation accuracy was 97.66%. A distinct detailed loaded-state evaluation achieved 96.88% accuracy, 96.86% macro F1 and 99.75% macro ROC-AUC.

## Key Findings

Residual modelling substantially outperformed the inspected MLP and SimpleCNN baselines, while ablations quantified the contribution of training choices.

## Limitations

No labelled test evaluation or checkpoint is available. The original unchanged academic report contains a student identifier and should be reviewed before public release.

## Technologies

Python, PyTorch, Torchvision, OpenCV, Pillow, NumPy, Matplotlib and scikit-learn.

## Repository Structure

```text
notebooks/  Cleaned portfolio notebook
reports/    Original academic report
figures/    Curves, comparisons, confusion matrix and ROC
results/    Architecture, ablation and loaded-state summaries
data/       Class mapping and access guidance
```

## Reproduction Instructions

Install the root requirements, obtain authorised images, set `BLOOD_CELL_DATA_DIR`, and run the notebook. Reproduction requires fresh training because no checkpoint is included.
