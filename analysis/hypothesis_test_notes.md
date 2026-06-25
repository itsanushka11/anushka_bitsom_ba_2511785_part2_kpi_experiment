# Hypothesis Test Notes

## Business Objective

The company launched a new onboarding and activation campaign to improve user conversion and early user engagement. The objective of this experiment is to determine whether the new onboarding experience should be rolled out to all users.

---

## Primary Metric Selected

### Paid Conversion Rate

**Definition**

> Paid Conversion Rate = Users Converted to Paid ÷ Total Users

### Why This Metric?

* Directly measures the success of the onboarding campaign.
* Closely linked to revenue growth and business performance.
* Represents the final outcome of the user activation funnel.
* Provides a clear basis for launch decisions.

---

## Hypotheses

### Null Hypothesis (H₀)

There is no statistically significant improvement in Paid Conversion Rate between the Treatment group and the Control group.

**H₀:** Treatment Conversion Rate ≤ Control Conversion Rate

### Alternative Hypothesis (H₁)

The Treatment group has a statistically significant higher Paid Conversion Rate than the Control group.

**H₁:** Treatment Conversion Rate > Control Conversion Rate

---

## Test Type

### One-Tailed Test

A one-tailed test is used because the business objective is specifically to determine whether the new onboarding experience improves conversion performance.

The experiment is not testing for any difference in either direction; it is testing for an improvement.

---

## Significance Level

**α = 0.05**

* Confidence Level: 95%
* Significance Level: 5%

A result will be considered statistically significant if:

**p-value < 0.05**

---

## Sample Sizes

| Group     | Users |
| --------- | ----: |
| Control   |   693 |
| Treatment |   715 |

---

## Observed Results

| Metric               | Control | Treatment |
| -------------------- | ------: | --------: |
| Paid Conversion Rate |   3.17% |     6.99% |

### Observed Lift

**6.99% − 3.17% = 3.82 percentage points**

The Treatment group achieved a higher observed conversion rate than the Control group.

---

## Decision Rule

### Reject H₀ If

**p-value < 0.05**

### Fail to Reject H₀ If

**p-value ≥ 0.05**

---

## Business Interpretation Logic

The experiment outcome will be evaluated primarily using the Paid Conversion Rate.

However, a recommendation will not be made solely on conversion improvement.

The following guardrail metrics must also be reviewed:

* Refund Rate
* Support Ticket Rate
* Average Engagement Score
* Average Days to Convert
* Segment-Level Performance

---

## Recommendation Criteria

A full rollout recommendation should only be made if:

* Conversion improvement is statistically significant.
* No major guardrail metric deteriorates materially.
* Segment-level analysis supports consistent performance across key user groups.
* The business impact outweighs potential risks.

---

## Expected Business Decision

Based on the hypothesis test results and guardrail evaluation, one of the following recommendations will be made:

* Launch to all users
* Launch only for selected segments
* Continue testing
* Do not launch

---

## Hypothesis Test Result

A two-sample proportion test was conducted using Paid Conversion Rate as the primary metric.

### Test Results

| Metric                    |  Value |
| ------------------------- | -----: |
| Control Conversion Rate   |  3.17% |
| Treatment Conversion Rate |  6.99% |
| Z-Score                   |   3.25 |
| P-Value                   | 0.0006 |
| Significance Level        |   0.05 |

### Interpretation

The p-value (**0.0006**) is lower than the significance level (**0.05**).

Therefore, the **Null Hypothesis (H₀)** is rejected.

The analysis provides strong statistical evidence that the Treatment onboarding experience increased the Paid Conversion Rate compared with the Control experience.

The observed improvement is statistically significant and unlikely to have occurred by random chance.

---

# Guardrail Metrics Evaluation

## Purpose

While Paid Conversion Rate was selected as the primary success metric, additional guardrail metrics were evaluated to ensure that the Treatment experience did not create unintended negative business impacts.

---

## Refund Rate

| Group     | Refund Rate |
| --------- | ----------: |
| Control   |       0.00% |
| Treatment |       0.42% |

### Observation

The Treatment group shows a small increase in refund requests. Although the increase should be monitored, the overall refund rate remains low and does not currently represent a major business risk.

---

## Support Ticket Rate

| Group     | Support Ticket Rate |
| --------- | ------------------: |
| Control   |                0.22 |
| Treatment |                0.37 |

### Observation

Support ticket volume increased in the Treatment group. This may indicate that some users require additional assistance during onboarding. However, the increase is moderate and should be monitored after rollout.

---

## Average Engagement Score

| Group     | Average Engagement Score |
| --------- | -----------------------: |
| Control   |                    57.03 |
| Treatment |                    62.93 |

### Observation

User engagement improved substantially in the Treatment group. This suggests that users are interacting more actively with the product after experiencing the new onboarding flow.

---

## Average Days to Convert

| Group     | Average Days to Convert |
| --------- | ----------------------: |
| Control   |                    8.86 |
| Treatment |                    6.40 |

### Observation

Users in the Treatment group converted more quickly than users in the Control group. Faster conversion is beneficial because it accelerates revenue generation and user activation.

---

## Revenue Quality Assessment

### Average Revenue Per User

| Group     | Average Revenue Per User |
| --------- | -----------------------: |
| Control   |                    51.75 |
| Treatment |                    53.88 |

### Average Revenue Per Converted User

| Group     | Average Revenue Per Converted User |
| --------- | ---------------------------------: |
| Control   |                            1630.10 |
| Treatment |                             770.41 |

### Observation

Average Revenue Per User increased slightly in the Treatment group, indicating positive overall revenue impact.

However, Average Revenue Per Converted User decreased significantly. This suggests that the Treatment group generated more conversions, but those conversions may be associated with lower-value subscriptions or lower-spending users. This should be monitored in future experiments.

---

## Guardrail Risk Assessment

### Positive Signals

* Higher Paid Conversion Rate
* Higher Engagement Score
* Faster Time to Convert
* Higher Revenue Per User

### Potential Risks

* Increased Refund Rate
* Increased Support Ticket Rate
* Lower Revenue Per Converted User

### Overall Assessment

The Treatment experience demonstrates strong improvement in conversion and engagement metrics. While some guardrail metrics indicate areas for monitoring, none of the observed risks are severe enough to outweigh the benefits observed in the primary success metric.
