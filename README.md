# Malicious URL Detection — Multi-Model Comparative Analysis

> **Machine Learning & Cybersecurity Project** | ESI-SBA | 2024/2025

## Overview

A comprehensive cybersecurity project implementing and comparing multiple machine learning and deep learning approaches for detecting malicious URLs. The system classifies URLs into four threat categories (benign, defacement, phishing, malware) using TF-IDF character n-gram features and a suite of traditional and neural models. This work demonstrates end-to-end ML pipeline design, from feature engineering to model evaluation and comparative benchmarking.

## Dataset

- **Source:** [Kaggle Malicious URLs Dataset](https://www.kaggle.com/datasets/sid321axn/malicious-urls-dataset)
- **Size:** 651,191 URLs
- **Classes:** Benign, Defacement, Phishing, Malware
- **Split:** 80/20 stratified train-test

## Feature Engineering

- **URL-based features:** length, special character counts, domain analysis, IP pattern detection, digit counts
- **TF-IDF Vectorization:** character-level n-grams (3-5 grams), 10,000 features
- **Total features:** 15+ handcrafted + 10,000 TF-IDF

## Models Implemented

| Model | Type | Key Parameters |
|-------|------|---------------|
| Logistic Regression | Traditional ML | One-vs-Rest, L2 regularization |
| Random Forest | Ensemble ML | 100 estimators, feature importance |
| XGBoost | Gradient Boosting | 100 estimators, optimized for speed |
| LSTM | Deep Learning | Embedding (64d) → LSTM (100 units) → Dense → Softmax |

## Results

| Model | Accuracy | F1-Score | Training Time |
|-------|----------|----------|---------------|
| Logistic Regression | 95.5% | 95.4% | ~45s |
| **Random Forest** | **96.8%** | **96.7%** | ~180s |
| XGBoost | 96.5% | 96.4% | ~120s |
| LSTM | 94.2% | 94.1% | ~450s |

**Best Overall:** Random Forest (highest F1-score with balanced performance).

## Tech Stack

- Python 3.8+, Jupyter Notebooks
- Scikit-learn, XGBoost, TensorFlow/Keras
- Pandas, NumPy, Matplotlib, Seaborn, Plotly

## Repository Structure

```
.
├── code.ipynb              # Main implementation notebook
├── report.pdf              # Detailed project report
├── README.md                 # This file
└── Generated Outputs/        # Visualizations (auto-generated)
```

## Usage

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost tensorflow plotly

# Run the notebook
jupyter notebook code.ipynb
```

## Key Insights

1. **Random Forest** achieved the best trade-off between accuracy and interpretability.
2. **TF-IDF character n-grams** (3-5) significantly outperformed word-level features for URL classification.
3. **LSTM** showed promise but required more tuning and data to match ensemble methods.
4. Feature importance analysis revealed URL length and special character density as top predictors.

## Authors

**Adem Toumi** — ESI-SBA, Engineering Degree in AI & Data Science  
**Ahmed Saadi** — ESI-SBA, Engineering Degree & M2 in AI & Data Science

## License

MIT
