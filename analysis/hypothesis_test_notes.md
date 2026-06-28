# Part 2 : KPI Framework, Business Experiment Analysis & Decision Recommendation
---

# Task 6: Hypothesis Test Notes

## Objective

The objective of this hypothesis test is to determine whether the new onboarding campaign significantly improves the **Paid Conversion Rate** compared to the existing onboarding experience.

## North Star Metric

**Paid Conversion Rate**

This is the primary success metric used to evaluate the experiment.

## Statistical Test

A **Chi-Square Test of Independence** was used because:

- The experiment compares two independent groups (Control and Treatment).
- The outcome (Paid Conversion) is a binary variable.
- The objective is to determine whether the Treatment group performs better than the Control group.

## Hypotheses

### Null Hypothesis (H₀)

The new onboarding campaign does not improve the Paid Conversion Rate.

### Alternative Hypothesis (H₁)

The new onboarding campaign improves the Paid Conversion Rate.

## Test Type

A **one-tailed hypothesis test** was used because the business objective is to determine whether the Treatment group performs better than the Control group.

## Significance Level

The significance level used for the test is:

**α = 0.05**

## Methodology

The hypothesis test was performed using the cleaned dataset.

The following calculations were completed:

- Observed frequencies
- Expected frequencies
- Chi-Square statistic
- Degrees of Freedom
- P-value
- Decision based on the significance level

All calculations were performed using spreadsheet formulas.

## Decision Rule

- If **p-value < 0.05**, reject the Null Hypothesis.
- If **p-value ≥ 0.05**, fail to reject the Null Hypothesis.

## Result

The calculated p-value was less than 0.05.

Therefore, the **Null Hypothesis was rejected**.

## Business Interpretation

The statistical analysis indicates that the new onboarding campaign significantly improves the Paid Conversion Rate.

Based on this result, the Treatment group performed better than the Control group and provides statistical evidence in support of rolling out the new onboarding experience.


---


# Hypothesis Test Notes

## Task 7: Perform Hypothesis / A/B Test Analysis

The objective of this analysis was to determine whether the new onboarding campaign significantly improves the **Paid Conversion Rate** compared to the existing onboarding experience.

### Summary of Test Inputs

**Primary Metric**

- Paid Conversion Rate

**Groups Compared**

- Control Group
- Treatment Group

**Statistical Test**

- Chi-Square Test of Independence

**Test Type**

- One-tailed

**Significance Level**

- α = 0.05

### Test Output

The hypothesis test was performed using the cleaned dataset.

The following calculations were completed:

- Observed frequencies
- Expected frequencies
- Chi-Square statistic
- Degrees of Freedom
- P-value

All calculations were performed using spreadsheet formulas in the Hypothesis Test worksheet.

### P-value

The calculated p-value was less than **0.05**.

### Decision Rule

- If the p-value is less than 0.05, reject the Null Hypothesis.
- If the p-value is greater than or equal to 0.05, fail to reject the Null Hypothesis.

### Decision

Since the p-value is less than 0.05, the **Null Hypothesis was rejected**.

### Business Interpretation

The statistical analysis indicates that the Treatment group achieved a significantly higher **Paid Conversion Rate** than the Control group.

The results provide statistical evidence that the new onboarding campaign improves user conversion and supports recommending the Treatment experience for a broader rollout.


---


