---
layout: post
title: "Programming Language Trends from the 2025 Stack Overflow Survey"
tags: [stackoverflow, python, data-analysis]
---

## Dataset

This analysis uses the data from 2025 Stack Overflow Developer Survey.

## Key Question

Which programming languages are used most frequently?
Which programming languages are paid highest?

## Results

![Language Popularity]({{site.baseurl}}/assets/images/top_languages.png)
![Language Experience]({{site.baseurl}}/assets/images/language_vs_experience.png)
![Salary vs Language]({{site.baseurl}}/assets/images/language_vs_salary.png)
![Salary comparison]({{site.baseurl}}/assets/images/language_salary_distribution_ordered.png)

### Observations

- Four top languages (JS, HTML/CSS, SQL, Python) account for almost half of the developers. This trend suggests that database relevant applications are dominating the market.
- All languages showed more than 15 years of experience. This result could be biased as only experienced developer taken this survey.
- Language Ruby showed highest median salary, followed by Erlang, Elixir, Perl and Scala. It is interesting that they are not popular languages. It is possibly due to high demand in specific industry, such as finance, telecommunication.

### Limitations
- Self-reported data could be biased
- Normalized counts by respondent
- Excluded missing values
