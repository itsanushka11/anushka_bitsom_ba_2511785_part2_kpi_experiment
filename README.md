# anushka_bitsom_ba_2511785_part2_kpi_experiment
Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

Business Context

This project analyzes the performance of a new onboarding and activation campaign launched by a subscription-based digital product company. The company aims to improve user activation, engagement, and conversion into paying subscribers.

Users were randomly assigned to one of two groups:

- Control Group: Existing onboarding experience
- Treatment Group: New onboarding and activation campaign

The objective of this analysis is to determine whether the treatment experience should be rolled out to all users based on business impact, statistical evidence, and guardrail metric evaluation.

---

Business Problem Statement

The company must decide whether the new onboarding and activation campaign should replace the existing onboarding experience.

This decision impacts multiple stakeholders, including product teams, marketing teams, customer success teams, and company leadership. The primary goal is to increase the number of users who convert into paying subscribers while maintaining a positive user experience and healthy business performance.

Success will be evaluated using a primary North Star metric supported by additional KPIs and guardrail metrics. A recommendation will only be made if the treatment demonstrates meaningful business improvement supported by statistical evidence and without creating significant risks in key guardrail metrics.

---

Dataset Description

The dataset contains user-level experiment data collected from both Control and Treatment groups.

Key variables include:

- User ID
- Experiment Group
- Landing Page Visit
- Trial Start
- Onboarding Completion
- Paid Conversion
- Revenue
- Refund Request
- Support Ticket
- Engagement Score
- Days to Convert
- Region
- Device Type
- Traffic Source
- Plan Type

The dataset is stored as:

"data/campaign_experiment_data.xlsx"

---

North Star Metric

Selected Metric: Paid Conversion Rate

Definition

Paid Conversion Rate = Number of Paid Conversions ÷ Total Users

Why This Is the North Star Metric

Paid conversion directly measures the business objective of turning users into paying subscribers. Since the company operates on a subscription-based model, increasing paid conversions directly contributes to revenue growth and long-term business sustainability.

Supporting Metrics

The following metrics support the North Star metric:

- Landing Page Visit Rate
- Trial Start Rate
- Onboarding Completion Rate
- Average Revenue Per User (ARPU)
- Average Revenue Per Converted User
- Engagement Score
- Days to Convert

These metrics explain user behavior and help identify which stages of the onboarding funnel contribute to conversion success.

Risks of Optimizing Only This Metric

Improving conversion alone may lead to unintended consequences, such as:

- Increased refund requests
- Higher support burden
- Lower user satisfaction
- Reduced quality of acquired customers

Therefore, guardrail metrics must also be evaluated before making a rollout decision.

---

KPI Tree Summary

North Star Metric:

Paid Conversion Rate

Primary KPI Drivers:

1. Acquisition Quality

- Landing Page Visit Rate
- Traffic Source Quality

2. Activation Success

- Trial Start Rate
- Onboarding Completion Rate

3. User Engagement

- Engagement Score
- Days to Convert

Guardrail Metrics:

- Refund Rate
- Support Ticket Rate
- Average Revenue Per User
- Segment-Level Performance

The complete KPI tree is available in:

"outputs/kpi_tree.png"

Preview screenshot:

"screenshots/kpi_tree_preview.png"

---

Data Cleaning and Preparation

The dataset was reviewed before analysis to ensure data quality.

The following checks were performed:

Missing Values

Missing values were identified and reviewed across all variables. Missing values in categorical fields were documented, while missing values in conversion-related fields were assessed for business relevance.

Duplicate User IDs

Duplicate user records were identified and reviewed to ensure they did not distort experiment results.

Group Counts

Control and Treatment group sizes were validated to confirm proper experiment allocation.

Binary Value Validation

Binary fields such as conversions, onboarding completion, support tickets, and refunds were checked to ensure values were limited to valid 0/1 entries.

Revenue Outlier Review

Revenue distributions were reviewed to identify unusual observations that could distort average revenue metrics.

Segment Distribution Review

Region, device type, traffic source, and plan type distributions were compared across experiment groups to verify balanced allocation.

The cleaned dataset and analysis workbook are available in:

"analysis/experiment_analysis.xlsx"

---

Experiment Analysis Approach

The analysis compared Control and Treatment groups across key business metrics, including:

- User Count
- Landing Page Visit Rate
- Trial Start Rate
- Onboarding Completion Rate
- Paid Conversion Rate
- Average Revenue Per User
- Average Revenue Per Converted User
- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Average Days to Convert

Additional segment-level analysis was conducted for selected metrics across:

- Region
- Device Type
- Traffic Source
- Plan Type

Results are summarized in:

"outputs/experiment_summary.xlsx"

---

Hypothesis Testing

Metric Tested

Paid Conversion Rate

Null Hypothesis (H₀)

There is no difference in paid conversion rate between the Control and Treatment groups.

Alternative Hypothesis (H₁)

The Treatment group has a higher paid conversion rate than the Control group.

Test Type

One-tailed Two-Proportion Z-Test

Significance Level

α = 0.05

Results

- Control Conversion Rate = 3.17%
- Treatment Conversion Rate = 6.99%
- Z Statistic ≈ 3.25
- P Value ≈ 0.0011

Since the p-value is below the significance threshold of 0.05, the null hypothesis is rejected.

This indicates that the treatment campaign significantly improves paid conversion performance.

Detailed test notes are available in:

"analysis/hypothesis_test_notes.md"

Evidence screenshot:

"screenshots/hypothesis_test_output.png"

---

Guardrail Metrics Considered

To ensure business improvement is sustainable, the following guardrail metrics were evaluated:

- Refund Rate
- Support Ticket Rate
- Average Revenue Per User
- Average Revenue Per Converted User
- Engagement Score
- Days to Convert
- Segment-Level Performance

These metrics were reviewed to identify any negative side effects associated with the treatment experience.

---

Final Recommendation

Recommendation: Launch

The treatment campaign demonstrates a statistically significant improvement in paid conversion rate compared to the control experience.

The experiment provides strong evidence that the new onboarding experience improves user activation and conversion performance.

While conversion improvements are substantial, support-related metrics should continue to be monitored to ensure increased customer support demand does not offset business gains.

Therefore, the recommendation is to proceed with a broader rollout of the treatment experience while maintaining ongoing monitoring of guardrail metrics.

---

Assumptions and Limitations

- Experiment assignment is assumed to be random.
- Revenue quality is evaluated using available revenue fields only.
- User behavior outside the observed experiment window is not included.
- Missing values may impact certain segment analyses.
- Results reflect the available sample and may differ in future cohorts.

---

Repository Contents

Data

- data/campaign_experiment_data.xlsx

Analysis

- analysis/experiment_analysis.xlsx
- analysis/hypothesis_test_notes.md

Outputs

- outputs/kpi_tree.png
- outputs/experiment_summary.xlsx
- outputs/recommendation_memo.md

Screenshots

- screenshots/summary_metrics.png
- screenshots/hypothesis_test_output.png
- screenshots/kpi_tree_preview.png

Documentation

- README.md
