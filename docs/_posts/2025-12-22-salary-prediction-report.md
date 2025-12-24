---
layout: post
title: "Can We Predict the Salary of a Developer?"
tags: [data-analysis, machine-learning, stackoverflow]
---

## Overview

This project explores whether we can **reasonably predict a developer’s annual compensation**
using self-reported survey data from the Stack Overflow Developer Survey.

This is a **demo-level machine learning project**, focused on clarity and interpretability
rather than production-grade prediction.

---

## Dataset

- Source: 2025 Stack Overflow Developer Survey (ODbL license)
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
- Simplified multi-select fields (primary role, primary language) by selecting the first response
- Dropped incomplete records after feature selection

These choices intentionally trade completeness for **simplicity and explainability**.

---

## Model Design

We trained a **Random Forest Regressor** using:

- One-hot encoding for categorical features
- 80/20 train-test split
- No hyperparameter tuning (baseline model)

---

## Results

## Visualization

### Feature Analysis

### How does the coding experience influence salary of developer?
![How does the coding experience influence salary of developer?]({{site.baseurl}}/assets/images/salary_vs_experience.png)
#### Observations
- Salary increase with years of coding experience.
- However, data is in wide range of variance, suggesting other factors also matter.

### How does the role affect the salary of developers?
![How does the role affect the salary of developers?]({{site.baseurl}}/assets/images/salary_by_role.png)
#### Observations
- Engineering manager has highest median salary than other roles
- The salary range if quite broader due to other reasons, such as country, experience, etc.

### Does developer salary vary with country?
![Does developer salary vary with country?]({{site.baseurl}}/assets/images/salary_by_country.png)
#### Observations
- Developers from United States have highest median salary compared to other countries.

### Would education level change the salary of developers?
![Would education level change the salary of developers?]({{site.baseurl}}/assets/images/salary_by_education.png)
#### Observations
- The education level has marginal influence on the median salary of developers.

### Which language has highest salary?
![Which language has highest salary?]({{site.baseurl}}/assets/images/salary_by_language.png)
#### Observations
- The language has marginal influence on the median salary of developers.

### Can we train a Random Forest Model to predict salary using selected features?
![Predicted vs Actual Salary]({{site.baseurl}}/assets/images/predicted_vs_true.png)

### Feature Importance
![Feature Importance]({{site.baseurl}}/assets/images/feature_importance.png)

### Observations
- Country of United States is the strongest factor
- Years of professional experience is the second strongest factor
- Other factors have marginal influence

### Model performance

- **Mean Absolute Error (MAE):** ~$34,984
- **R² Score:** ~0.44

Interpretation:
- Predictions are often within ~$35k of reported salary
- Roughly half of salary variance is explained by the model

---

### Limitations

- The data is self-reported and may not be accurate
- Model prediction power is limited (R²=0.44)
- Many factors are ignored to simplify the model for demo purpose

