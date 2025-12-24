---
layout: post
title: "Which Programming Languages Command the Highest Salaries?"
tags: [stackoverflow, python, data-analysis]
---

## Overview

This analysis explores the trends of languages used by developers using self-reported survey data from the 2025 Stack Overflow Developer Survey.

### Dataset
- Source: 2025 Stack Overflow Developer Survey (ODbL license)
- Respondents: 49,000+ responses from 177 countries
- Data type: Self-reported survey responses

### Results
### Question 1: Which programming languages are used most frequently?
![Language Popularity]({{site.baseurl}}/assets/images/top_languages.png)
#### Observations
- Four top languages (JS, HTML/CSS, SQL, Python) account for almost half of the developers. This trend suggests that database relevant applications are dominating the market.

### Question 2: Which programming language has been used for longest experience?
![Language Experience]({{site.baseurl}}/assets/images/language_vs_experience.png)
#### Observations
- The Delphi and Perl have longer experience than others because they have longer history.
- All developers have almost 20 years coding experience no matter what language they are using.

### Question 3: Which programming languages are paid highest?
![Salary vs Language]({{site.baseurl}}/assets/images/language_vs_salary.png)
![Salary comparison]({{site.baseurl}}/assets/images/language_salary_distribution_ordered.png)
#### Observations
- Language Ruby showed highest median salary, followed by Erlang, Elixir, Perl and Scala. It is interesting that they are not popular languages. It is possibly due to high demand in specific industry, such as finance, telecommunication.

---

### Limitations
- Self-reported data could be biased
- Normalized counts by respondent
- Excluded missing values
