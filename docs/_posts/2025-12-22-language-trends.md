---
layout: post
title: "Which Programming Languages Command the Highest Salaries?"
tags: [stackoverflow, python, data-analysis]
---

## Overview

This analysis explores the trends of languages used by developers using self-reported survey data from the 2025 Stack Overflow Developer Survey.

#### Project motivations
- I would like to learn which language is mostly used by developers.
- I'm also interested on which language is paid highest.

## Section 1: Business Understanding
#### This project aims to answer below questions
- Which programming languages are used most frequently?
- Which programming language has been used for longest experience?
- Which programming languages are paid highest?

## Section 2: Data Understanding

#### Dataset
- Source: 2025 Stack Overflow Developer Survey (ODbL license)
- Respondents: 49,000+ responses from 177 countries
- Data type: Self-reported survey responses

#### Select three features that are most relevant to the questions
- Language - aim to understand the language trends
- Years of Coding Experience - aim to learn which language has been used by most develoopers
- Salary - aim to learn which language is paid highest

## Section 3: Data Preparation
- Expand the multiple languages in each row to multiple rows, so all the languages are maintained in the analysis
- Save the cleaned dataset

## Section 4: Data Modeling (not applicable)

## Section 5: Data Evaluation - Visualizations
### Question 1: Which programming languages are used most frequently?
![Language Popularity]({{site.baseurl}}/assets/images/top_languages.png)
#### Observations
- To answer this question, a bar chart is created to rank the user numbers of each language.
- Four top languages (JS, HTML/CSS, SQL, Python) account for almost half of the developers. This trend suggests that database relevant applications are dominating the market.

### Question 2: Which programming language has been used for longest experience?
![Language Experience]({{site.baseurl}}/assets/images/language_vs_experience.png)
#### Observations
- To answer this question, a bar chart is created to rank average years of coding experience across different languages.
- The Delphi and Perl have longer experience than others because they have longer history.
- All developers have almost 20 years coding experience no matter what language they are using.

### Question 3: Which programming languages are paid highest?
![Salary vs Language]({{site.baseurl}}/assets/images/language_vs_salary.png)

![Salary comparison]({{site.baseurl}}/assets/images/language_salary_distribution_ordered.png)
#### Observations
- To answer this question, a bar chart is created to rank median salaries of different languages.
- For futher observation, a boxplot graph is created to illustrate salary distributions for different languages.
- Language Ruby showed highest median salary, followed by Erlang, Elixir, Perl and Scala. It is interesting that they are not popular languages. It is possibly due to high demand in specific industry, such as finance, telecommunication.

---

### Conclusions

- Four top languages (JS, HTML/CSS, SQL, Python) account for almost half of the developers. This trend suggests that database relevant applications are dominating the market.
- The Delphi and Perl have longer experience than others because they have longer history.
- All developers have almost 20 years coding experience no matter what language they are using.
- Language Ruby showed highest median salary, followed by Erlang, Elixir, Perl and Scala. It is interesting that they are not popular languages. It is possibly due to high demand in specific industry, such as finance, telecommunication.

### Limitations
- Self-reported data could be biased
- Normalized counts by respondent
- Excluded missing values
