# Hypothesis Test Notes

## Metric Being Tested

**Paid Conversion Rate (North Star Metric)**

The experiment aims to determine whether the new onboarding campaign increases the percentage of users who convert to paid customers compared to the existing onboarding experience.

---

## Null Hypothesis (H₀)

The new onboarding campaign does not improve the Paid Conversion Rate compared to the existing onboarding experience.

**H₀: p(Treatment) ≤ p(Control)**

---

## Alternative Hypothesis (H₁)

The new onboarding campaign improves the Paid Conversion Rate compared to the existing onboarding experience.

**H₁: p(Treatment) > p(Control)**

---

## Type of Test

**One-tailed hypothesis test**

The business objective is to determine whether the Treatment increases Paid Conversion Rate rather than simply checking for any difference between the two groups.

---

## Significance Level

**α = 0.05 (5%)**

A 5% significance level is used to determine whether the observed improvement is statistically significant.

---

## Reason for Choosing this Metric

Paid Conversion Rate is the North Star Metric for this experiment because it directly measures the success of the onboarding campaign in converting users into paying customers. It aligns with the primary business objective of increasing subscription conversions.

---

## Interpretation Logic

- If the **p-value < 0.05**, reject the null hypothesis and conclude that the new onboarding campaign significantly improves Paid Conversion Rate.
- If the **p-value ≥ 0.05**, fail to reject the null hypothesis and conclude that there is insufficient evidence to state that the new onboarding campaign improves Paid Conversion Rate.

# Hypothesis Test Notes

## Objective

The objective of this analysis is to determine whether the new onboarding campaign (Treatment group) resulted in a statistically significant improvement in the Paid Conversion Rate compared to the existing onboarding experience (Control group).

---

# 1. Metric Being Tested

**Primary Metric:** Paid Conversion Rate (North Star Metric)

Paid Conversion Rate was selected because it directly measures the success of the onboarding campaign in converting users into paying customers. Since increasing paid subscriptions is the primary business objective, this is the most appropriate metric for hypothesis testing.

---

# 2. Statistical Test Used

**Experiment Design:** A/B Test

**Statistical Analysis:** Two-Proportion Z-Test

A Two-Proportion Z-Test was selected because:

- The primary metric (Paid Conversion Rate) is binary (Converted / Not Converted).

- The Control and Treatment groups are independent.

- Both groups have sufficiently large sample sizes (690 and 710 users).

- The objective is to compare two conversion rates.

---

# 3. Null Hypothesis (H₀)

The new onboarding campaign does not improve the Paid Conversion Rate compared to the existing onboarding experience.

**H₀: p(Treatment) ≤ p(Control)**

---

# 4. Alternative Hypothesis (H₁)

The new onboarding campaign improves the Paid Conversion Rate compared to the existing onboarding experience.

**H₁: p(Treatment) > p(Control)**

---

# 5. Type of Test

**One-tailed hypothesis test**

A one-tailed test is appropriate because the business objective is specifically to determine whether the Treatment improves the Paid Conversion Rate, rather than simply checking whether the two groups are different.

---

# 6. Significance Level

**α = 0.05 (5%)**

A significance level of 5% was selected as the decision threshold for determining statistical significance.

---

# 7. Summary of Test Inputs

| Metric | Control | Treatment |

|---------|---------|-----------|

| Total Users | 690 | 710 |

| Converted Users | 22 | 50 |

| Paid Conversion Rate | 3.19% | 7.04% |

---

# 8. Test Output

| Statistic | Value |

|-----------|-------|

| Pooled Proportion | 5.14% |

| Standard Error | 0.01181 |

| Z Statistic | 3.264 |

| P-value | 0.00055 |

---

# 9. Decision Rule

- Reject the Null Hypothesis if **P-value < 0.05**

- Otherwise, fail to reject the Null Hypothesis.

---

# 10. Decision

Since the calculated P-value (**0.00055**) is less than the significance level (**0.05**), the Null Hypothesis is rejected.

---

# 11. Business Interpretation

The statistical analysis indicates that the Treatment group achieved a significantly higher Paid Conversion Rate than the Control group.

The increase from **3.19%** to **7.04%** is statistically significant and is unlikely to have occurred due to random chance alone.

Therefore, there is strong statistical evidence that the new onboarding campaign successfully improved user conversion to paid customers.

While the primary metric improved significantly, the final business recommendation should also consider guardrail metrics such as Support Ticket Rate, Refund Rate and Average Revenue per Converted User before recommending a full rollout.


