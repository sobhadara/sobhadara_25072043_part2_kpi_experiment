# Part 2 : KPI Framework, Business Experiment Analysis & Decision Recommendation

---


## Task 1: Understand the Business Problem

### Business Context

A subscription-based digital product company introduced a new onboarding and activation campaign to help users understand the product's value more quickly and increase the likelihood of converting into paying subscribers.

To evaluate the campaign, the company conducted an A/B experiment by randomly assigning users to one of two groups:

- **Control Group:** Existing onboarding experience
- **Treatment Group:** New onboarding and activation campaign

The purpose of the experiment is to determine whether the new onboarding experience should be rolled out to all users.

### Business Problem Statement

#### Decision to Be Made

Determine whether the new onboarding and activation campaign should be rolled out to all users based on its impact on business performance and customer experience.

#### Who the Decision Impacts

The decision affects multiple stakeholders, including:

- New users experiencing the onboarding process
- Product and Growth teams responsible for user activation
- Marketing teams focused on customer acquisition efficiency
- Business leadership responsible for subscription growth and revenue

#### Primary Metric to Improve

The primary success metric is **Paid Conversion Rate**, which measures the percentage of users who convert into paying subscribers.

Supporting metrics include:

- Trial Start Rate
- Onboarding Completion Rate
- User Engagement Score

These metrics help explain user behaviour throughout the onboarding journey and provide additional context for changes in Paid Conversion Rate.

#### Risks That Must Be Monitored

While increasing Paid Conversion Rate is the primary objective, the company must ensure that the new onboarding experience does not negatively affect the overall customer experience.

The following guardrail metrics should be monitored:

- Customer Support Ticket Rate
- Refund Request Rate
- User Satisfaction
- Long-term Customer Retention

#### Evidence Required Before Making a Recommendation

Before recommending a full rollout, the analysis should confirm:

1. The Treatment group outperforms the Control group on Paid Conversion Rate.
2. The improvement is statistically significant.
3. User activation and engagement metrics improve.
4. Guardrail metrics remain within acceptable limits.
5. The overall business benefits outweigh any identified risks.

#### Business Objective

Determine whether the new onboarding campaign delivers a meaningful improvement in Paid Conversion Rate and user engagement while maintaining a positive customer experience and supporting sustainable business growth.

---

## Dataset Description

The experiment dataset contains user-level records collected during an A/B test of the new onboarding and activation campaign.

### Dataset Overview

After data cleaning, the dataset contains **1,400 unique users**.

Users were randomly assigned to one of two experiment groups:

- **Control Group:** Existing onboarding experience
- **Treatment Group:** New onboarding and activation campaign

### Key Variables

| Variable | Description |
|----------|-------------|
| user_id | Unique user identifier |
| signup_date | User registration date |
| experiment_group | Control or Treatment assignment |
| region | User geographic region |
| device_type | Device used by the user |
| traffic_source | User acquisition channel |
| plan_type | Subscription plan selected |
| visited_landing_page | Landing page visit indicator |
| started_trial | Trial start indicator |
| completed_onboarding | Onboarding completion indicator |
| converted_to_paid | Paid conversion indicator |
| revenue_30d | Revenue generated within 30 days |
| support_tickets_30d | Number of support tickets within 30 days |
| refund_requested | Refund request indicator |
| days_to_convert | Days taken to convert to a paid subscription |
| engagement_score | User engagement score |

The dataset was cleaned and validated before analysis and forms the foundation for KPI evaluation, experiment analysis, hypothesis testing, and the final business recommendation.


---


## Task 2: Define the North Star Metric

### North Star Metric: Paid Conversion Rate

**Definition:**

Paid Conversion Rate measures the percentage of users who convert into paying subscribers after experiencing the onboarding process. It is calculated using the `converted_to_paid` outcome from the experiment dataset.

**Formula:**

Paid Conversion Rate = (Number of Users Converted to Paid / Total Users) × 100

### Why This Is the Main Success Metric

Paid Conversion Rate is the North Star Metric because the primary objective of the new onboarding and activation campaign is to increase the number of users who become paying subscribers.

Unlike activity-based metrics, Paid Conversion Rate directly measures the campaign's ability to generate revenue. Since the company operates on a subscription-based business model, improvements in Paid Conversion Rate have a direct impact on business performance.

### Why Other Metrics Are Supporting Metrics

Other metrics provide valuable insights into user behaviour but do not directly measure business success.

#### Trial Start Rate

Measures whether users begin exploring the product. While an important indicator of user interest, starting a trial does not guarantee a paid subscription.

#### Onboarding Completion Rate

Measures whether users complete the onboarding process. A higher completion rate indicates a smoother onboarding experience, but users can complete onboarding without becoming paying subscribers.

#### Engagement Score

Measures how actively users interact with the product after onboarding. Higher engagement often increases the likelihood of conversion, but engagement alone does not generate revenue.

These metrics are considered leading indicators that help explain changes in the North Star Metric rather than replace it.

### How This Metric Connects to Business Growth

Paid Conversion Rate is directly linked to business growth because more paying subscribers generate higher subscription revenue without necessarily increasing customer acquisition costs.

Improving Paid Conversion Rate can lead to:

- Increased subscription revenue
- Improved return on marketing investment
- Better customer acquisition efficiency
- Higher customer lifetime value
- Sustainable business growth

### Risks of Optimizing This Metric Blindly

Focusing only on Paid Conversion Rate can create unintended consequences if user experience is ignored.

Potential risks include:

- Aggressive onboarding that pressures users into subscribing
- Increased customer support requests due to onboarding complexity
- Higher refund rates from low-quality conversions
- Reduced customer satisfaction
- Lower long-term customer retention despite higher short-term conversions

For this reason, Paid Conversion Rate should always be evaluated together with guardrail metrics such as Support Ticket Rate, Refund Request Rate, Engagement Score, and Revenue Quality.

### Conclusion

Paid Conversion Rate is the most appropriate North Star Metric because it directly measures the experiment's primary objective of increasing paying subscribers. Supporting metrics explain user behaviour throughout the onboarding journey, while guardrail metrics ensure that improvements in conversion are achieved without negatively affecting customer experience or long-term business performance.

---


## Task 3: Create KPI Tree

The KPI Tree was created to show how the **North Star Metric**, **Paid Conversion Rate**, is influenced by key business drivers and supporting sub-drivers. It also includes guardrail metrics that should be monitored to ensure improvements in conversion are achieved without negatively affecting customer experience.

### North Star Metric

- Paid Conversion Rate

### Primary KPI Driver 1: User Activation

Measures how effectively users progress through the onboarding journey.

Sub-drivers:

- Trial Start Rate
- Onboarding Completion Rate

### Primary KPI Driver 2: User Engagement

Measures how actively users interact with the product and how efficiently they move toward becoming paying subscribers.

Sub-drivers:

- Average Engagement Score
- Average Days to Convert

### Primary KPI Driver 3: Subscription Intent

Measures users' intent to become paying customers and the revenue generated from successful conversions.

Sub-drivers:

- Paid Subscription Rate
- Revenue per User

### Guardrail Metrics

The following guardrail metrics are monitored to ensure that improvements in Paid Conversion Rate do not negatively impact customer experience:

- Support Ticket Rate
- Refund Request Rate
- Average Engagement Score

### KPI Tree Logic

The KPI Tree shows that improvements in user activation increase user engagement, which strengthens subscription intent and ultimately improves Paid Conversion Rate. Guardrail metrics are monitored to ensure that business growth is achieved without compromising customer experience.

### Deliverables

The completed KPI Tree was saved as:

```text
outputs/kpi_tree.png
```

A preview screenshot of the KPI Tree is included as:

```text
screenshots/kpi_tree_preview.png
```


---


## Task 4: Clean and Prepare Experiment Data

Before conducting the experiment analysis, the dataset was reviewed to identify and address potential data quality issues that could affect the reliability of the results.

### Data Quality Checks Performed

#### 1. Missing Values

The dataset was examined for missing values across all columns.

**Result:**

- `device_type` – 18 missing values
- `traffic_source` – 24 missing values
- `engagement_score` – 14 missing values
- `days_to_convert` – 1,328 missing values

**Action Taken:**

- Missing values in `days_to_convert` were retained because only users who converted to paid subscriptions have a recorded conversion time.
- Missing values in `device_type`, `traffic_source`, and `engagement_score` were documented and retained because they represented only a small proportion of the dataset.

---

#### 2. Group Counts

The number of users in the Control and Treatment groups was verified after removing duplicate records.

**Result:**

- The experiment groups remained reasonably balanced for comparison.

**Action Taken:**

- No changes were required.

---

#### 3. Duplicate User IDs

The `user_id` column was checked for duplicate records.

**Result:**

- 8 duplicate user records were identified.

**Action Taken:**

- Duplicate rows were removed while retaining the first occurrence of each user.
- The cleaned dataset contains **1,400 unique users**.

---

#### 4. Invalid Binary Values

The binary fields were checked to ensure they contained only valid values (0 or 1).

Fields checked:

- `visited_landing_page`
- `started_trial`
- `completed_onboarding`
- `converted_to_paid`
- `refund_requested`

**Result:**

- No invalid binary values were found.

**Action Taken:**

- No corrections were required.

---

#### 5. Revenue Outliers

The `revenue_30d` column was reviewed for unusually high values.

**Result:**

- High-value observations were identified but appeared to be valid business transactions.

**Action Taken:**

- All revenue values were retained.

---

#### 6. Segment Distribution Across Groups

The distribution of users across the Control and Treatment groups was reviewed by:

- Region
- Device Type
- Traffic Source
- Plan Type

**Result:**

- The segment distributions were reasonably balanced across both experiment groups.

**Action Taken:**

- No adjustments were required.

---

### Cleaned Dataset Summary

The cleaned dataset:

- Contains **1,400 unique users**
- Retains **all 16 original columns**
- Removes duplicate user records only
- Preserves valid missing values where appropriate
- Is ready for KPI analysis, hypothesis testing, and business decision-making

---


## Task 5: Create Experiment Summary

The cleaned experiment data was summarized to compare the performance of the **Control** and **Treatment** groups across the key business metrics required for the A/B experiment. The summary workbook was created using dynamic spreadsheet formulas to ensure all calculations update automatically if the source data changes.

### Workbook Contents

The `experiment_summary.xlsx` workbook contains the following sheets:

- Data_Source
- Overall Metrics Dashboard
- Region Analysis
- Device Type Analysis
- Traffic Source Analysis
- Metric Calculations

### Overall Metrics Dashboard

The dashboard compares the Control and Treatment groups using the following metrics:

- User Count
- Landing Page Visit Rate
- Trial Start Rate
- Onboarding Completion Rate
- Paid Conversion Rate
- Average Revenue per User
- Average Revenue per Converted User
- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Average Days to Convert

The dashboard also includes the difference between the two groups to make performance comparisons easier.

### Segment Analysis

To understand how the experiment performed across different user groups, Paid Conversion Rate was analyzed by:

- Region
- Device Type
- Traffic Source

These analyses help identify whether the treatment performs consistently across different segments.

### Formula Approach

All calculations were created using dynamic spreadsheet formulas instead of hardcoded values.

The following functions were used throughout the workbook:

- COUNTIF
- COUNTIFS
- SUMIFS
- AVERAGEIFS

This ensures that every metric is automatically updated whenever the source data changes.

### Data Validation

The following checks were performed while creating the experiment summary:

- Verified that all formulas reference the Data_Source sheet.
- Confirmed that Control and Treatment user counts match the cleaned dataset.
- Verified that each metric uses the correct source column.
- Checked percentage calculations and averages.
- Confirmed that Average Days to Convert is calculated only for users who converted to paid subscribers.

### Outcome

The completed experiment summary provides a clear comparison of the Control and Treatment groups and serves as the foundation for the hypothesis testing and final business recommendation in the next tasks.


---


## Task 6: Frame Hypotheses

A hypothesis test was performed to determine whether the new onboarding campaign significantly improved the **Paid Conversion Rate**, the North Star Metric for this experiment.

### Statistical Test

A **Chi-Square Test of Independence** was used because the experiment compares conversion outcomes between two independent groups.

The hypothesis test included:

- Null Hypothesis (H₀)
- Alternative Hypothesis (H₁)
- One-tailed test
- Significance Level (α = 0.05)
- Observed frequencies
- Expected frequencies
- Chi-Square statistic
- Degrees of Freedom
- P-value
- Decision
- Business interpretation

All calculations were performed using spreadsheet formulas based on the cleaned dataset.

### Outcome

The calculated p-value was less than 0.05, so the Null Hypothesis was rejected.

The results indicate that the new onboarding campaign significantly improves the Paid Conversion Rate compared to the existing onboarding experience.


---


## Task 7: Perform Hypothesis / A/B Test Analysis

A Chi-Square Test of Independence was performed to determine whether the new onboarding campaign significantly improved the **Paid Conversion Rate** compared to the existing onboarding experience.

The analysis included:

- Summary of test inputs
- Observed and expected frequencies
- Chi-Square statistic
- P-value
- Decision rule
- Business interpretation

All calculations were performed using spreadsheet formulas in the Hypothesis Test worksheet.

### Outcome

The calculated p-value was less than **0.05**, so the **Null Hypothesis was rejected**.

The results indicate that the new onboarding campaign significantly improves the **Paid Conversion Rate**, providing statistical support for recommending the Treatment experience.


---


## Task 8: Evaluate Guardrail Metrics

The North Star Metric alone is not sufficient to recommend a full rollout of the new onboarding campaign. Guardrail metrics were evaluated to ensure that the improvement in **Paid Conversion Rate** did not negatively impact the overall user experience or business performance.

### Guardrail Metrics Evaluated

The following guardrail metrics were analyzed:

- Refund Rate
- Support Ticket Rate
- Average Days to Convert
- Average Engagement Score

### Analysis Performed

Each guardrail metric was compared between the Control and Treatment groups to identify any potential business risks.

- Refund Rate was evaluated to determine whether the increase in conversions resulted in more refund requests.
- Support Ticket Rate was analyzed to identify whether the new onboarding experience generated additional customer support requests.
- Average Days to Convert was compared to measure how quickly users became paying subscribers.
- Average Engagement Score was evaluated to determine whether users interacted more actively with the product.

### Findings

The Treatment group achieved a higher **Paid Conversion Rate**, along with higher user engagement and a lower average number of days required for users to convert.

However, the Treatment group also showed higher Refund Rates and Support Ticket Rates. These metrics indicate that although the new onboarding campaign improves conversion, customer experience should continue to be monitored after rollout.

### Outcome

The guardrail analysis indicates that the new onboarding campaign delivers meaningful improvements in user conversion and engagement while reducing the time required for users to become paying subscribers.

Although the increase in Refund Rate and Support Ticket Rate suggests some operational risk, these metrics do not outweigh the overall business benefits. The results support recommending the Treatment experience while continuing to monitor guardrail metrics after implementation.


---


