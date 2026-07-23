# Butterfly CNN Classification

> This project was originally completed as part of university coursework and has been reorganised and documented for professional portfolio presentation.

## Project Overview

A compact PyTorch CNN classifies five butterfly categories and compares optimiser settings using an internal train/validation/test split.

## Academic Context

The work was completed as a university coursework project. The public version retains the original technical evidence while improving naming, navigation, transparency and evaluation context.

## Problem Statement

Develop an image-classification workflow for a small, imbalanced butterfly dataset and evaluate alternative optimisation settings.

## Dataset

Course-provided images are excluded. The cleaned working set contained 113 images across five highly imbalanced classes; see [data access](data/README.md).

## Data Preparation

Invalid labels and unreadable or near-black images were identified non-destructively. Images were resized to 64×64 pixels and normalised.

## Methodology

Three optimiser and learning-rate configurations were trained for five epochs under a consistent internal split.

## Model Architecture

Three convolutional blocks (16, 32 and 64 channels) feed a 128-unit dense layer and five-class output.

## Experimental Design

The split contained 79 training, 16 validation and 18 internal test images. SGD and two Adam learning rates were compared.

## Results

Adam at 0.001 achieved 93.75% validation accuracy and 72.22% accuracy on the 18-image internal test split. See [results](results/internal-test-results.csv).

## Key Findings

The experiment demonstrates CNN construction, data preparation and controlled optimiser comparison.

## Limitations

The dataset is small and severely imbalanced. The supplied external 30-image test set was not evaluated, and the result does not demonstrate deployment readiness.

## Technologies

Python, PyTorch, Torchvision, OpenCV, NumPy, Pandas and Matplotlib.

## Repository Structure

```text
notebooks/  Cleaned portfolio notebook
figures/    Verified statistical and performance visuals
results/    Internal evaluation summary
data/       Access and licensing guidance
```

## Reproduction Instructions

Install the root requirements, obtain the data lawfully, set `BUTTERFLY_DATA_DIR`, and run the notebook sequentially. Exact historical package versions were not recorded.
