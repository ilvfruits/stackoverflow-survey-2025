---
layout: post
title: "Predicting Developer Salary Using the Stack Overflow Survey"
tags: [data-analysis, machine-learning, stackoverflow]
---

## Overview

This project explores whether we can **reasonably predict a developer’s annual compensation**
using self-reported survey data from the Stack Overflow Developer Survey.

This is a **demo-level machine learning project**, focused on clarity and interpretability
rather than production-grade prediction.

---

## Dataset

- Source: Stack Overflow Developer Survey (ODbL license)
- Respondents: ~80,000 developers worldwide
- Data type: Self-reported survey responses

### Features used

- Years of professional coding experience
- Country
- Primary developer role
- Primary programming language
- Education level

Target variable:
- Annual compensation (USD, normalized by Stack Overflow)

---

## Data Cleaning

Key cleaning steps:

- Removed missing or extreme salary values
- Converted years of experience to numeric
- Simplified multi-select fields by selecting the primary response
- Dropped incomplete records after feature selection

These choices intentionally trade completeness for **simplicity and explainability**.

---

## Model Design

We trained a **Random Forest Regressor** using:

- One-hot encoding for categorical features
- 80/20 train-test split
- No hyperparameter tuning (baseline model)

Why Random Forest?
- Handles non-linear relationships well
- Robust to mixed feature types
- Strong baseline for tabular survey data

---

## Results

### Model performance

- **Mean Absolute Error (MAE):** ~$20,000
- **R² Score:** ~0.50

Interpretation:
- Predictions are often within ~$20k of reported salary
- Roughly half of salary variance is explained by the model

---

## Visualization

### Predicted vs Actual Salary

![Predicted vs Actual Salary](/assets/images/salary_vs_pred.png)

The model captures general salary trends but struggles with
high-income outliers, which is expected given the survey nature
of the data.

---

## Key Takeaways

- Years of experience is the strongest predictor
- Geography introduces large salary variance
- Role and language add signal, but less than experience
- Education has limited incremental impact

---

## Limitations

- Self-reported data
- No company size or industry normalization
- Multi-select responses simplified
- Not suitable for individual salary negotiation

---

## Conclusion

This project demonstrates an **end-to-end ML workflow** using real-world survey data:

- Data cleaning
- Feature engineering
- Model training
- Interpretation and communication

The goal is insight and learning—not precise salary prediction.

---

## Code & Reproducibility

All code, notebooks, and raw data are available in the same repository:

- Jupyter notebooks for analysis
- Python scripts for reusable components
- GitHub Pages for public reporting
