# XGBoost Oncology Classification: Breast Cancer Diagnostics

## Executive Summary
This repository contains a comprehensive supervised machine learning analysis of the Breast Cancer Wisconsin dataset using R and the **XGBoost (Extreme Gradient Boosting)** algorithm. 

While unsupervised models (like K-Means) are excellent for identifying hidden patient clusters, clinical diagnostics require high-precision supervised models to predict malignancy. This project focuses on building a robust classification model to distinguish between Benign and Malignant tumors, while deeply visualizing the algorithm's internal decision-making process to ensure clinical interpretability.

## Tech Stack & Methodology
* **Language & Environment:** R, R Markdown
* **Core Libraries:** `xgboost`, `caret`, `caTools`, `dplyr`, `ggplot2`, `DiagrammeR`
* **Algorithm:** Extreme Gradient Boosting (Objective: Binary Logistic)
* **Hyperparameters:** Max Depth = 6, Rounds = 50, Learning Rate (eta) = 0.1

## Key Analytical Features

### 1. High-Precision Classification
The XGBoost model was trained on a 75/25 train-test split, utilizing a DMatrix architecture for optimized computation. The evaluation via the confusion matrix demonstrates the model's accuracy in predicting the binary target variable (0 = Benign, 1 = Malignant), effectively minimizing critical diagnostic errors.

### 2. Feature Importance Extraction
In clinical data science, knowing *why* a model made a decision is as important as the decision itself. The analysis utilizes XGBoost's Gain metrics to extract the relative importance of biological features. The mathematical consensus of the model identified **Uniformity of Cell Size** and **Uniformity of Cell Shape** as the absolute primary indicators of malignancy.

### 3. Visualizing the Decision Logic

Black-box algorithms are often rejected in healthcare. To counter this, the project utilizes the `DiagrammeR` package to map and visualize the exact threshold splits of the foundational decision tree within the XGBoost ensemble. This provides transparent, auditable logic for how biological measurements are algorithmically routed to a final diagnosis.

### 4. Tumor Cluster Analysis

To overcome the limitations of integer-based clinical scoring (which causes data point overlap), the analysis features a custom **Jitter Plot combined with 2D Density Contours**. This effectively visualizes the exact density zones where benign cases cluster (low uniformity variance) versus the highly dispersed malignant cases.

## Conclusion
This R Markdown report proves that XGBoost can serve as a highly accurate and, more importantly, fully interpretable diagnostic assistant. By combining advanced gradient boosting mathematics with transparent decision-tree plotting and density visualization, this pipeline bridges the gap between raw algorithmic power and clinical trust.
