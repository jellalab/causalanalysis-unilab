# Causal Analysis of Marijuana and Cigarette Use on Health

## Project Overview

This project investigates the **causal effect of marijuana consumption and cigarette smoking on individual health outcomes** using observational data from the **NHANES (National Health and Nutrition Examination Survey)** dataset.

The goal is to estimate whether using marijuana or smoking cigarettes has a measurable impact on **self-reported health**, compared to individuals who do not use these substances.

Because the treatment (substance use) is **not randomly assigned**, the analysis applies several **causal inference methods** to estimate treatment effects while accounting for potential confounding variables.

---

## Research Questions

1. What is the causal effect of **marijuana consumption** on an individual's health compared to not using marijuana?
2. What is the causal effect of **smoking cigarettes** on an individual's health compared to not smoking?

---

## Dataset

The analysis uses data from the **NHANES survey**, which collects health and nutrition information from a nationally representative sample of the U.S. population.

Key dataset characteristics:

* ~10,000 observations
* 76 variables
* Demographic, behavioral, and health-related variables

Examples of variables used in the analysis:

* Age
* Gender
* Education
* Depression indicators
* Physical activity
* Alcohol consumption
* Marijuana use
* Cigarette smoking
* Self-reported health score

Health is measured on a **1–5 scale**, where:

* 1 = Poor
* 5 = Excellent

---

## Methods

Since treatment assignment is **observational rather than randomized**, several causal inference approaches were used:

### Directed Acyclic Graph (DAG)

A DAG was used to visualize relationships between:

* Treatment variables (marijuana use or smoking)
* Outcome variable (health)
* Confounders such as alcohol use, depression, and physical activity

### Linear Regression

Three regression models were estimated:

* **Simple OLS regression** (without control variables)
* **OLS with control variables**
* **OLS with interaction effects**

These models examine how substance use correlates with health outcomes while adjusting for observable covariates.

### Matching and Treatment Effect Estimation

To estimate causal effects more directly, the analysis applied:

* **Average Treatment Effect (ATE)**
* **Average Treatment Effect on the Treated (ATET)**
* **Exact matching on key covariates**

Matching variables included:

* Age
* Education
* Depression
* Physical activity
* Gender

### Augmented Inverse Probability Weighting (AIPW)

AIPW was used as a **doubly robust estimator** to improve causal effect estimation by combining outcome modeling and treatment probability weighting.

---

## Results

### Marijuana Consumption

Across multiple methods, marijuana use is associated with a **small negative effect on self-reported health**.

Key findings:

* ATE ≈ **-0.127**
* ATET ≈ **-0.082**
* AIPW estimate ≈ **-0.082**

This suggests that individuals who use marijuana report slightly lower health scores on average compared to non-users, although the magnitude of the effect is relatively small.

### Cigarette Smoking

Smoking shows a **stronger negative association with health** than marijuana use.

Key findings:

* ATE ≈ **-0.177**
* ATET ≈ **-0.175**

This indicates that cigarette smoking has a **larger negative impact on self-reported health outcomes**.

---

## Limitations

Several limitations should be considered:

* The dataset is **observational**, meaning treatment is not randomly assigned.
* **Unobserved confounders** (e.g., stress, genetics, access to healthcare) may still influence results.
* Health outcomes are **self-reported**, which may introduce reporting bias.
* Some variables contain **missing values**, reducing the sample size for certain analyses.

---

## Conclusion

The analysis suggests that both **marijuana use and cigarette smoking are associated with lower self-reported health scores**.

However:

* The estimated effect of **marijuana consumption is modest**.
* The effect of **cigarette smoking is larger and more consistent across methods**.

While multiple causal inference techniques support these findings, results should be interpreted cautiously due to the limitations of observational data.

---

## Tools and Techniques

* Python / statistical analysis
* Linear regression
* Exact matching
* ATE and ATET estimation
* Augmented Inverse Probability Weighting (AIPW)
* Causal inference frameworks

---

## Author

University project for **DS839 – Causal Analysis in Business Data Science**.
