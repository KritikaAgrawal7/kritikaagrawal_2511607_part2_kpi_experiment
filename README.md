# AI Business Analytics Capstone – Part 2

## Project Overview

This project evaluates the effectiveness of a new onboarding and activation campaign using an **A/B experiment**. The objective is to determine whether the redesigned onboarding experience should be rolled out to all users by analysing business metrics, performing statistical hypothesis testing, and evaluating guardrail metrics to ensure that improvements in conversion do not negatively impact customer experience or business performance.

The analysis follows a structured business analytics approach consisting of:

- Understanding the business problem
- Defining the North Star Metric
- Designing a KPI Tree
- Validating the experiment dataset
- Comparing experiment performance
- Performing statistical hypothesis testing
- Evaluating guardrail metrics
- Making a business recommendation

---

# Repository Structure

```text
part2_kpi_experiment/
│
├── data/
│   └── campaign_experiment_data.xlsx
│
├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md
│
├── outputs/
│   ├── experiment_summary.xlsx
│   ├── kpi_tree.png
│   └── recommendation_memo.md
│
├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png
│
└── README.md
```

---

# Task 1: Business Problem Understanding

## Business Problem

The company launched a redesigned onboarding and activation campaign and conducted an A/B experiment to evaluate whether the new experience performs better than the existing onboarding process.

Users were randomly assigned to one of two groups:

- **Control Group:** Existing onboarding experience
- **Treatment Group:** New onboarding experience

The objective of this experiment is to determine whether the Treatment experience should be rolled out to all users.

---

## Business Decision

The business must decide whether the new onboarding experience should:

- Be launched to all users,
- Be refined and tested further, or
- Be rejected based on experiment performance.

---

## Stakeholders

The experiment findings support decision-making for multiple business teams.

- Product Team
- Engineering Team
- Marketing Team
- Business Leadership
- End Users

---

## Expected Business Outcome

The redesigned onboarding experience is expected to:

- Increase Paid Conversion Rate
- Improve onboarding completion
- Increase user engagement
- Generate higher business value
- Maintain a positive customer experience

---

## Business Risks

While improving conversion is important, the following risks must also be monitored:

- Higher Refund Rate
- Increased Support Ticket Rate
- Lower User Engagement
- Longer Time to Convert
- Poor performance for specific customer segments

These metrics serve as **guardrail metrics** to ensure business growth is achieved without negatively affecting customer experience.

---

## Evidence Required

The rollout decision should be supported by:

- KPI comparison between Control and Treatment groups
- Statistical hypothesis testing
- Guardrail metric evaluation
- Segment-level analysis
- Business interpretation of results

---

# Task 2: Define the North Star Metric

## Selected North Star Metric

**Paid Conversion Rate**

> Paid Conversion Rate = Converted Users ÷ Total Users

---

## Why this is the North Star Metric

The primary objective of the onboarding campaign is to convert more users into paying customers.

Paid Conversion Rate directly measures whether the redesigned onboarding experience successfully achieves this objective, making it the most meaningful indicator of experiment success.

---

## Supporting Metrics

Several additional metrics explain **why** Paid Conversion Rate changes throughout the customer journey.

### User Acquisition

- Landing Page Visit Rate
- Trial Start Rate

### User Activation

- Onboarding Completion Rate
- Average Engagement Score

### Conversion Quality

- Average Revenue per User
- Average Revenue per Converted User

### Guardrail Metrics

- Refund Rate
- Support Ticket Rate
- Average Days to Convert

These metrics provide supporting evidence but do not replace Paid Conversion Rate as the primary measure of experiment success.

---

## Connection to Business Growth

An increase in Paid Conversion Rate contributes directly to business growth by:

- Increasing the paying customer base
- Improving recurring revenue
- Supporting long-term customer value
- Improving return on acquisition efforts

---

## Risks of Optimising Only the North Star Metric

Optimising Paid Conversion Rate without monitoring supporting metrics could result in:

- Higher refund requests
- Increased customer support demand
- Lower customer value
- Poor customer experience

For this reason, the North Star Metric should always be evaluated alongside guardrail metrics.

---

# Task 3: KPI Tree

## KPI Tree Overview

A KPI Tree was created to illustrate how the North Star Metric is influenced by different stages of the customer journey.

Rather than viewing Paid Conversion Rate as an isolated outcome, the KPI Tree breaks it down into measurable business drivers and supporting metrics.

---

## North Star Metric

**Paid Conversion Rate**

Business Question:

> Did users become paying customers?

---

## User Acquisition

Business Question:

> Did users successfully enter the onboarding journey?

Supporting Metrics:

- Landing Page Visit Rate
- Trial Start Rate

---

## User Activation

Business Question:

> Did users complete onboarding and begin engaging with the product?

Supporting Metrics:

- Onboarding Completion Rate
- Average Engagement Score

---

## Conversion Quality

Business Question:

> Did converted users generate business value?

Supporting Metrics:

- Average Revenue per User
- Average Revenue per Converted User

---

## Guardrail Metrics

The following guardrail metrics were monitored to ensure that improvements in Paid Conversion Rate did not negatively impact customer experience or business performance.

- Refund Rate
- Support Ticket Rate
- Average Days to Convert

---

## Business Interpretation

The KPI Tree demonstrates that Paid Conversion Rate is influenced by improvements across the entire customer journey rather than by a single activity.

Monitoring User Acquisition, User Activation, Conversion Quality and Guardrail Metrics together enables the business to understand where users progress successfully, where friction exists, and whether the Treatment experience should be rolled out to all users.

---

## Deliverables

- **KPI Tree:** `outputs/kpi_tree.png`
- **Preview Screenshot:** `screenshots/kpi_tree_preview.png`

# Task 4: Data Preparation and Validation

## Data Validation Objective

Before performing the experiment analysis, the dataset was validated to ensure that the results would be reliable, unbiased, and suitable for A/B testing.

The validation focused on identifying issues that could affect KPI calculations, statistical testing, or business conclusions.

---

## Data Validation Approach

The following validation checks were performed:

### 1. Missing Values

Missing values were identified across all columns.

- Blank values in **days_to_convert** were expected because only users who converted to a paid plan have a conversion date.
- Missing values in **device_type**, **traffic_source**, and **engagement_score** were documented and retained because there was no reliable basis for imputation.

**Status:** Completed

---

### 2. Experiment Group Balance

The number of users in each experiment group was verified to ensure a fair comparison.

| Group | Users |
|:------|------:|
| Control | 690 |
| Treatment | 710 |

The difference of only **20 users (1.4%)** indicates that the experiment groups are well balanced.

**Status:** Completed

---

### 3. Duplicate User IDs

Duplicate User IDs were identified using the `user_id` field.

- **8 duplicate records** were found.
- All duplicate rows were exact copies.
- Duplicate records were removed from the cleaned dataset while preserving the original dataset in the **Raw_Data** worksheet.

**Status:** Completed

---

### 4. Binary Value Validation

The following binary variables were validated:

- visited_landing_page
- started_trial
- completed_onboarding
- converted_to_paid
- refund_requested

All variables contained only valid values (**0** and **1**).

No invalid records were identified.

**Status:** Completed

---

### 5. Revenue Outlier Assessment

Revenue (30 Days) was evaluated using the **Interquartile Range (IQR)** method.

Because **1,328 of the 1,400 users recorded zero revenue**, both **Q1** and **Q3** were equal to zero, making the standard IQR method unsuitable for identifying meaningful outliers.

Non-zero revenue values were retained because they represent genuine customer transactions rather than data errors.

**Status:** Completed

---

### 6. Segment Distribution

The distribution of the following customer attributes was compared across the Control and Treatment groups:

- Region
- Device Type
- Traffic Source
- Plan Type

The experiment groups were found to be reasonably balanced across all major customer segments.

A slight imbalance was observed for missing Traffic Source values (6 vs. 18 users), affecting only **24 users (1.7% of the dataset)**. This was not considered material enough to impact the experiment.

**Status:** Completed

---

## Validation Summary

| Validation Check | Result |
|:-----------------|:------|
| Missing Values | Documented and retained where appropriate |
| Group Balance | Balanced (690 vs. 710 users) |
| Duplicate Records | 8 duplicate records removed |
| Binary Value Validation | All values valid |
| Revenue Outliers | No records removed |
| Segment Distribution | Groups reasonably balanced |

Based on these validation checks, the dataset was considered suitable for KPI calculation, statistical testing, and business decision-making.

---

## Experiment Analysis Workbook

The experiment analysis was performed using:

```text
analysis/experiment_analysis.xlsx
```

The workbook contains the following worksheets:

| Worksheet | Description |
|:----------|:------------|
| **Raw_Data** | Original dataset provided for the assignment without modification. |
| **Calculations** | Cleaned dataset used for KPI calculations after removing duplicate records. |
| **Data_Validation** | Summary of validation checks, observations, actions taken and validation status. |
| **Pivot_Tables** | Supporting Pivot Tables used for validation, KPI calculations and segment analysis. |
| **Hypothesis_Test** | Statistical hypothesis testing, calculations and business conclusion. |

This workbook structure ensures that the analysis is transparent, reproducible, and based on a validated dataset.

---

# Task 5: Experiment Summary

## Experiment Objective

The objective of the experiment was to determine whether the redesigned onboarding experience improved the **Paid Conversion Rate** compared to the existing onboarding experience while maintaining healthy customer experience and business performance metrics.

---

## Overall Experiment Summary

| Metric | Control | Treatment |
|:-------|:-------:|:---------:|
| User Count | 690 | 710 |
| Landing Page Visit Rate | 63.62% | 72.39% |
| Trial Start Rate | 25.07% | 29.01% |
| Onboarding Completion Rate | 15.65% | 21.13% |
| **Paid Conversion Rate (North Star Metric)** | **3.19%** | **7.04%** |
| Average Revenue per User | ₹51.97 | ₹54.25 |
| Average Revenue per Converted User | ₹1,630.10 | ₹770.41 |
| Refund Rate | 0.00% | 0.42% |
| Support Ticket Rate | 14.64% | 24.93% |
| Average Engagement Score | 57.03 | 62.94 |
| Average Days to Convert | 8.86 | 6.40 |

---

## Key Findings

The Treatment group demonstrated improvements across most **User Acquisition** and **User Activation** metrics.

Positive outcomes included:

- Higher Landing Page Visit Rate
- Higher Trial Start Rate
- Higher Onboarding Completion Rate
- Higher Paid Conversion Rate
- Higher Average Revenue per User
- Higher Average Engagement Score
- Faster Average Days to Convert

However, **Conversion Quality** showed mixed results.

Although more users converted to paid subscriptions, **Average Revenue per Converted User** decreased from **₹1,630.10** to **₹770.41**, indicating that converted users generated lower average revenue during the 30-day observation period.

Support Ticket Rate also increased from **14.64%** to **24.93%**, highlighting an important guardrail metric that requires further investigation before a full rollout.

---

## Deliverables

The complete experiment summary is available in:

```text
outputs/experiment_summary.xlsx
```

A screenshot of the summary metrics is included in:

```text
screenshots/summary_metrics.png
```

# Task 6: Hypothesis Test Design

## Objective

The objective of the hypothesis test was to determine whether the redesigned onboarding experience resulted in a statistically significant improvement in the **Paid Conversion Rate** compared to the existing onboarding experience.

---

## Metric Being Tested

**Primary Metric:** Paid Conversion Rate (North Star Metric)

Paid Conversion Rate was selected because it directly measures the percentage of users who successfully converted into paying customers. Since increasing paid subscriptions was the primary business objective of the experiment, this metric provides the most meaningful measure of experiment success.

---

## Statistical Test Selected

The experiment was analysed using a **One-Tailed Two-Proportion Z-Test**.

This test was selected because:

- The primary metric is binary (Converted / Not Converted).
- The Control and Treatment groups are independent.
- Both experiment groups have sufficiently large sample sizes.
- The objective is to determine whether the Treatment group achieved a higher conversion rate than the Control group.

---

## Hypotheses

### Null Hypothesis (H₀)

The redesigned onboarding campaign does **not** improve the Paid Conversion Rate.

$begin:math:display$
H\_0 \: p\_\{Treatment\} \\leq p\_\{Control\}
$end:math:display$

### Alternative Hypothesis (H₁)

The redesigned onboarding campaign **improves** the Paid Conversion Rate.

$begin:math:display$
H\_1 \: p\_\{Treatment\} \> p\_\{Control\}
$end:math:display$

---

## Significance Level

The hypothesis test was performed using a **5% significance level (α = 0.05)**.

The Null Hypothesis would be rejected if the calculated p-value was less than 0.05.

---

# Task 7: Hypothesis Test Results

## Test Summary

The statistical analysis compared the Paid Conversion Rates of the Control and Treatment groups.

### Experiment Results

| Metric | Control | Treatment |
|:-------|:-------:|:---------:|
| Users | 690 | 710 |
| Converted Users | 22 | 50 |
| Paid Conversion Rate | **3.19%** | **7.04%** |

---

### Statistical Results

| Statistic | Value |
|:----------|------:|
| Significance Level (α) | 0.05 |
| Z Statistic | 3.264 |
| P-value | 0.00055 |

---

## Decision

Since the calculated **p-value (0.00055)** is less than the significance level (**0.05**), the **Null Hypothesis was rejected**.

---

## Business Interpretation

The statistical analysis provides strong evidence that the redesigned onboarding experience significantly improved the Paid Conversion Rate.

The observed increase from **3.19%** to **7.04%** is unlikely to have occurred due to random chance alone.

The detailed hypothesis test calculations are available in:

```text
analysis/hypothesis_test_notes.md
```

A screenshot of the hypothesis test output is included in:

```text
screenshots/hypothesis_test_output.png
```

---

# Task 8: Guardrail Metric Evaluation

Improving the North Star Metric alone is not sufficient to recommend a rollout.

Additional business metrics were evaluated to ensure that the redesigned onboarding experience did not negatively affect customer experience or business performance.

## Guardrail Metric Summary

| Guardrail Metric | Control | Treatment | Assessment |
|:-----------------|:-------:|:---------:|:-----------|
| Refund Rate | 0.00% | 0.42% | Low Risk |
| Support Ticket Rate | 14.64% | 24.93% | High Risk |
| Average Days to Convert | 8.86 days | 6.40 days | Positive Outcome |
| Average Revenue per Converted User | ₹1,630.10 | ₹770.41 | Medium Risk |

## Business Interpretation

The analysis identified two important trade-offs:

- **Support Ticket Rate** increased from **14.64%** to **24.93%**, indicating that more users required customer support after experiencing the redesigned onboarding journey.
- **Average Revenue per Converted User** decreased from **₹1,630.10** to **₹770.41**, indicating that converted users generated lower average revenue during the first 30 days.

At the same time, the experiment produced positive outcomes:

- Users converted more quickly.
- Engagement Score increased.
- Average Revenue per User increased.
- Paid Conversion Rate more than doubled.

These findings indicate that although the experiment successfully improved conversion, additional optimisation is recommended before a full rollout.

---

# Task 9: Business Recommendation

## Final Recommendation

### **Continue Testing Before Full Rollout**

The experiment successfully achieved its primary objective by significantly improving the **Paid Conversion Rate**.

However, the increase in Support Ticket Rate and the decline in Average Revenue per Converted User indicate potential trade-offs that should be addressed before deploying the redesigned onboarding experience to all users.

A phased approach is recommended to preserve the observed improvement in Paid Conversion Rate while strengthening **Conversion Quality** and reducing customer support requirements.

---

## Assumptions

The analysis assumes that:

- Users were randomly assigned to the Control and Treatment groups.
- User observations are independent.
- Revenue values represent the first 30 days after conversion.
- The experiment duration is representative of normal customer behaviour.

---

## Limitations

- The analysis covers only a 30-day observation period.
- Long-term customer retention and customer lifetime value were not evaluated.
- Qualitative customer feedback was not included.
- The decline in Average Revenue per Converted User requires further investigation.

---

## Project Deliverables

| Deliverable | Location |
|:------------|:---------|
| Original Dataset | `data/campaign_experiment_data.xlsx` |
| Experiment Analysis Workbook | `analysis/experiment_analysis.xlsx` |
| Hypothesis Test Notes | `analysis/hypothesis_test_notes.md` |
| KPI Tree | `outputs/kpi_tree.png` |
| Experiment Summary | `outputs/experiment_summary.xlsx` |
| Recommendation Memo | `outputs/recommendation_memo.md` |

---

## Screenshots Included

| Screenshot | Description |
|:-----------|:------------|
| `summary_metrics.png` and `summary_metrics2.png`| Overall experiment summary |
| `hypothesis_test_output.png` | Hypothesis test calculations and results |
| `kpi_tree_preview.png` | KPI Tree visualization |

---

## Conclusion

The redesigned onboarding experience significantly improved the **Paid Conversion Rate**, which was selected as the North Star Metric for this experiment.

Statistical testing confirmed that the observed improvement was significant and unlikely to have occurred due to random chance. However, the increase in Support Ticket Rate and the decline in Average Revenue per Converted User indicate that the Treatment introduced trade-offs that require further investigation.

Based on the available evidence, the recommended course of action is to **continue testing before a full rollout**, refining the onboarding experience to improve **Conversion Quality** while preserving the gains achieved in Paid Conversion Rate.
