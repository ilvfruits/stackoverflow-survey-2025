---
layout: post
title: "Can We Predict the Salary of a Developer?"
tags: [data-analysis, machine-learning, stackoverflow]
---

## Overview

This project explores whether we can **reasonably predict a developer’s annual compensation**
using self-reported survey data from the 2025 Stack Overflow Developer Survey.

#### Project motivations:
- I would like to understand how coding experience, programming language, years of coding experience, education level, and job positions affect the salary of developers.
- I also wonder if it is possible to predict the salary using these factors.

---

## Section 1: Business Understanding
#### The project aim to answer below questions.
- How does the coding experience influence salary of developer?
- How does the role affect the salary of developers?
- Does developer salary vary with country?
- Would education level change the salary of developers?
- Which language has highest salary?
- Can we train a Random Forest Model to predict salary using selected features?

---

## Section 2: Data Understanding

## Dataset
- Source: 2025 Stack Overflow Developer Survey (ODbL license)
- Respondents: 49,000+ responses from 177 countries
- Data type: Self-reported survey responses

### Features used
- Years of professional coding experience
- Country
- Primary developer role
- Primary programming language
- Education level
- Annual compensation (USD, normalized by Stack Overflow)

### Data cleaning
- Removed missing or extreme salary values
- Converted years of experience to numeric
- Simplified multi-select fields (primary role, primary language) by selecting the first response
- Dropped incomplete records after feature selection

These choices intentionally trade completeness for **simplicity and explainability**.

---

## Section 4: Data Modeling
We trained a **Random Forest Regressor** using:
- One-hot encoding for categorical features
- 80/20 train-test split
- No hyperparameter tuning (baseline model)

---

## Section 5: Evaluation

### Feature Analysis

### How does the coding experience influence salary of developer?
![How does the coding experience influence salary of developer?]({{site.baseurl}}/assets/images/salary_vs_experience.png)
#### Observations
- To answer this question, a scatter plot is created to observe the correlation between salary and years of coding experience.
- Salary increases with years of coding experience.
- However, data is in wide range of variance, suggesting other factors also matter.

### How does the role affect the salary of developers?
![How does the role affect the salary of developers?]({{site.baseurl}}/assets/images/salary_by_role.png)
#### Observations
- To answer this question, a boxplot graph is created to observe the salary distributions for each role.
- Architect, software or solutions, has highest median salary than other roles.
- Each role has many outliers on top salary range. This could be due to other reasons, such as country, experience, etc.

### Does developer salary vary with country?
![Does developer salary vary with country?]({{site.baseurl}}/assets/images/salary_by_country.png)
#### Observations
- To answer this question, a boxplot graph is created to compare salaries from different countries.
- Developers from United States have highest median salaries compared to other countries.
- Each country has many outliers on top salary range due to other reasons, such as experience, role, etc.

### Would education level change the salary of developers?
![Would education level change the salary of developers?]({{site.baseurl}}/assets/images/salary_by_education.png)
#### Observations
- To answer this question, a boxplot graph is created to compare salaries of develops with different educations.
- The median salary ranking follows the order of Professional > Master's > Bachelor's > Associate > Others.
- However, the difference between education levels is quite small.
- The education levels above college or secondary school level have many outliers in high salary range. The graduate degree didn't show obvious benefits than college degree.

### Which language has highest salary?
![Which language has highest salary?]({{site.baseurl}}/assets/images/salary_by_language.png)
#### Observations
- To answer this question, a boxplot graph is created to compare salaries across different programming languages.
- The median salary ranking follows the order of Go > Bash/Shell > C# > Java > Others
- The difference between languages is very small. 
- All languages have outliers in high salary ranges. The Bash/Shell and Assembly have highest outliers than others, possibly due to a demand in specific expertise.

### Can we train a Random Forest Model to predict salary using selected features?
- The predicted value is aligned with true values in low salary range (<400,000).
- The model underpredicted the high salary range (>=400,000). There could be other factors contribute to the high salary.
![Predicted vs Actual Salary]({{site.baseurl}}/assets/images/predicted_vs_true.png)
  
### Feature Importance
![Feature Importance]({{site.baseurl}}/assets/images/feature_importance.png)
- Country is the strongest factor. It explains about 48% of the model's predictive power.
- Years of coding experience is the second strongest factor, explaining about 26% of the model's predictive power.
- Professional role explains about 13% of the model's predictive power.
- The programming language and education level have small influence, with each one explaining less than 10% of the model's predictive power.

### Model performance
- **Mean Absolute Error (MAE):** ~$38,511
- **R² Score:** ~0.39

Interpretation:
- Predictions are often within ~$39k of reported salary.
- Roughly 40% of salary variance is explained by the model.
- The 60% of unexplained variance could be due to missing factors, such as network, negotiation skills.

---
### Conclusions
 - The major factors to influence developer salary are country and coding experience, together explaining about 75% of model's predictive power.
 - The RF model can explain roughly 40% of salary variance. It underestimated the salary for high value range (>400,000), possibly due to missing other factors.

### Limitations

- The data is self-reported and may not be accurate
- Model prediction power is limited (R²=0.44)
- Many factors are ignored to simplify the model for demo purpose

