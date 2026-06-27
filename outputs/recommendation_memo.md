Recommendation Memo

Executive Summary

An A/B experiment was conducted to evaluate the effectiveness of a new onboarding and activation campaign for a subscription-based digital product. The objective was to determine whether the redesigned onboarding experience could improve user conversion to paid subscriptions while maintaining healthy business and customer experience metrics.

The experiment demonstrated a statistically significant improvement in the primary success metric, Paid Conversion Rate. The Treatment group achieved a Paid Conversion Rate of 7.04%, compared to 3.19% for the Control group, representing an improvement of 3.85 percentage points (120.87%).

A One-Tailed Two-Proportion Z-Test confirmed that this improvement was statistically significant (Z = 3.264, p-value = 0.00055).

However, the analysis also identified important trade-offs. While users converted faster and engagement increased, the Treatment group recorded a higher Support Ticket Rate and a lower Average Revenue per Converted User. These findings suggest that although the new onboarding experience effectively improved conversions, further optimisation is recommended before a full-scale rollout.

⸻

North Star Metric

The North Star Metric selected for this experiment was Paid Conversion Rate.

Paid Conversion Rate measures the percentage of users who become paying customers after experiencing the onboarding journey. Since increasing paid subscriptions was the primary business objective of the experiment, this metric provides the most meaningful measure of success.

⸻

KPI Tree Explanation

The KPI Tree illustrates how the North Star Metric is influenced by three primary business drivers.

User Acquisition

Measures how effectively users enter the onboarding funnel.

Supporting Metrics

* Landing Page Visit Rate
* Trial Start Rate

User Activation

Measures how effectively users engage with and complete the onboarding experience.

Supporting Metrics

* Onboarding Completion Rate
* Average Engagement Score

Conversion Quality

Measures the business value of converted users.

Supporting Metrics

* Average Revenue per User
* Average Revenue per Converted User

To ensure that improvements in Paid Conversion Rate did not negatively impact customer experience or business performance, the following guardrail metrics were also monitored:

* Refund Rate
* Support Ticket Rate
* Average Days to Convert

⸻

Experiment Result Summary

The Treatment group improved most acquisition, activation and conversion metrics compared to the Control group.

Metric	Control	Treatment
Paid Conversion Rate	3.19%	7.04%
Trial Start Rate	25.07%	29.01%
Onboarding Completion Rate	15.65%	21.13%
Average Revenue per User	₹51.97	₹54.25
Average Engagement Score	57.03	62.94
Average Days to Convert	8.86	6.40

However, Average Revenue per Converted User decreased from ₹1,630.10 to ₹770.41, indicating a trade-off between higher conversion volume and revenue generated per converted customer during the 30-day observation period.

⸻

Hypothesis Test Interpretation

A One-Tailed Two-Proportion Z-Test was performed to compare the Paid Conversion Rates of the Control and Treatment groups.

Statistic	Value
Significance Level (α)	0.05
Z Statistic	3.264
P-value	0.00055

Since the p-value is less than the significance level (0.05), the Null Hypothesis was rejected.

This provides strong statistical evidence that the Treatment group achieved a significantly higher Paid Conversion Rate than the Control group and that the observed improvement is unlikely to have occurred due to random chance.

⸻

Guardrail Analysis

Although the Treatment group significantly improved the North Star Metric, several guardrail metrics require attention.

Guardrail Metric	Control	Treatment	Risk Assessment
Refund Rate	0.00%	0.42%	Low Risk
Support Ticket Rate	14.64%	24.93%	High Risk
Average Days to Convert	8.86 days	6.40 days	Positive Outcome
Average Revenue per Converted User	₹1,630.10	₹770.41	Medium Risk

The increase in Support Ticket Rate indicates that more users required customer support after experiencing the Treatment.

Additionally, although the Treatment increased the number of paid conversions, the Average Revenue per Converted User decreased during the 30-day observation period.

These guardrail metrics should be monitored and investigated before considering a full rollout.

⸻

Segment-Level Insights

Segment-level analysis was performed to evaluate whether the experiment produced consistent results across different customer groups.

* Paid Conversion Rate by Region: The Treatment group achieved higher Paid Conversion Rates across all four regions, with the largest improvement observed in the North region.
* Average Engagement Score by Device Type: Engagement improved across Desktop, Mobile, and Tablet users, indicating that the redesigned onboarding experience performed consistently across devices.
* Support Ticket Rate by Traffic Source: Support Ticket Rates increased across most traffic sources, with the largest increases observed for Referral and Paid Search users. Email users were the only segment where the Support Ticket Rate decreased.

These findings indicate that the Treatment performed consistently across multiple customer segments while highlighting areas where additional optimisation may be beneficial.

⸻

Final Recommendation

Recommendation: Continue Testing Before Full Rollout

The experiment successfully achieved its primary objective by significantly improving the Paid Conversion Rate from 3.19% to 7.04%, and the statistical test confirmed that this improvement was significant (p-value = 0.00055).

However, two guardrail metrics require further investigation:

* Support Ticket Rate increased from 14.64% to 24.93%.
* Average Revenue per Converted User decreased from ₹1,630.10 to ₹770.41.

Although the experiment successfully improved conversions, these findings indicate potential trade-offs that should be addressed before launching the new onboarding experience to all users.

Therefore, the recommended next step is to continue testing while maintaining the improvement in Paid Conversion Rate, strengthening Conversion Quality, and reducing customer support requirements before a full rollout.

⸻

Risks and Limitations

* The experiment measured user behaviour over a 30-day observation period and does not evaluate long-term customer retention or customer lifetime value.
* The analysis is based on quantitative metrics and does not include qualitative customer feedback.
* The decrease in Average Revenue per Converted User should be investigated further to better understand its business impact.

⸻

Next Steps

1. Investigate the increase in Support Ticket Rate to identify potential friction points in the onboarding journey.
2. Analyse the decline in Average Revenue per Converted User to better understand its business impact.
3. Collect qualitative user feedback to complement the quantitative findings.
4. Refine the onboarding experience based on identified improvement opportunities.
5. Conduct a follow-up A/B experiment to validate whether the identified guardrail risks have been addressed while maintaining the improvement in Paid Conversion Rate.
