# AI Business Analytics Capstone – Part 2
## Project Overview
This project evaluates the effectiveness of a new onboarding and activation campaign using A/B testing. The objective is to determine whether the new onboarding experience should be rolled out to all users by analyzing key business metrics, performing statistical hypothesis testing, and evaluating guardrail metrics to ensure the experiment improves customer and business outcomes.
Task 1: Business Problem Understanding
1. What decision needs to be made?
The business needs to determine whether the new onboarding and activation campaign (Treatment group) performs better than the existing onboarding experience (Control group). Based on the results of the A/B experiment, the company must decide whether to roll out the new onboarding experience to all users or continue with the existing version.
2. Who does this decision impact?
The decision impacts multiple stakeholders across the organization:
•	Users, who will experience either the existing or the new onboarding journey.
•	Product Team, responsible for improving customer acquisition and conversion.
•	Engineering Team, responsible for implementing and deploying the chosen onboarding experience.
•	Marketing Team, which relies on an effective onboarding process to maximize campaign performance.
•	Business Leadership, who use the experiment results to make strategic decisions that influence customer growth and revenue.
3. What metric should improve?
The primary objective of the experiment is to improve user conversion and early customer engagement. The company expects the new onboarding experience to increase the number of users progressing through the onboarding funnel, ultimately resulting in higher paid conversions, increased revenue, and stronger user engagement while maintaining a positive customer experience.
4. What risks should be monitored?
While improving conversion is important, the company must ensure that the new onboarding experience does not negatively affect other aspects of the business. Key risks include:
•	An increase in refund requests.
•	A higher number of customer support tickets.
•	Lower user engagement after onboarding.
•	Longer time taken for users to convert to paid customers.
•	Poor performance for specific customer segments such as different devices, regions, or traffic sources.
These metrics act as guardrail metrics to ensure that improvements in conversion do not come at the expense of customer satisfaction or business performance.
5. What evidence is required to make the decision?
The final decision should be based on objective data from the A/B experiment. This includes:
•	Comparing key performance indicators (KPIs) between the Control and Treatment groups.
•	Measuring improvements in conversion, revenue, and engagement metrics.
•	Performing statistical hypothesis testing to determine whether any observed differences are statistically significant.
•	Evaluating guardrail metrics to ensure there are no unintended negative effects.
•	Reviewing performance across different customer segments before recommending a full rollout of the new onboarding experience.
Task 2: Define the North Star Metric
Selected North Star Metric
North Star Metric: Paid Conversion Rate (Users Converted to Paid ÷ Total Users)
1. Why this metric is the main success metric
The primary objective of the experiment is to determine whether the new onboarding and activation campaign encourages more users to become paying customers. Paid Conversion Rate directly measures the success of the new onboarding experience by showing the percentage of users who complete the journey and subscribe to a paid plan. Since becoming a paying customer is the desired business outcome, this metric best represents the overall success of the experiment.
2. Why other metrics are supporting metrics instead of the North Star
The remaining metrics help explain why the Paid Conversion Rate changes, but they do not independently determine the success of the experiment.
•	Landing Page Visit Rate indicates whether users reached the landing page.
•	Trial Start Rate measures user interest in trying the product.
•	Onboarding Completion Rate shows how effectively users complete the onboarding process.
•	Revenue per User measures the financial outcome after conversion.
•	Engagement Score reflects how actively users interact with the product.
•	Days to Convert measures how quickly users become paying customers.
These metrics provide valuable insights into different stages of the customer journey, but they primarily support the interpretation of the North Star Metric rather than serving as the primary measure of success.
3. How this metric connects to business growth
Paid Conversion Rate is closely linked to business growth because an increase in the percentage of users converting to paid customers leads to a larger paying customer base, higher recurring revenue, and improved customer lifetime value. A higher conversion rate also indicates that the onboarding experience effectively guides users through the product journey, supporting sustainable business growth.
4. What could go wrong if this metric is optimized blindly
Optimizing only the Paid Conversion Rate without considering other business metrics could result in unintended consequences. For example, aggressive onboarding strategies may increase conversions but also lead to more refund requests, higher customer support tickets, lower user engagement, or poor experiences for specific customer segments. Therefore, Paid Conversion Rate should always be evaluated alongside guardrail metrics to ensure that business growth is achieved without negatively impacting customer satisfaction or long-term product performance.

Task 3: KPI Tree
KPI Tree Overview
A KPI Tree was created to illustrate how the selected North Star Metric, Paid Conversion Rate, is influenced by the different stages of the customer journey. Rather than viewing conversion as an isolated outcome, the KPI Tree breaks it down into measurable business drivers and supporting metrics that can be monitored throughout the onboarding funnel.
North Star Metric
Paid Conversion Rate (Users Converted to Paid ÷ Total Users)
This metric represents the primary success measure of the experiment because it directly reflects whether the new onboarding experience successfully converts users into paying customers.
Primary KPI Drivers
1. User Acquisition
Business Question: Did users successfully enter the onboarding journey?
This driver measures the effectiveness of attracting users into the onboarding funnel.
Supporting Metrics:
•	Landing Page Visit Rate
•	Trial Start Rate
2. User Activation
Business Question: Did users complete the onboarding process?
This driver evaluates how effectively users progress through onboarding and begin engaging with the product.
Supporting Metrics:
•	Onboarding Completion Rate
•	Average Engagement Score
3. Conversion Quality
Business Question: Did activated users become valuable customers?
This driver measures the quality and efficiency of the conversion process after successful onboarding.
Supporting Metrics:
•	Average Revenue per Converted User
•	Average Days to Convert
Guardrail Metrics
Improving the North Star Metric should not negatively impact customer experience or business performance. Therefore, the following guardrail metrics will be monitored throughout the experiment:
•	Refund Rate
•	Support Ticket Rate
•	Engagement Score
These metrics help ensure that higher conversion rates are achieved without increasing customer dissatisfaction or reducing product quality.
Business Interpretation
The KPI Tree demonstrates that Paid Conversion Rate is not driven by a single activity but by improvements across the entire customer journey. By monitoring acquisition, activation, conversion quality, and guardrail metrics together, the business can identify where users drop off, understand the impact of the new onboarding experience, and make informed decisions about whether the treatment should be launched to all users.
KPI Tree Image: outputs/kpi_tree.png, screenshots/kpi_tree_preview.png

Task 4: Data Preparation and Validation
Before performing the experiment analysis, the dataset was reviewed to ensure its quality and suitability for A/B testing. The following validation checks were completed.
Data Validation Approach
The dataset was assessed for completeness, consistency and integrity before calculating any business metrics. Validation focused on identifying issues that could bias experiment results or reduce the reliability of the analysis.
The following checks were performed:
•	Missing Values: Missing values were identified across all columns. Blank values in days_to_convert were expected because only users who converted to a paid plan have a conversion date. Missing values in device_type, traffic_source, and engagement_score were documented and retained because there was no reliable basis for imputation.
•	Experiment Group Counts: User counts for the Control and Treatment groups were verified to ensure a balanced experiment. The dataset contained 690 users in the Control group and 710 users in the Treatment group, indicating an appropriate distribution.
•	Duplicate User IDs: Duplicate records were identified using the user_id field. Eight duplicate records were removed from the analysis dataset while preserving the original dataset in the Raw_Data worksheet.
•	Binary Value Validation: All binary variables (visited_landing_page, started_trial, completed_onboarding, converted_to_paid, and refund_requested) were checked to ensure they contained only valid values (0 or 1). No invalid values were identified.
•	Revenue Outlier Assessment: Revenue outliers were evaluated using the Interquartile Range (IQR) method. Because the majority of users did not convert and therefore recorded zero revenue, both Q1 and Q3 were equal to zero. As a result, the standard IQR method was not suitable for identifying meaningful outliers. Non-zero revenue values were retained as legitimate customer transactions.
•	Segment Distribution: The distribution of Region, Device Type, Traffic Source and Plan Type was compared across the Control and Treatment groups. The experiment groups were found to be reasonably balanced across all major customer segments, indicating that the experiment was suitable for comparative analysis.
Based on these validation checks, the cleaned dataset was considered suitable for KPI calculation, hypothesis testing and business decision-making.

Validation Check	Method Used	Why is this important?	Observation	Action Taken	Status
Missing Values	COUNTBLANK 	Missing values can bias calculations and segment analysis.	Missing values found in device_type (18), traffic_source (24), engagement_score (14), and days_to_convert (1336).	Missing values were retained. days_to_convert blanks are expected for users who did not convert, while other missing values were documented and left unchanged due to the absence of a reliable basis for imputation.	Completed
Group Counts	Pivot Table / COUNTIF	Balanced group sizes ensure fair comparison between the Control and Treatment groups and reduce the risk of biased results.	After removing duplicate records, the cleaned dataset contained 690 Control users and 710 Treatment users. The difference of 20 users (1.4%) indicates that the experiment remains well balanced.	No action required. The slight difference in group sizes is minimal and is not expected to affect the validity of the experiment.	Completed
Duplicate User IDs	COUNTIF	Duplicate users may bias experiment metrics and statistical analysis by counting the same user more than once.	8 duplicate User IDs were identified. All duplicate records were exact copies of the original rows.	Exact duplicate rows were removed from the Cleaned_Data sheet while preserving the original dataset unchanged in Raw_Data. All subsequent analysis was performed using the cleaned dataset.	Completed
Invalid Binary Values	Pivot Tables	Binary variables should contain only valid values (0 or 1). Invalid values could lead to incorrect calculations and unreliable experiment results.	The binary fields (visited_landing_page, started_trial, completed_onboarding, converted_to_paid, and refund_requested) were checked. All columns contained only valid binary values (0 and 1), with no unexpected or invalid entries.	No action required. The binary variables were validated and found to be consistent with the expected data format.	Completed
Revenue Outliers	IQR Method	Extreme revenue values can influence averages and business conclusions.	The IQR method resulted in Q1 = Q3 = 0 because 1,328 of 1,400 users had zero revenue. This made the standard IQR rule unsuitable for identifying meaningful outliers.	No revenue records were removed. Non-zero revenue values were retained as they represent genuine paid customer transactions rather than data errors.	Completed
Segment Distribution	Pivot Tables	imilar segment distribution across experiment groups ensures that observed differences are more likely due to the treatment rather than differences in customer characteristics.	Region, Device Type, Traffic Source, and Plan Type distributions were compared between the Control and Treatment groups. All major segments were reasonably balanced. A slight imbalance was observed in missing Traffic Source values (6 vs. 18), but this affected only 24 users (1.7% of the dataset).	No action required. The segment distributions were considered sufficiently balanced for reliable A/B testing.	Completed

Experiment_Analysis Workbook
The experiment analysis was performed using the workbook analysis/experiment_analysis.xlsx. The workbook was organized into separate worksheets to preserve the original dataset, maintain a cleaned version for analysis and calculations, and document the data validation process. It also has a worksheet where hypothesis_test was performed.
The workbook contains the following worksheets:
•	Raw_Data: Original dataset provided for the assignment without any modifications.
•	Calculations: Cleaned Dataset used for analysis after removing duplicate records while preserving all other original values.
•	Data_Validation: Summary of all data validation checks, observations, actions taken, and validation status prior to performing the experiment analysis.
•	
•	Pivot_Tables: Supporting pivot tables used to validate missing values, experiment group balance, duplicate records, binary variables, and segment distributions.
•	Hypothesis_Test: hypothesis test was performed with calculations and business recommendations.
This structure ensures that the analysis is transparent, reproducible, and based on a validated dataset.
# Task 5: Experiment Summary

## Experiment Analysis Approach

The experiment dataset was validated before analysis by performing the following quality checks:

- Verified missing values across all columns.
- Confirmed the number of users in the Control and Treatment groups.
- Checked for duplicate User IDs.
- Validated binary columns to ensure they contained only valid values (0 or 1).
- Performed outlier analysis on the **Revenue (30 Days)** field using the IQR method.
- Compared segment distributions across Region, Device Type, Traffic Source and Plan Type to ensure the experiment groups were reasonably balanced.

Blank values in categorical fields (such as Device Type and Traffic Source) were retained because they represented missing observations rather than invalid data.

The complete validation and analysis are documented in:

```text
analysis/experiment_analysis.xlsx
```

## Overall Experiment Summary

| Metric | Control | Treatment |
|---------|:-------:|:---------:|
| User Count | 690 | 710 |
| Landing Page Visit Rate | 63.62% | 72.39% |
| Trial Start Rate | 25.07% | 29.01% |
| Onboarding Completion Rate | 15.65% | 21.13% |
| Paid Conversion Rate (North Star Metric) | 3.19% | 7.04% |
| Average Revenue per User | ₹51.97 | ₹54.25 |
| Average Revenue per Converted User | ₹1,630.10 | ₹770.41 |
| Refund Rate | 0.00% | 0.42% |
| Support Ticket Rate | 14.64% | 24.93% |
| Average Engagement Score | 57.03 | 62.94 |
| Average Days to Convert | 8.86 | 6.40 |

The Treatment group improved most acquisition, activation and conversion metrics. However, Average Revenue per Converted User declined from **₹1,630.10** to **₹770.41**, indicating a trade-off between higher conversion volume and revenue generated per converted customer during the 30-day observation period.

The complete comparison is available in:

```text
outputs/experiment_summary.xlsx
```

---

# Task 6: Hypothesis Test Summary

## Metric Being Tested

**Paid Conversion Rate (North Star Metric)**

Paid Conversion Rate was selected because it directly measures whether the redesigned onboarding campaign successfully converted more users into paying customers.

## Hypotheses

### Null Hypothesis (H₀)

The new onboarding campaign does not improve the Paid Conversion Rate compared to the existing onboarding experience.

### Alternative Hypothesis (H₁)

The new onboarding campaign improves the Paid Conversion Rate compared to the existing onboarding experience.

## Test Type

- One-Tailed Two-Proportion Z-Test
- Significance Level (α): 0.05

---

# Task 7: Hypothesis Test Results

| Statistic | Value |
|-----------|------:|
| Z Statistic | 3.264 |
| P-value | 0.00055 |

Since the p-value is less than **0.05**, the Null Hypothesis was rejected.

The statistical analysis provides strong evidence that the Treatment group achieved a significantly higher Paid Conversion Rate than the Control group.

The complete hypothesis testing calculations are available in:

```text
analysis/hypothesis_test_notes.md
```

---

# Task 8: Guardrail Metrics Considered

Although the Treatment group significantly improved the North Star Metric, additional business metrics were evaluated to identify potential risks.

| Guardrail Metric | Control | Treatment | Assessment |
|------------------|:-------:|:---------:|------------|
| Refund Rate | 0.00% | 0.42% | Low Risk |
| Support Ticket Rate | 14.64% | 24.93% | High Risk |
| Average Days to Convert | 8.86 days | 6.40 days | Positive Outcome |
| Average Revenue per Converted User | ₹1,630.10 | ₹770.41 | Medium Risk |

The increase in Support Ticket Rate and decline in Average Revenue per Converted User indicate that further optimisation is recommended before a full rollout.

---

# Task 9: Final Recommendation

## Recommendation

**Continue Testing Before Full Rollout**

The experiment successfully achieved its primary objective by significantly improving the Paid Conversion Rate from **3.19%** to **7.04%**.

However, the increase in Support Ticket Rate and the decline in Average Revenue per Converted User suggest potential trade-offs that should be addressed before launching the new onboarding experience to all users.

The recommended next step is to continue testing while maintaining the improvement in Paid Conversion Rate, strengthening Conversion Quality and reducing customer support requirements.

## Assumptions and Limitations

### Assumptions

- Users were randomly assigned to Control and Treatment groups.
- User observations are independent.
- Revenue values represent the first 30 days after conversion.

### Limitations

- The analysis covers only a 30-day observation period.
- Long-term customer retention and lifetime value were not evaluated.
- Qualitative customer feedback was not included in the analysis.
- The decrease in Average Revenue per Converted User requires further investigation.

## Screenshots Included

The following screenshots have been included as part of the submission:

| Screenshot | Description |
|------------|-------------|
| `screenshots/summary_metrics.png` | Control vs Treatment summary table |
| `screenshots/summary_metrics2.png` | Segment Analysis | 
 
| `screenshots/hypothesis_test_output.png` | Hypothesis test calculations and output |
 
| `screenshots/kpi_tree_preview.png` | KPI Tree preview |
 

