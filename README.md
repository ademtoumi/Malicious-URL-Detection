# Machine Learning-Based URL Classification

**Machine Learning Project — ESI-SBA, 2024–2025**

---

## Overview

This project presents a comparative study of machine learning and deep learning models for multi-class URL classification. Four model families are trained and evaluated on a large-scale labeled dataset, with the goal of identifying the approach that best balances classification accuracy and generalization across URL categories. Feature engineering combines statistical text representations with handcrafted structural descriptors.

---

## Dataset

- **Size:** 651,191 URLs
- **Classes:** 4 — benign, defacement, phishing, malware
- **Split:** 80% training / 20% test (stratified by class)
- **Source:** Publicly available URL classification dataset

---

## Objectives

- Engineer a hybrid feature set combining TF-IDF character n-gram representations with handcrafted URL structural features.
- Train and compare four model architectures (Logistic Regression, Random Forest, XGBoost, LSTM) under consistent evaluation conditions.
- Identify the model configuration that achieves the highest F1-score across all four URL classes.

---

## Methodology

1. **Feature Engineering**
   - TF-IDF character n-grams (3–5 gram range, 10,000 features) applied to the raw URL string.
   - 15+ handcrafted structural features: URL length, digit count, special character frequencies, domain structure analysis, IP address detection, subdomain depth, and path segment statistics.

2. **Model Training**
   - Each model is trained on the combined feature matrix.
   - Hyperparameters are tuned per model; class imbalance is addressed through stratified sampling.

3. **Comparative Evaluation**
   - Models are evaluated on the held-out test set using accuracy and macro-averaged F1-score.
   - Results are analyzed per class and aggregated for overall comparison.

---

## Models

| Model               | Type                  | Key Configuration                                      |
|---------------------|-----------------------|--------------------------------------------------------|
| Logistic Regression | Linear classifier     | L2 regularization, multi-class one-vs-rest             |
| Random Forest       | Ensemble (bagging)    | 100 estimators, feature subsampling                    |
| XGBoost             | Ensemble (boosting)   | Gradient boosted trees, early stopping                 |
| LSTM                | Deep learning (RNN)   | Sequence model on character-level URL encoding         |

---

## Technologies

Python · Scikit-learn · XGBoost · TensorFlow · Pandas · NumPy · Matplotlib · Jupyter Notebook

---

## Results

| Model               | Accuracy | F1-Score     |
|---------------------|----------|--------------|
| Logistic Regression | 95.5%    | 95.4%        |
| **Random Forest**   | **96.8%**| **96.7%**    |
| XGBoost             | 96.5%    | 96.4%        |
| LSTM                | 94.2%    | 94.1%        |

> Random Forest achieved the highest macro-averaged F1-score of 96.8% across all four classes.

---

## Report

[Project Report](report.pdf)

---

Academic Project — Higher School of Computer Science (ESI-SBA), Sidi Bel Abbès, Algeria — 2024/2025

Authors: Adem Toumi — ESI-SBA | Ahmed Saadi — ESI-SBA
